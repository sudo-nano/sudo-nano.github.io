---
layout: post
title: "Linux for Mere Mortals"
date: 2025-06-26 22:00:00 -0700
tags: linux right-to-repair
categories: drafts
hidden: true
--- 

If your technological journey has led you to wondering what the deal is with Linux, 
but it all seems like a bit too much to take in, this is for you.
If you're fed up with the alternatives (Windows or MacOS), but not sure where
to start with leaving them behind, this is also for you.


## Foreword on Accessibility
I won't hesitate to acknowledge that the Linux community (and to be honest, 
tech spaces in general) have a problem with being elitist. Many competent and
well meaning people have long since forgotten how hard it was to be a beginner.
Telling someone who's struggling that what they're doing is "obvious" will only
make them feel awful.
It's time we do better. 
This guide was constructed in an effort to make this tech more accessible
to the layperson. Everyone should be able to own their devices, and it
shouldn't take a computer science degree to do that.

## What will Linux do for me?
### Your computer gets faster for free! 
How is this possible? It's because Linux has less overhead than Windows or MacOS. 
Overhead, in this case, means programs that the operating system runs in the 
background. When you start up your PC, before you even open any programs, 
Windows runs a ton of background processes. It's normal to see background CPU
usage in the 10-20% range.[^1]
On Linux, your typical background CPU usage is under 5%. 
One major reason for this is telemetry. Telemetry is when your software
(in this case, the OS) "phones home" to the vendor's servers and tells
them what you're doing. If that sounds invasive, that's because it can
be. Telemetry ranges from relatively innocuous things like hardware specs
to much more personalized things such as what programs you're running
and what elements of the interface you're clicking on.

Windows and MacOS run extremely extensive telemetry. 
At the maximum Windows telemetry level, 
[crash reports include the memory of the process](https://www.zdnet.com/article/windows-10-telemetry-secrets/)
 at the time of the crash, which can include sensitive data. 
Linux, on the other hand, is capable of this level of telemetry, but will not 
enable it without your explicit consent.[^2]

![KDE Plasma Telemetry Slider]({{site.url}}/assets/linux/plasma_telemetry_slider.png)
*Figure 1: The slider for adjusting the level of telemetry in the KDE Plasma desktop
environment.*

### Installing programs is easier
The most important innovation that Linux brings to consumers is a **package manager**. 
Software is divided into different **packages**, and a package manager is a program
that provides a centralized way to install and remove software. Some package managers
are command line only, but distributions like Ubuntu and Fedora provide easy to use
graphical package managers. 
<!-- Write about how Ubuntu, Fedora, etc provide graphical package managers -->

On Windows, you might download an installer to install a program. 
Sometimes, these have boxes you have to uncheck to prevent the installer from 
installing additional garbage. (Looking at you, McAfee and Norton.)
On a package manager like `apt`, you might just run the command 
`apt install program`, then it installs. Easy as that, no "uncheck this box if you
don't want malware."

Uninstalling programs is easier as well. There's no tracking down the uninstaller
exe that may or may not have come with your program, and no tracking down
extraneous files in order to uninstall something. Your package manager will also
handle uninstalling for you. Continuing with the `apt` example, uninstalling
a program is as simple as `apt uninstall program`.

### Complete control over your computer
<!-- TODO: Research permission levels on linux -->
<!-- Use example: Candy crush installed with system privileges on Windows -->
You may have noticed that Windows keeps some things out of reach of even system
administrators. When I was poking around my Windows 10 install, I found that
without asking me, Windows had installed Candy Crush with *system privileges*. 
That means even with my administrator account, being the sole owner of the
computer, it wouldn't let me delete it. 

If Microsoft will take bribes from Candy Crush to forcibly install it on your
computer, is the operating system really yours? Linux will do no such thing.
Even if they did, root privileges give you full control over your computer.
You could have it removed in minutes.
There are no permissions higher than yours, and that's how it should be.

### No bullshit system requirements
Windows 10 is reaching its end of life in October 2025, and lots of those
devices don't meet the Windows 11 system requirements. The two big changes
they're making are that you must sign in with a Microsoft account, and your
device must support <abbr title="Trusted Platform Module">TPM</abbr> 2.0.[^TPM]
Tons of people are throwing out devices that don't support TPM 2.0, but they
don't have to be e-waste. Linux will let you install it on any device that has
the storage for it. 

Part of Microsoft's reasoning for requiring a TPM 2.0 is that the TPM stores
keys for full disk encryption, and stores biometrics for biometric login such
as facial recognition or fingerprint. Storing biometrics there is a good idea,
but pushing for 100% biometric support is, in all likelihood, a prerequisite for
mandatory biometric usage. That would be a grave and unprecedented privacy threat,
and without alternative operating systems, people would have no choice but to roll
over.
There are many ways to store disk encryption keys that don't require a TPM. Sometimes 
they're stored
on device but themselves encrypted with a password, sometimes they're stored
on an external USB drive that's required to decrypt your drive. The long
and short of it is that if you're not using biometrics, you probably don't
actually need a TPM. 


## Frequently Asked Questions
### Doesn't Linux produce weird and hard to troubleshoot problems?
The short answer is no. Linux doesn't produce weirder problems than other
operating systems, it's just that other OSes just try to hide the weird problems 
from you.

Microsoft and Apple don't want anyone except themselves touching the OS, so they don't
tell you how to work on your own system. Linux wants you to fix your own problems,
so the documentation tells you how to get your hands dirty. Every time you would
normally find yourself in a dead end on the Microsoft or Apple forums going back
and forth with a useless support representative, you can instead dig into problems
yourself. (No shade to support reps, they're just not equipped to do what they
actually need to.)
You can still choose not to work on your own system, but with all the new insights, 
you may find it hard to resist poking around.

The long answer is that some distributions, called **rolling release** distributions,
publish bleeding edge new packages to their package manager.
These packages are more up to date, but also not as thoroughly tested. Arch
is an example of a rolling release distribution. I would not recommmend Arch
or its derivatives for first time Linux users, because they're more prone 
to having rough edges and odd bugs.

**Stable release** distributions, like Debian, Ubuntu, and Mint, thoroughly
test their software before publishing it. This takes a while, so packages are
less up to date, but you're spared the weird issues. I would recommend starting
with a stable release distribution.

Additionally, you'll find that the available support is more useful, and *usually*
more friendly. Microsoft's support forums are littered with poor souls whose
cries go unanswered, or answered by hapless support representatives who are at
the mercy of their support script. With Linux, if you look up the exact error 
text of your problem, there's usually a forum thread where someone has already
solved it. If no solution exists yet, Linux forums are full of hard-working and
passionate volunteers who are happy to help you diagnose your problem. 

If you want to get started troubleshooting your own issues, you can start by
looking at `journalctl`. If you type this into your terminal, it will show you
extensive logs from all parts of your operating system. (You can press `Q` to exit.)
Normal `journalctl` is pretty overwhelming.
To see only the high priority logs, such as those emitted by crashing
programs, try `journalctl -p3`. It will also start you at the beginning of the log,
which could be months back. You can filter for just logs from the last time you started
your computer using the `-b` flag, short for "boot." Together, to see only high priority 
logs from the last boot, you use `journalctl -p3 -b`.

### Can I still play video games?
**Short answer:** Nearly all Steam games will run well out of the box.
Your mileage may vary with non-Steam games.

**Long Answer:** Most Steam games run under Proton, Steam's built-in emulator,
without any configuration.[^proton]
There's a wonderful website called [ProtonDB](https://www.protondb.com/)
where users will review games and rate how well they run under Proton. On the
rare occasion that they require setting launch options to start properly, 
someone on ProtonDB has probably already figured it out. Just copy and
paste the suggested options into the text box in Steam. 
[Valve outlines the steps to add launch options here.](https://help.steampowered.com/en/faqs/view/7D01-D2DD-D75E-2955)

Surprisingly, indie games are more likely to run on Linux. You'd think that large
studios would have the resources to develop for many operating systems, but most of them
are stuck in their ways, and use engines without Linux support. This is not necessarily
an age thing, since older Source engine games like Team Fortess 2 support Linux natively.
Factorio and Baldur's Gate 3 are popular non-AAA games with native Linux support. 
Visual novels made with RenPy, including many on itch.io, also support Linux natively.

### What is a desktop environment?
The desktop environment (sometimes abbreviated DE) is the graphical part of your operating system, basically
the system that makes the windows you click on. Desktop environments usually ship
their own set of basic utilities, such as your file manager and basic text editor.
If you're coming from Windows, these are equivalent File Explorer and Notepad.
Coming from MacOS, these would be Finder and TextEdit. The desktop environment
also controls your taskbar and notifications. 

Desktop environments come in a wide variety. On the light end is something
like XFCE, which is designed to be performant even on older computers. 
Some people find stock XFCE to be overly plain, but it can still be customized
to your liking. 

![A plain XFCE installation]({{site.url}}/assets/linux/xfce_1.jpg)
*Figure 2: A plain looking XFCE installation*

![A customized XFCE installation]({{site.url}}/assets/linux/xfce_2.jpg)
*Figure 3: A prettier and more customized XFCE installation with transparent terminal windows, shown inside a virtual machine under Windows*

The lightness of XFCE is one of the things that makes Linux Mint w/ XFCE a great
choice for breathing life into older computers.

<!-- TODO: Write about Gnome and KDE -->

### What the heck is a distribution?



## My Recommendations
Fedora with KDE is my best rec.
Debian and its derivatives are acceptable starter distributions, but I have
[ideological disagreements]({{site.url}}/posts/Btw-I-Use-Arch) with Debian's 
design philosophy.

## Appendix: Forum Etiquette
https://dontasktoask.com/
https://xyproblem.info


Outline: 
- Less overhead (your computer gets faster for free)
- Package managers 
- No bloatware 
- Escape from capitalism 
- Your system is yours (no constant UI changes just to make things shiny)\

## Footnotes
[^1]: Your mileage may vary depending on your CPU.
[^2]: The actual amount of telemetry and ease of configuration depends on your distribution. I use EndeavourOS with the KDE Plasma desktop environment, which gives me a nice labeled slider describing the different levels of telemetry I can allow. 
[^TPM]: The Trusted Platform Module (TPM for short) is a microcomputer separate from your main system, and it's used to enable security features such as full disk encryption and biometrics like fingerprint or face scanning.
[^proton]: Proton is technically not an emulator, it's a software translation layer. It doesn't emulate the entire Windows environment, it only translates the program's calls to Windows-specific tasks into Linux-specific tasks.
