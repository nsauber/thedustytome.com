---
layout: post
title:  "Hiding the VirtualBox 'Mini Menu' bar in Fullscreen"
date:   2011-01-21 23:22:00
tags: virtualbox
---

When you send a VirtualBox client into fullscreen mode <kbd>Host</kbd> + <kbd>F</kbd>, there's a small 'Mini Menu' bar pinned to the bottom of the screen that has Devices and Machine menus on it.  This gets in the way, and although you can 'un-pin' it so it auto-hides, I keep bumping it in WinXP VMs when I'm mousing around the XP taskbar.  Fortunately, the interwebs is our friend, and a kind blogger [pointed out](http://artotech.wordpress.com/2010/12/23/moving-the-mini-menu-bar-in-fullscreen-virtualbox/) that you can move the Mini Menu bar to the top of the screen:

1. Make sure your VM is not running
1. Open the Settings for that VM by right-clicking on it in the main VirtualBox GUI
1. Go to General -&gt; Advanced tab
1. Check the Mini Menu entry for 'Show at top of screen'

You can also turn the thing off entirely, if so desired.
