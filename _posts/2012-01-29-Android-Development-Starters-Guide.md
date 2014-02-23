---
layout: post
title:  "Android Development - Starters Guide (Updated for Android 4.0)"
date:   2012-01-29 11:12:00
tags: android app development ubuntu
---

First things first, major appreciation goes out to Lars Vogel for his [incredibly helpful tutorial](http://www.vogella.de/articles/Android/article.html) on Android development. The [last time](http://thedustytome.blogspot.com/2010/11/android-development-starters-guide.html) I tinkered with all this, the best (only) online resources available were on the official [Android Developers](href="http://developer.android.com/) site, which is a great reference site, but didn't provide the clearest guidance to get you up and running quickly. If you're here to get started with Android Development for the first time, save yourself some headaches and head straight over to Lars' tutorial. Thanks Lars!

Second, the folks at Google have simplified the initial setup and installation process. No more mucking around to download and install the SDK, then install Eclipse and install the APK plug-in, then tell the APK where your SDK is... all these dependencies can be installed for you from inside Eclipse now, and that awkward SDK configuration is handled for you. So thanks Google!

So, here are the steps I took to set up my Android development environment. FYI, I'm working in a VirtualBox VM with a sparkly fresh copy of Ubuntu 11.10.

* First, open the Ubuntu Software Center, search for "eclipse", and install the Eclipse Integrated Development Environment. (No need to install eclipse-jdt separately anymore, Ubuntu apparently gives it to you automatically now. Yay!) Note that it might take a while to download and install.
* When it's done installing, launch Eclipse.
* Use Eclipse's Update Manager (Help -&gt; Install New Software...) to install the Android Development Toolkit plug-in.
    * First, be sure to add the software site for the version of Eclipse that you're using (in my case, it was [http://download.eclipse.org/releases/indigo/](http://download.eclipse.org/releases/indigo/)). Otherwise Eclipse won't be able to resolve dependencies when installing the ADT plug-in. I don't know why this isn't added by default, but it always trips me up.
    * Next add Google's ADT software site ([https://dl-ssl.google.com/android/eclipse/](https://dl-ssl.google.com/android/eclipse/)).
    * Working with the Google software site, select the "Developer Tools" item and it's four sub-items.
    * Click Next, and after Eclipse did some calculating, click Next again to confirm that you want to install the items you selected.
    * Then accept a couple of license agreements, and click Finish.
    * Eclipse will popp up a progress dialog, and do its download and install magic.
        *Note that in the middle of this step, I got a warning prompt asking me to confirm that I want to install unsigned content. Clicking "Details" revealed that it's Google's ADT components making Eclipse a little nervous. I clicked OK and didn't look back.
    * When the installation completes, Eclipse should prompt me to restart (Eclipse, not the whole computer), which you should do.
* After Eclipse restarts, it should prompt you to configure a copy of the Android SDK that it can use.
    * I opted to let it install a new copy of the Android SDK, and chose to install the "latest available version" (4.0.3 at the time I'm doing this). I left the default install location.
    * Clicking Next will lead to being prompted to let Google gather anonymous usage statistics on the SDK (your choice).
    * After a little bit of Eclipse progress-bar action, you should be prompted to Accept all of the SDK packages you wanted installed.
    * Then the Android SDK Manager will take over, showing a progress bar while it downloads and installs the SDK.
    * Note that only some of the SDK components are installed during this step. It's enough so you can write and release an app, but there are other components for each API version that you'll also want.
* In order to install ALL the components for a particular API version, you'll want to select them yourself in the Android SDK Manager.
    * In Eclipse, Window -&gt; Android SDK Manager
    * Under the Packages section, check the box next to any entry or sub-entry that you want to install. I recommend just checking the box for each version of Android that you want to target, and let it auto-check all of it's sub-entries.
    * Then click Install, and wait...
    * ...and wait...
    * ...and maybe put on a TV show until it finishes downloading and installing.

From here, I should be good to create a new android project. But that's for another day...
