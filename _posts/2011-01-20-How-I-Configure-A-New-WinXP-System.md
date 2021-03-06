---
layout: post
title:  "How I Configure A New WinXP System"
date:   2011-01-20 17:35:00
tags: windowsxp
---

I've just finished created a new WinXP VM in which I plan to do some .NET development.  Since I was getting the system to a customized/workable state from essentially a clean installation, I thought I'd capture the typical tweaks I make when I start work on a new machine.

Typically, I prefer the cleaner (and more compact) "Windows Classic Style" over the "Windows XP Style", though on occasion I've used a tool to enable skinning of the WinXP UI. The windowing style can be set in the Display Properties dialog (right-click on the desktop -&gt; Preferences), on the Appearance tab, via the 'Windows and buttons' pick-list.

I prefer to darken the standard light-grey window coloring.  On the Appearance tab, click the Advanced button in the bottom-right.  Then click on the OK button in the example window to set the Item picklist to "3D Objects".  Pull down the "Color 1" color selector and choose 'Other' so you can set the RGB values to Red: 155, Green: 147, Blue: 128.

For the desktop background, I can usually find something on [DeviantArt](http://browse.deviantart.com/customization/wallpaper/), or I might just go for a clean, solid color.  Either way, it's set on the 'Desktop' tab of the Display Properties dialog.  Some decent solid colors are:

* Green (R:25 G:70 B:25)
* Blue (R:0 G:67 B:128)
* Grey (R:73 G:73 B:73)
* VS2010 Blue-Grey (R:41 G:57 B:85)

Also, ClearType font smoothing is a must!  Microsoft has an [online setup wizard](http://www.microsoft.com/typography/cleartype/tuner/Step1.aspx) to turn this on (you'll have to install the ActiveX component).

While we're on fonts, I'm a huge fan of the Consolas font for any monospaced text editing (programming, notepad, the command prompt).  You can download the Consolas Font Pack [here](http://www.microsoft.com/downloads/en/details.aspx?familyid=22e69ae4-7e40-4807-8a86-b3d36fab68d3&amp;displaylang=en).  Though it says it's only for uses of Visual Studio 2005 or 2008, I was able to install it without a hitch.

In the QuickLaunch bar, I typically keep three icons visible, with the '&gt;&gt;' popup list for any others I may want.  The three are:

1. A shortcut to 'My Documents' (more on this later)
1. Chrome (or Firefox, or IE if I'm in a locked-down ecosystem)
1. The "Show Desktop" link

For the 'My Documents' shortcut, I actually use a modified shortcut to Windows Explorer, as I prefer to have the Explorer 'Fodlers' sidebar open by default.  The modifications are probably overkill, but I like it "just right".  ;-)  To create the shortcut, I copy the Windows Explorer shortcut from the Start menu (Start -&gt; All Programs -&gt; Accessories) and edit it (right-click -&gt; Properties) to the desktop.  On the 'General' tab, I change the name to 'My Documents'.  On the 'Shortcut' tab, I change the "Run" picklist to 'Maximized' and change the Icon to match the normal My Documents icon (in 'C:\WINDOWS\system32\mydocs.dll').  Then just drag this shortcut from the desktop to the Quick Launch bar.

I also tweak the layout and options in Windows Explorer a bit.  The navigation buttons toolbar gets changed to use small icons (right-click on it -&gt; Customize -&gt; change 'Icon options' to 'Small icons').  The menu, address, and navigation button toolbars are all dragged to all be on the same line across (navigation on far left, menu on far right, address filling the space in the middle).  The Views drop-down is changed to Details.   I also turn on the Status Bar (View -&gt; Status Bar).  Next, I go to Tools -&gt; Folder Options, to the 'View' tab and click "Apply to All Folders" so these settings stick as I navigate around.   In the View tab Advanced Settings list, I do the following:

* Select "Show hidden files and folders"
* Uncheck "Hide extensions for known file types"

As far as programs to install, here's a breakdown:

* [Launchy](http://www.launchy.net/) - I can't live without this anymore!
* [Chrome](http://www.google.com/chrome) (or [Firefox](http://www.mozilla.com/en-US/firefox/) as a backup)
* [WinLayout](http://code.google.com/p/winlayout/) for window positioning/resizing at a keystroke.
* [Notepad++](http://notepad-plus-plus.org/)

Launchy gets a little extra setup.  In Launchy's Options (right-click on the system tray icon), on the General tab, check "Hide Launchy when it loses focus" and "Always on top", and change the hotkey combination to Control + Space.  On the Skins tab, change the skin to "Spotlight Wide".  On the Catalog tab, I'll add a custom folder (like "MyDocs\util\Shortcuts\") set to index "*.lnk" files, where I can throw any shortcut I want to be launchable.

Alright, that's all I can think of for now.  I'll try to keep this updated as I think of further customizations.
