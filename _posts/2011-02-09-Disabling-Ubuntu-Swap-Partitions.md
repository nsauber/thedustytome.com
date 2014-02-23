---
layout: post
title:  "Disabling Ubuntu Swap Partitions"
date:   2011-02-09 19:51:00
tags: systemadministration ubuntu
---

When installing Ubuntu on my wife's new netbook, the installation crashed mid-way through... after it reworked the partition table and added the ext3 and swap partitions.  Some trial and error showed that Ubuntu had trouble recognizing the intended partitions when choosing to install alongside Windows again (it tried to cram everything into the space held by the shrunken Windows partition).  So in order to get the partitions back to where they were, I tried to delete the new ext3 and swap partitions.  Unfortunately, when booting to the Ubuntu Live USB stick, it mounted the swap partition on the main hard drive and prevented me from deleting it!  Some googling showed me that I could force-disable all swap partitions via the command-line:

{% highlight console %}
sudo swapoff -a
{% endhighlight %}

When running as the Live disk's default 'ubuntu' user, there is no password so there's no password prompt.
