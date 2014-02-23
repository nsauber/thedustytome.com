---
layout: post
title:  "Setting up Eclipse with Android Development Tools in Ubuntu"
date:   2010-01-16 19:27:00
tags: android app eclipse ubuntu
---

To get set up for Android App development, I'm following the instructions from Google [here](http://developer.android.com/sdk/installing.html).

I installed Eclipse through the Ubuntu Software Center (searched for "eclipse" and clicked install).

Also had to install eclipse-jdt (Java Development Tools) through the Synaptic Package Manager.

Also had to install eclipse-pdt (Plugin Development Tools) through Package Manager.

*(Edit 11/11/2010: When going through this process again with Ubuntu 10.4, I used the Ubuntu Software Center instead of the Synaptic Package Manager.  Also, I must have meant eclipse-pde - Plugin Development Environment, as I can't find eclipse-pdt listed as an available package.)*

Through Eclipses "Help -&gt; Install New Software" dialog, I had to add the basic software source for eclipse (don't know why this isn't set up by default) which is: `http://download.eclipse.org/releases/galileo/`

and install "WST Server Adapters" which is apparently a prerequisite for the ADT plugin.  Learned that from [this site](http://groups.google.com/group/android-developers/browse_thread/thread/1da899d34557f2e8?pli=1). 

Now to try installing the android plugin (ADT) by adding `https://dl-ssl.google.com/android/eclipse/` to the eclipse list of software sources.

Looks like that did it!  ADT is installed... (now what's next?)
