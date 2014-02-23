---
layout: post
title:  "Cloning a Virtual Hard Drive in VirtualBox 3.0"
date:   2011-01-19 18:10:00
tags: virtualbox
---

VirtualBox doesn't make it easy to clone/copy the configured virtual machines and their hard drive image files.  To create an exact clone of an existing VM, you have to first clone the .vdi disk image file from the command line.  Then you create a new VM with the same configuration, but point it to use the cloned .vdi image instead of the original.  You'd think this would be provided as a one-click menu option, but it's not.

In Ubuntu, the .vdi files are stored in:

{% highlight text %}
~/.VirtualBox/HardDisks/
{% endhighlight %}

and the command to clone a .vdi is:

{% highlight text %}
VBoxManage clonevdi [source .vdi] [new .vdi]
{% endhighlight %}

More (and better) info can be found from [this article](http://srackham.wordpress.com/cloning-and-copying-virtualbox-virtual-machines/).
