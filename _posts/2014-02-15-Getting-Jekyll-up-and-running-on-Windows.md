---
layout: post
title:  "Getting Jekyll up and running on Windows"
date:   2014-02-15 12:27:00
#categories: jekyll githubpages
tags: githubpages jekyll ruby windows
---

I've started tinkering with [GitHub Pages][github-pages] and [Jekyll][jekyll], partially motivated by a [recent post][haack-post] by Phil Haack.

Unfortunately, Jekyll (as with many Ruby projects) is not officially supported on Windows, though it's possible with a little fiddling around. There are a number of "here's what worked for me" posts out there, all of which are a little different. Here's my contribution...

The [Jekyll QuickStart][jekyll-quickstart] instructions say getting a Jekyll site up and running is a simple as:

{% highlight console %}
~ $ gem install jekyll
~ $ jekyll new myblog
~ $ cd myblog
~/myblog $ jekyll serve
{% endhighlight %}

Well since I'm on a pretty new machine, `gem install jekyll` won't work because I don't have Ruby installed yet. So I downloaded and ran the Ruby v1.9.3 installer from [rubyinstaller.org][rubyinstaller-downloads], which installed everything to 'C:\Ruby193\'. The only option I changed from default during the install was to check the box adding the ruby binaries to my path.

Now I can run `gem install jekyll`, but it complains because I don't have the Ruby DevKit installed, and directs me to [installation instructions](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit) on the GitHub project wiki.

I downloaded the DevKit for Ruby v1.9.3 (again from [rubyinstaller.org][rubyinstaller-downloads]). The installer relies on you to choose a good permanent home for the extracted DevKit files. I chose to put it underneath my Ruby install location in 'C:\Ruby193\devkit\' (creating the 'devkit' directory myself). I saved the .exe file to that location and ran the .exe to extract it's files to the same directory. I then opened up a console and ran `ruby dk.rb init` and `ruby dk.rb install`, per the instructions linked above.

Now that Ruby and the Ruby DevKit were installed, I was able to run `gem install jekyll` without error. Following Jekyll's QuickStart instructions, I ran `jekyll new myblog` to create a new default blog site. It ran without error.

I then ran `jekyll serve`, but it blew up with the following error output:
{% highlight shell-session %}
C:\temp\JekyllDemo\myblog>jekyll serve
Configuration file: C:/temp/JekyllDemo/myblog/_config.yml
            Source: C:/temp/JekyllDemo/myblog
       Destination: C:/temp/JekyllDemo/myblog/_site
      Generating... C:/Ruby193/lib/ruby/gems/1.9.1/gems/posix-spawn-0.3.8/lib/posix/spawn.rb:162: warning: cannot close fd before spawn
'which' is not recognized as an internal or external command,
operable program or batch file.
error: Invalid argument - C:/temp/JekyllDemo/myblog/_site/C:. Use --trace to view backtrace
{% endhighlight %}

While the error isn't exactly the same, I tried the guidance at the bottom of [this post](http://minimaldev.com/how-to-install-jekyll-on-windows/), uninstalling the pygments.rb code formatting gem and reinstalling to an older version which (apparently) plays nicer with Windows.

{% highlight console %}
gem uninstall pygments.rb
gem install pygments.rb --version "=0.5.0"
{% endhighlight %}

And that resolved some of the errors, but not all:

{% highlight shell-session %}
C:\temp\JekyllDemo\myblog>jekyll serve
Configuration file: C:/temp/JekyllDemo/myblog/_config.yml
            Source: C:/temp/JekyllDemo/myblog
       Destination: C:/temp/JekyllDemo/myblog/_site
      Generating... error: Invalid argument - C:/temp/JekyllDemo/myblog/_site/C:. Use --trace to view backtrace
{% endhighlight %}

I then found an [answer on StackOverflow](http://stackoverflow.com/questions/21164557/jekyll-serve-error-invalid-argument-issue) which resolved the remaining problem:

{% highlight console %}
gem uninstall jekyll
gem install jekyll --version "=1.4.2"
{% endhighlight %}

Now I can `jekyll serve` and browse the resulting page . Nice!

Not too painful, all in all. Basically it came down to getting the right (well, older compatible) versions installed:

* Ruby v1.9.3
* Ruby DevKit for Ruby v1.9.3
* jekyll v1.4.2
* pygments.rb v0.5.0

Hopefully some awesome contributors to the Jekyll and Pygments.rb projects will get the newer versions stablized on Windows. In the meantime, big ups to everyone on those projects for their work to date!

**Update:** After starting to work with Jekyll, I quickly wanted to be able to run `jekyll serve --watch` so the site would automatically detect updates as I created posts and otherwise played around. But running that command resulted in the following error (I've omitted a stack trace for brevity):

{% highlight shell-session %}
C:\temp\JekyllDemo\myblog>jekyll serve --watch
Configuration file: C:/temp/JekyllDemo/myblog/_config.yml
            Source: C:/temp/JekyllDemo/myblog
       Destination: C:/temp/JekyllDemo/myblog/_site
      Generating... done.
 Auto-regeneration: enabled
C:/Ruby193/lib/ruby/site_ruby/1.9.1/rubygems/custom_require.rb:36:in `require': cannot load such file -- wdm (LoadError)
{% endhighlight %}

Thanks to [some folks on StackOverflow](http://stackoverflow.com/questions/20459859/ruby-error-cannot-load-such-file-wdm-loaderror), I was able to resolve this error by installing the 'wdm' gem via:

{% highlight console %}
gem install wdm
{% endhighlight %}

Editing the site is much easier now that watch is working.

[github-pages]: http://pages.github.com
[jekyll]: http://jekyllrb.com
[haack-post]: http://haacked.com/archive/2013/12/02/dr-jekyll-and-mr-haack/
[jekyll-quickstart]: http://jekyllrb.com/docs/quickstart/
[rubyinstaller-downloads]: http://rubyinstaller.org/downloads