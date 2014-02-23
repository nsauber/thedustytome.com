---
layout: post
title:  "VirtualBox Panel Indicator for Ubuntu"
date:   2011-02-21 10:15:00
---

Big thanks to [Michael Otto](https://launchpad.net/indicator-virtualbox) for creating an Ubuntu Indicator Panel applet! It has a drop-down menu that lets you directly launch any VirtualBox VM you have configured on your machine. Also props to the [several][several] [kindly][kindly] [bloggers][bloggers] who gave instructions for installing this slick utility.

It's not part of the official Ubuntu repository (yet, I'm sure) so you need to add the correct repository and install it using apt. The command-line commands are:

{% highlight console %}
sudo add-apt-repository ppa:michael-astrapi/ppa
sudo apt-get update
sudo apt-get install indicator-virtualbox
{% endhighlight %}

You can have it start automatically on log-in by adding it to the list of Startup Applications (System -> Preferences -> Startup Applications).  The command to start it is:

{% highlight console %}
indicator-virtualbox
{% endhighlight %}

This is so helpful it's bound to end up in the primary Ubuntu repository in the next release or two. Thanks again, Michael!

[several]: http://www.webupd8.org/2010/12/indicator-virtualbox-launch-virtual.html
[kindly]: http://www.omgubuntu.co.uk/2010/12/indicator-virtualbox-adds-quick-click-os-launching-to-your-panel/
[bloggers]: http://www.unixmen.com/linux-tutorials/1411-indicator-virtualbox-launch-virtualbox-machines-from-your-quick-launch-panel-


