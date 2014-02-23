---
layout: post
title:  "Android Development - Starters Guide"
date:   2010-11-11 14:28:00
tags: android eclipse ubuntu
---

I'm giving Android development another shot, and had to install Eclipse and the Android Development Tools again. Note that this is all on a box running Ubuntu 10.4.

The [Android Developers](http://developer.android.com/) site is a plethora of information, including setup instructions, a developer guide and reference, videos, tutorials, etc. The following pages seem to be the most relevant when first getting started:

* [SDK Download and Quick Start](http://developer.android.com/sdk/index.html), which includes a to-the-point SDK Quick Start guide
* [Installing the SDK](http://developer.android.com/sdk/installing.html) is a more thorough version of the Quick Start guide, including next steps such as recommended reading and tutorials
* A [Hello, World](http://developer.android.com/resources/tutorials/hello-world.html) tutorial, the recommended first step for new developers
* A [Notepad](http://developer.android.com/resources/tutorials/notepad/index.html) tutorial, the recommended second step for new developers
* [Developer Resources](http://developer.android.com/resources/index.html) lists a few other tutorials that may be worth looking at

Here are the steps I took to prepare my development environment per the 'Installing the SDK' instructions:

1. I followed (and updated) my old post on [Setting up Eclipse and Android Development Tools in Ubuntu](http://tomeofunderstanding.blogspot.com/2010/01/setting-up-eclipse-with-android.html) to install the required Eclipse packages, and install the Android Development Tools plug-in for Eclipse. This covers steps 1 & 3 of the Quick Start / Installing the SDK guides.

2. For step 2 of the guides, installing the Android SDK, I downloaded the Linux platform SDK file from the [SDK download page](http://developer.android.com/sdk/index.html) and unpacked it from the terminal with 'tar xzvf [filename]'. I also added the SDK tools directory to my path, per instructions in the Installing the SDK guide.

3. For step 4 of the guides, I ran the GUI 'Android SDK and AVD Manager' by typing 'android' at the terminal (the 'android' executable is in the SDK 'tools' folder). In the 'Available Packages' section, I installed everything. At this time, it included the SDK Platform and Google API packages for Android versions 1.5 - 2.2, the Samples for SDK API 7 and 8 (Android 2.1 and 2.2), and the latest Documentation package.

Note, I've let Eclipse use it's default '~/workspace/' path as my workspace, and I've unpacked the Android SDK into a folder under '~/dev/'. Also, the "Android SDK and AVD Manager" can also be launched from within Eclipse by selecting "Window -&gt; Android SDK and AVD Manager". You must first tell it where to find the SDK by going to "Window -&gt; Preferences -&gt; Android".

From here I was able to successfully complete the "[Hello, World](http://developer.android.com/resources/tutorials/hello-world.html)" tutorial. Good luck, and happy coding!
