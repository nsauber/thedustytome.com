---
layout: post
title:  "Installing Dropbox 1.0 in Ubuntu 10.10"
date:   2010-12-27 17:03:00
tags: dropbox ubuntu
---

[Dropbox](http://www.dropbox.com/) recently released a new 1.0 client for all platforms with several new features. Particularly, the selective folder syncing would be very helpful for the Ubuntu netbook my wife uses. However, the Dropbox website only offers Linux downloads for the 0.6.7 version. Strange.

A little googling led to this [forum discussion](http://forums.dropbox.com/topic.php?id=29015), which linked to this [forum post](http://forums.dropbox.com/topic.php?id=29000&amp;replies=46#post-182280) and this French-language [blog posting](http://blog.nicolargo.com/2010/12/comment-installer-vraiment-dropbox-1-0-sous-gnulinux.html). The steps are quite easy, but it's bothersome that Dropbox hasn't made this obvious. The download and installation process is seamless for both other platforms.

1. Stop the Dropbox client to your home folder.
1. Download the appropriate 1.0.10 linux client for [x86](http://dl-web.dropbox.com/u/17/dropbox-lnx.x86-1.0.10.tar.gz) or [x86_64](http://dl-web.dropbox.com/u/17/dropbox-lnx.x86_64-1.0.10.tar.gz).
1. Rename or delete the '.dropbox-dist' folder (in a terminal at ~, `mv .dropbox-dist .dropbox-dist.backup`).
1. Unpack the downloaded client archive (`tar zxvf dropbox-lnx.x86-1.0.10.tar.gz`).
1. Restart the Dropbox client from the Ubuntu menu (Applications -&gt; Internet -&gt; Dropbox).

The Dropbox icon should appear in the Ubuntu notification area. The new version (1.0.10) should show in the Preferences window, on the Account tab.

**Update 1/31/2011:** I installed Dropbox on my new laptop Ubuntu install using the 0.6.7 installer downloaded from the website. After installing, it immediately downloaded an update to the 1.0.20 version. Thanks, Dropbox team.
