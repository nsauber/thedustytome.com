---
layout: post
title:  "Fixing Android ADT After Upgrade to Ubuntu 10.10"
date:   2010-11-21 07:53:00
tags: android development eclipse ubuntu
---

After upgrading from Ubuntu 10.4 to Ubuntu 10.10, I found that the Android ADT plug-in was not showing up in Eclipse anymore. None of the features were accessible from the Eclipse menus. The "Help -&gt; Install New Software..." dialog would hide the packages when "Hide items that are already installed" was checked, and attempting to re-install gave an "already installed" error message.

Some googling uncovered others with this problem, particularly <a href="http://sonalsantan.blogspot.com/2010/10/eclipse-adt-plugin-on-ubuntu-1010-after.html">this helpful post</a> from Sonal. The fix is, basically, to delete the entire configuration directory for eclipse. While a bit heavy-handed for those with complex installations and many installed components, it was fine for me as all I'm doing is Android development. My steps were slightly different from Sonal's, so here's a recap:

1. Exit eclipse if running
1. Delete (or backup) `~/.eclipse/org.eclipse.platform_3.5.0_155965261`
1. Start eclipse
1. Open Help -&gt; Install New Software
1. Add the Eclipse 3.5 Default update site: [http://download.eclipse.org/releases/galileo/](http://download.eclipse.org/releases/galileo/) (Note that I explicitly installed the WST Server Adapters, though adding the update site may be enough.)
1. Add the GEF (Graphical Editor Framework) plugin update site: [http://download.eclipse.org/tools/gef/updates/releases](http://download.eclipse.org/tools/gef/updates/releases) (I did not explicitly install GEF.)
1. Add the Google Android ADT plugin update site: [https://dl-ssl.google.com/android/eclipse](https://dl-ssl.google.com/android/eclipse)
1. Install the "Android DDMS" and "Android Development Tools" packages from the Android ADT update site.

Notably, the GEF plugin appears to be new.  I don't recall installing this under Ubuntu 10.4. Also, I believe that if you just add the update sites for the dependancies (WST Server Adapters and GEF), they will be installed automatically when you install the Android ADT packages. No need to hunt them down and install them directly. I haven't verified this though.

There may be more re-configuration to be done. I'll update this post with anything I find as it comes up.
