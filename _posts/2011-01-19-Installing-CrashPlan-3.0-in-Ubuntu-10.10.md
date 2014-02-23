---
layout: post
title:  "Installing CrashPlan 3.0 in Ubuntu 10.10"
date:   2011-01-19 19:15:00
tags: backup crashplan ubuntu
---

I've put off installing online backup software for ages.  It's the kind of thing that sits on your TODO list, nagging at you, but for some reason it just always seemed very daunting.  At some point a friend of mine recommended a service called [CrashPlan](http://www.crashplan.com/).  It's cheap ($6 a month gets you unlimited space for all your home's computers), and best of all, it supports Windows, Mac, and (gasp!) Linux.  The program also allows free offline backup, for example to a dedicated hard drive or another computer on your network.  They offer a 30-day trial of their online backup service, which I'm trying right now.  So far, I'm thoroughly impressed and will likely buy a year's subscription when my 30 days are up!

My only gripes have to do with ease-of-use on Linux:

* The first is with the Linux installation, which basically consisted of a shell script which obviously ran in a geeky terminal window.  To be fair, CrashPlan gets major points for even supporting Linux, so this does feel a bit like nitpicking.  And, granted, Linux users tend to be significantly less command-line averse, but I'd still prefer to see them offer a more novice-friendly installation option.  I have no trouble recommending Ubuntu to the average "grandma" user (web/email/word processing), but this is not something Grandma could install herself.  It's just not up to par with the ease-of-use expected on the more ubiquitous Windows or Mac platforms.
* The second gripe is with the shortcut (launcher in Ubuntu parlance) for the CrashPlanDesktop GUI configuration tool.  The installation added a shortcut to the tool on my desktop, but not one to the Ubuntu Applications menu.  Other third-party installations (like Dropbox) have integrated into the standard Ubuntu applications listing, so why doesn't CrashPlan?  Also, after rebooting, the shortcut disappeared and I had to manually re-create it.  This was probably a glitch, but the annoyance would have been averted if there had been a shortcut in the Applications menu.

Gripes aside, the installation worked without a hitch.  I just chose all the default options and it installed and ran fine.  The GUI tool is clean, simple to use and understand, but offers plenty of options to fine-tune the backup to my needs.

For future reference, to recreate the CrashPlanDesktop launcher, just create a new launcher or copy an existing one, open it in a text editor, and replace the contents with the following:

{% highlight text %}
#!/usr/bin/env xdg-open

[Desktop Entry]
Version=1.0
Type=Application
Terminal=false
Icon[en_US]=/usr/local/crashplan/skin/icon_app_128x128.png
Exec=/usr/local/bin/CrashPlanDesktop
Name[en_US]=CrashPlanDesktop
Comment[en_US]=CrashPlan Desktop Configuration Tool
Name=CrashPlanDesktop
Comment=CrashPlan Desktop Configuration Tool
Icon=/usr/local/crashplan/skin/icon_app_128x128.png
{% endhighlight %}
