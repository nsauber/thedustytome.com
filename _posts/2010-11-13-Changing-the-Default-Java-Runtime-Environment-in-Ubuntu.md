---
layout: post
title:  "Changing the Default Java Runtime Environment in Ubuntu"
date:   2010-11-13 19:50:00
tags: java ubuntu
---

I've been having trouble with a couple Java programs in Ubuntu, so I'm attempting to switch the Java Runtime Environment from the OpenJDK, which is default in Ubuntu, to the official Sun runtime. I found [instructions](http://www.ubuntugeek.com/how-install-sun-java-runtime-environment-jre-in-ubuntu-10-04-lucid-lynx.html), which I've followed with the following changes:

* The partner repository was added through the GUI Software Sources utility (System menu -&gt; Administration -&gt; Software Sources, or from the Ubuntu Software Center, Edit -&gt; Software Sources)

* The sun-java6-jre and sun-java6-fonts packages were installed by searching in the "Canonical Partners" section of the Ubuntu Software Store. The sun-java6-plugin package was not found and not installed.

Here's hoping things improve, and that there are no problems because of not installing the plugin package.
