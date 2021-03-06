---
layout: post
title:  "Enabling DVD Playback in Ubuntu"
date:   2011-02-12 16:48:00
tags: dvd systemadministration ubuntu vlc
---

Surprisingly, I've never done this before, but I needed to enable DVD playback on my wife's new netbook which she uses for her work. While I was at it, I also enabled it on my new laptop.  We're both running Ubuntu 10.10 and loving it.

Because of Ubuntu's commitment to free / open-source software (and because of some licensing concerns), Ubuntu doesn't ship with the libraries to play mp3s, DVDs, or some other media formats. They are, however, freely (as in beer) available through the package manager / Software Center. Here's what I did to enable DVD playback:

1. Installed Ubuntu Restricted Extras from the Software Center (ubuntu-restricted-extras if installing using apt or Synaptic).
2. Verified in the Software Center that 'libdvdread4' was installed (it was for me, but you should install it if it's not).
3. Ran the following command from a terminal to install the restricted DVD decryption codec (thanks to the [Ubuntu Help site](https://help.ubuntu.com/community/RestrictedFormats/PlayingDVDs) for this): `sudo /usr/share/doc/libdvdread4/install-css.sh`
4. Installed 'VLC Media Player' via the Software Center. This may not be required, but Totem (Movie Player) crashed a few seconds into playing a dvd before doing this. After installing VLC, both VLC and Totem played the DVD fine. There are probably some codecs installed along with VLC that fixed the problem.

There it is. Both laptops are playing DVDs without any errors.
