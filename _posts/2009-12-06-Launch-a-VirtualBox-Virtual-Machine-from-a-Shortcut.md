---
layout: post
title:  "Launch a VirtualBox Virtual Machine from a Shortcut"
date:   2009-12-06 15:11:00
tags: ubuntu virtualbox
---

Found [this link](http://blarts.wordpress.com/2007/12/03/how-to-launch-a-virtualbox-virtual-machine-from-a-shortcut/) about creating a shortcut to launch a VirtualBox machine directly without having to first load the VirtualBox GUI.  In short, the linux command-line is:

{% highlight console %}
VBoxManage startvm <your virtual machine name>
{% endhighlight %}
