---
layout: post
title:  "Turning off Bluetooth by Default in Ubuntu"
date:   2011-02-09 19:15:00
tags: bluetooth systemadministration ubuntu
---

The Ubuntu 10.10 install on my new laptop turns on the Bluetooth adapter by default, which is a minor battery drain.  Since I rarely (if ever) use any Bluetooth devices, I'd rather turn off the adapter by default.  Unfortunately, this is not as simple as changing an option in the Bluetooth panel application and requires some minor command-line tweakage.

Per [this helpful post](http://wwww.ubuntuforums.org/showthread.php?t=1333221) on the Ubuntu forums, I just had to edit the file `/etc/init.d/rc.local`:

{% highlight console %}
sudo vim /etc/init.d/rc.local
{% endhighlight %}

And add the following line:

{% highlight console %}
rfkill block bluetooth
{% endhighlight %}

Although the post suggests putting the line at the end of `rc.local`, that didn't seem to work for me.  So I added it near the beginning and all is well.  Now, after booting up and logging in, the Bluetooth panel icon is happily grayed-out to show that the adapter is deactivated.
