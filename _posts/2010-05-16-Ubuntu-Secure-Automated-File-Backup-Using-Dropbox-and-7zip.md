---
layout: post
title:  "Ubuntu - Secure, Automated File Backup Using Dropbox and 7zip"
date:   2010-05-16 19:18:00
tags: backup dropbox ubuntu
---

Since switching to Ubuntu as my primary OS, I've been lax in setting up an automatic backup of important files.  I finally got around to it this weekend, using a combination of cron (via Gnome Scheduler), 7zip, some simple shell scripting, and the Dropbox application for linux.

At this point, I'm not concerned about backing up every little thing.  Just the file-based equivalent of "what would you grab if the house was on fire".  So no music, videos, or large amounts of photos for this.  And, of course, some of these files will be sensitive or personal in nature, so I want to make sure they're encrypted.  Dropbox does a fine job of encrypting the files they store, but they're still just a password hack away from public access, so providing a second encryption password for sensitive data is at least a step towards more protection.

So let's get this set up...

First things first, I installed the [Dropbox](https://www.dropbox.com/) client for linux.  Dropbox creates a folder in your home directory that is automatically backed up to their servers, and is synced among any other computers or devices connected to your account.  They have clients for the three major platforms (Win/Mac/Lin) plus iPhone and Android apps.  You can check out their website for instructions or more info.

Second, I installed 7zip (search "7zip" in the Ubuntu Software Center) to get the best compression rate.  I don't want to eat up more of my limited Dropbox storage than I need to.  I got some help on the 7zip command-line options from (what else?) the [man page](http://manpages.ubuntu.com/manpages/gutsy/man1/7z.1.html).

Next, I created a shell script to create a compressed and encrypted archive of any specified folder:

{% highlight text %}
#!/bin/bash

if [ -z "$1" ]; then
echo usage: first parameter must be a target filename
exit
fi
if [ -z "$2" ]; then
echo usage: second parameter must be the folder to backup
exit
fi

FILENAME=$1
FILESTOCOMPRESS=$2/*
DESTINATION=~/Dropbox/Backup/[computername]
PASSWORD=[password]

7z a -mhe=on -mx=9 -p"$PASSWORD" ~/$FILENAME $FILESTOCOMPRESS
mv ~/$FILENAME $DESTINATION/$FILENAME
{% endhighlight %}

Note the use of the "-mhe=on" switch to encrypt the archive header, which includes the list of files in the archive.  And also the use of "-mx=9" to enforce the highest level of compression.

I also created another script which calls this one multiple times, once for each folder I want backed up.  I'm quite the shell script novice, so there are probably better ways to do this.  Perhaps with a function and by reading the filename and a list files to archive out of a text file.  I'll get around to it eventually (maybe).

Finally, I set up this script to run daily using Gnome Scheduler (a GUI frontend for cron).  Search "Gnome Scheduler" in the Ubuntu Software Center.  Here's a [nice overview](http://maketecheasier.com/easy-way-to-schedule-and-automate-tasks-in-ubuntu/2008/06/16) of the tool.  For those who wish to apply their command-line kung fu directly to cron and the crontab, [this page](https://help.ubuntu.com/community/CronHowto) from the Ubuntu Community Documentation may be of use.

There are some things to keep in mind with this backup option.  There are certainly more secure backup options available.  Although Dropbox uses high-end encryption when it stores your files on their servers, anyone with your Dropbox account password can access your files through the Dropbox website.  So your files are only as secure as your account password.  Adding a second level of encryption with 7zip is a step in the right direction, but of course you should be sure not to use the same password for 7zip encryption and for your Dropbox account.  All in all, though, this seems like a decent trade-off between security and ease-of-use.
