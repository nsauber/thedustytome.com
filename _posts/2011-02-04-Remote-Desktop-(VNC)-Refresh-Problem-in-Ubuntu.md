---
layout: post
title:  "Remote Desktop (VNC) Refresh Problem in Ubuntu"
date:   2011-02-04 17:22:00
tags: remotedesktop ubuntu vnc
---

I set up my main desktop computer to enable remote access to my desktop (System -> Preferences -> Remote Desktop).  Then, when I access it from my laptop (Applications -> Internet -> Remote Desktop Viewer), I run into problems.  I am able to make a connection, and see the initial screen state when I first connect.  Any actions I take through remote desktop are visible on the desktop monitor, but my laptop's Remote Desktop Viewer doesn't get screen updates... it always looks as it did when I first connected.

This is apparently a [known](http://ubuntuforums.org/showthread.php?t=1383356) [issue](http://ubuntuforums.org/showthread.php?p=7168779) with a workaround.  You just have to disable visual effects on the computer you're accessing (via System -> Preferences -> Appearance -> Visual Effects -> None).  This is definitely not ideal as it does clunkify and de-prettify Ubuntu a bit on the target system, but I can live with it for now as I'll be using the laptop far more often.