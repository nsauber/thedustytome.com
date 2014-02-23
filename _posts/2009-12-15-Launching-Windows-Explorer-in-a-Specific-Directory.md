---
layout: post
title:  "Launching Windows Explorer in a Specific Directory"
date:   2009-12-15 18:59:00
tags: utilities windowsxp
---

Here's something I've wanted to do for ages in Windows: starting Explorer in a specific directory from a shortcut.  The command-line is this:

{% highlight console %}
C:\WINDOWS\explorer.exe /n,/e,c:\somepath
{% endhighlight %}

Note that the commas are necessary. Refer to [this knowledge base article](http://support.microsoft.com/kb/152457) for info on the commane-line switches.