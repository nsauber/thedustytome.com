---
layout: post
title:  "Configuring Ubuntu to Auto-Mount an NTFS Partition on Boot"
date:   2011-01-24 16:02:00
tags: systemadministration ubuntu
---

I have a partition on a second internal hard drive that I use for media storage.  Ubuntu is smart enough to detect it's existence and add a link in the Places menu to mount and open this partition, however I'd like to have it mounted automatically on boot so it can be accessible to my online backup software.  I also want to make sure it maintains it's entry in the Places menu, so I can access it as easily as I currently do.

There are two administration utilities I used to accomplish this:

1. NTFS Configuration Tool (ntfs-config)
2. Storage Device Manager (pysdm)

Both utilities are GUI tools for modifying the '/etc/fstab' file, which defines the file-system table configuration.  Both can be found in the Ubuntu Software Center, or can be installed from the command-line with apt-get (package names are in parenthesis).  Once installed, both can be launched from the System -&gt; Administration menu, as of Ubuntu 10.10.

The NTFS Configuration Tool is obviously focused on NTFS partitions, so it's not a general-purpose 'fstab' configuration tool.  Before launching, make sure you don't have any partitions mounted or it may be unable to detect them properly.  When launched, it will detect any new NTFS partitions (meaning ones that don't have entries in 'fstab') and ask if you want to configure them.  When this happens, make sure that only the partitions you want to be auto-mounted are checked!  Then click OK to add an entry for the checked drive to 'fstab', or you can click Cancel if you don't want any to add any new entries to 'fstab'.  This leaves you at the main NTFS Configuration Tool window.  If you open up Advanced Configuration, you'll see an entry for any of the partitions you just selected.  You may need to check the 'Writable' box next to your new entries.  From here you can Close the utility.  Your selected partitions will be mounted automatically on boot, and they will still be listed in the Places menu!  If you accidentally configured a partition, or want to remove a previous entry, you'll have to fix that with the Storage Device Manager.

The Storage Device Manager is a GUI front-end to modifying any 'fstab' entry, not just for NTFS partitions.  When launched, you can select a partition to configure from the Partition List on the left side.  If a partition does not have an entry in the 'fstab' file, you'll get a message box saying it hasn't been configured and asking if you want to configure it now.  If you load this before running the NTFS Configuration Tool, then it should prompt you when you choose any of the unconfigured drives.  If you need to remove an entry that you added with the NTFS Configuration Tool, you can do that here (be sure to Unmount first if applicable).

The only other thing I'd like to tweak would be to not have the mounted partitions display a desktop icon (I like my desktop as clean as possible), but I can live with it for now.  And it's probably possible to use the Storage Device Manager to do all this (and of course I could just learn to edit the 'fstab' manually), but I haven't figured that out yet.
