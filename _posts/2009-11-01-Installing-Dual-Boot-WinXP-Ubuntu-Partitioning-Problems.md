---
layout: post
title:  "Installing Dual-Boot WinXP/Ubuntu - Partitioning Problems"
date:   2009-11-01 08:01:00
tags: ubuntu
---

I recently received my new 1TB hard drive (more storage than I've ever had!).  I'm hoping to switch to Ubuntu as my main day-to-day OS, but I still want to keep an XP install around for games and other needs, so a dual-boot setup was in order.  I've set this up before on other machines, but it's been a while and I'd obviously forgotten a few things.  This post is an attempt to capture the process for future reference, so I won't repeat this yet again in the future.

The first step was to partition my new 1TB hard drive.  I used the partition manager on a [slipstream](http://lifehacker.com/386526/slipstream-service-pack-3-into-your-windows-xp-installation-cd) WinXP cd to create the following partitions:

* 2GB NTFS for Windows virtual memory file
* 2GB Linux Swap
* 50GB NTFS for Windows System
* 350GB Ext4 for Ubuntu
* 100GB NTFS for Windows program installs
* 450GB NTFS for shared media

Obviously I only sized the two Linux partitions here since XP doesn't know about Linux Swap or Ext4.  After installing Windows to the 50GB NTFS partition, I booted into Windows to be sure everything was working.  It was.  Next I popped in the fresh and shiny burned Ubuntu 9.10 disc and installed to the 350GB partition.  Install went fine, and after rebooting I was presented with a Grub prompt asking which system I'd like to load.  I chose Ubuntu, and it loaded fine.  I then rebooted, chose Windows XP at the Grub prompt, and was presented with the following error:

> Windows could not start because the following file is missing or corrupt: <Windows root>\system\hal.dll

I started to get this vague feeling like I'd been here before... After a bit of googling (booting back into Ubuntu), I remembered that WinXP needs to be installed on a primary partition.  Check [here](http://www.pcguide.com/ref/hdd/file/structPartitions-c.html) for a primer in primary, extended, and logical partitions.  Apparently, the XP install disk's partition manager creates the first new partition as a primary, and any partitions created after that are added as logical partitions on a single extended partition.  So my partition table looked like this:

* [primary] 2GB NTFS for Windows virtual memory file
* [extended]
    * [logical] 2GB Linux Swap
    * [logical] 50GB NTFS for Windows System
    * [logical] 350GB Ext4 for Ubuntu
    * [logical] 100GB NTFS for Windows program installs
    * [logical] 450GB NTFS for shared media

Obviously the Windows System partition wasn't primary.  So somehow, before installing Ubuntu, Windows was able to load from the 50GB logical partition, but this was broken by some change made during the Ubuntu install (Grub?).

Anyway, I decided to rework my partitions as follows:

* [primary] 50GB NTFS for Windows System
* [extended]
    * [logical] 2GB Linux Swap
    * [logical] 350GB Ext4 for Ubuntu
    * [logical] 100GB NTFS for Windows program installs
    * [logical] 450GB NTFS for shared media

I used the WinXP slipstream disk to wipe out my partition table and recreate it using these partitions.  After installing XP and Ubuntu, I'm now able to boot into either OS without a problem.  Phew!
