---
layout: post
title:  "Installing Ubuntu 9.04 NBR in VirtualBox 3.0"
date:   2009-11-04 18:53:00
tags: ubuntu virtualbox
---

In preparation for setting up our soon-to-arrive (hopefully) new [nettop](http://www.newegg.com/Product/Product.aspx?Item=N82E16883103234&amp;nm_mc=AFC-C8Junction&amp;cm_mmc=AFC-C8Junction-_-Desktop+PC-_-Acer+America-_-83103234) as a home theater PC, I'm experimenting with different media center programs and Linux/Ubuntu variations.  I think I've settled on using [Ubuntu Netbook Remix](http://www.canonical.com/projects/ubuntu/unr) (NBR) as the base OS.  The large-icon interface seems like it would work well on a TV when viewed from a distance.  On top of this I'll install [XBMC](http://xbmc.org/) (or maybe [Boxee](http://www.boxee.tv/homepage/)) and the Linux version of the [Hulu Desktop](http://www.hulu.com/labs/hulu-desktop-linux).  I started with installing the fresh-out-of-the-oven Ubuntu 9.10 NBR, but found out that XBMC doesn't currently support [Karmic](http://releases.ubuntu.com/karmic/) (they will when they release their next full version).  So for now I'm stuck with [Jaunty](http://releases.ubuntu.com/jaunty/) if I want XBMC.

The first challenge was finding the 9.04 downloads, since 9.10 just came out.  I eventually googled my way to [this page](http://releases.ubuntu.com/jaunty/) which contains (at the bottom) links to all variety of 9.04 versions.  I grabbed the torrent file for the 9.04 Netbook Remix and queued it up in Transmission, Ubuntu's default BitTorrent client.

The next challenge was being able to mount the downloaded .img file.  Why oh why didn't Canonical release an .iso?  I first tried converting the .img to a .iso using the [ccd2iso](http://www.mopedia.co.uk/2008/02/convert-img-to-iso-in-ubuntu.html) console command (didn't work).  Then I found [this blog post](http://mdm-adph.blogspot.com/2009/05/using-img-files-with-virtualbox-to-test.html), which explains how to convert a .img to a VirtualBox hard drive file (.vdi) and mount the file as a second hard drive in VirtualBox.  The console command to convert is:

{% highlight console %}
VBoxManage convertfromraw -format VDI [filename].img [filename].vdi
{% endhighlight %}

This worked like a charm.  I've now got a Jaunty NBR install in VirtualBox.  Next step is to install XBMC and Hulu Desktop to see how they play together.