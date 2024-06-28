---
layout: post
title: "Btw I Use Arch"
date: 2024-03-27 19:35:00 -0700
tags: linux software opinion apt yay
category: My Software Stack
--- 
This post is intended for an audience that is familiar with the basic differences 
between various Linux distributions, such as stable release vs rolling release. 
In the interest of brevity, this post uses some amount of Linux-related jargon that
will not be explained but is highly google-able. 

## Stable-Release Distro Problems
Just this week, I replaced my desktop computer's diseased frankenstein installation 
of Linux Mint 21.1[^1] with EndeavourOS, an arch-based distribution. 
Having used only Debian-based Linux distributions 
for all of my 7 years using Linux in some capacity, I have become familiar with 
their benefits and their shortcomings. The deal-breaker for me is the inflexibility 
of stable release distributions and the Debian philosophy.

Over the years, I've regularly run into situations where the latest release of some 
open source software will not run or possibly even compile, because the latest libraries 
shipped in my distro's official repositories are ancient. While it's definitely *possible*
to manually install newer libraries, if 
you have system software that relies on those libraries being a specific version, 
you risk breaking them and thus your OS. I've done this several times by making 
the foolish mistake of trying to upgrade my system C libraries manually. 

Quoth Tumblr user clitfisto on the infamous [battery acid spaghetti post](https://www.tumblr.com/babblingbranches/669570171962327040), "don't do this."[^2] 

If you're not going to manually upgrade libraries, your only option is to wait months
for newer versions to be pushed to official Debian repositories. Possibly longer
if you're on Ubuntu, Mint, or some other Debian derivative. Worse, the 
[Debian wiki page on how to not break Debian](https://wiki.debian.org/DontBreakDebian)
effectively says that building from source is the only safe way to install software 
not included in the official repositories. "Safe", in this case, means unlikely 
to cause issues (present or future) or incur technical debt. This is because Debian 
has no way to ensure that 3rd party packages don't conflict with official packages. 
Arch avoids the outdated libraries issue by being a rolling release distribution, and
handles the conflict issue by letting the `yay` package manager handle both official
packages (via `pacman`) and unofficial packages (via AUR). 

In short, I have fundamental disagreements with the Debian philosophy on how to 
use your own operating system. I didn't even know about the "Don't Break Debian" 
page until my friend [Tucker R. Twomey](https://tucker.the-twomeys.com/blog/) showed
it to me last week, but it was illuminating as to why all of my machines using Debian
based distributions seemed to accrue technical debt until they collapsed under their
own weight. It's because I wasn't using Debian the way it's intended.

Above all, I would like to emphasize that this is *not* a "Debian is bad" post. 
Debian is not intended to safely do what I want, which is install 3rd party
software willy-nilly. 


## EndeavourOS to the Rescue
Right off the bat, several things were easier on EndeavourOS. Managing software 
is much improved by the fact that `yay` can handle both official packages and AUR
packages. Endeavour comes with KDE, which is pretty and comes with lots of QoL features. 
(KTimer's ability to defer alarms for a customizable amount of time, and KCalc's 
ability to switch between hexadecimal/decimal/octal/binary easily is great.) You 
get the benefits of Arch with a lot less hassle, because it comes with an easy graphical
installer and sensible defaults. 

Several ongoing quality-of-life issues are fixed.
1. **`apt` has no clean way to handle 3rd party repository keys.** Since `apt-key` is
deprecated, [the recommended method](https://itsfoss.com/apt-key-deprecated/) 
is to manually download them to 
`/usr/share/keyring/insert_name.gpg` and then add that location to the appropriate 
line in your `/etc/apt/sources.list`. It's a hassle, and I think computers should
be better than this. On Endeavour, `yay` handles 3rd party repository keys with
no hassle at all. 

2. ~~**I can fix the cursed issue with Gigabyte B550 motherboards.** There's an issue with 
Gigabyte B550 motherboards where the GPP0 bridge will wake the computer up mere 
seconds after going to sleep, preventing it from sleeping. 
[The solution to this problem](https://www.reddit.com/r/gigabyte/comments/p5ewjn/b550i_pro_ax_f13_bios_sleep_issue_on_linux/), when implemented on my Mint install, 
caused a secondary issue where the screen would black out for a second every time
I moved my mouse. This secondary issue is no longer present on the clean Endeavour
install.~~ 
Edit 2024-04-14: The secondary issue was actually a monitor issue. It was caused
by my ViewSonic portable monitor being a piece of garbage, and fixed by 
obtaining a better monitor.

3. My display refresh rate no longer reverts to 60 Hz every time I reboot. 
This may be a nonissue for people who use 60 Hz monitors, but I enjoy video 
games and use a 144 Hz monitor. 

So far, there have been no regressions from my Mint install or complaints about Endeavour. Seeing as
I've only been using it for a few days, thorough assessment has yet to be done. 
My initial impression is that it feels like the cute and easy experience that Mint
tries to be. 



Thanks for reading. Send any questions to @themagicalc on Discord. I have a post 
in the works called "Linux for Mere Mortals", which will be a guide to Linux for 
those who are not technical but are ready to move on from Windows or MacOS. If you
have things you want to see in this series, send them my way.

## Footnotes
[^1]: My previous setup was Mint 21.1 with KDE and with Linux kernel 6.1.0 kludged in as an attempted (unsuccessful) fix for the suspend issue before I had figured out the true root cause. 

[^2]: This broke my operating system both times I tried it. Keep regular backups, or else. 
