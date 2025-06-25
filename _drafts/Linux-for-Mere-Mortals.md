---
layout: post
title: "Linux for Mere Mortals"
date: 2024-01-26 22:00:00 -0700
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
It's time we do better. We're all in it together, and we should act like it. 
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

### Installing programs is easier
The most important innovation that Linux brings to consumers is a **package manager**. 
Software is divided into different **packages**, and a package manager is a program
that provides a centralized way to install and remove software. While most package
managers are command line only, and the command line can be scary, package managers
are uncomplicated. 
<!-- Write about how Ubuntu, Fedora, etc provide graphical package managers -->

On Windows, you might download a graphical installer to install a program. 
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

### Control over your computer
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


## Frequently Asked Questions
### Doesn't Linux produce weird and hard to troubleshoot problems?
The short answer is no, Windows just tries to hide the weird problems from you.

Microsoft doesn't want anyone except themselves touching the OS, so they don't
tell you how to work on your own system. Linux wants you to fix your own problems,
so the documentation tells you how to get your hands dirty.
You can still choose not to work on your own system, but with all the new insights
into the problems, you may find it hard to resist poking around.

The long answer is that some distributions, called **rolling release** distributions,
publish bleeding edge new packages to their package manager.
These packages are more up to date, but also not as thoroughly tested. Arch
is an example of a rolling release distribution. I would not recommmend Arch
or its derivatives for first time Linux users. 
**Stable release** distributions, like Debian, Ubuntu, and Mint, thoroughly
test their software before publishing it. This takes a while, so packages are
less up to date, but you're spared the weird issues. I would recommend starting
with a stable release

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
programs, try `journalctl -p3`.

### Can I still play video games?
**Short answer:** Steam has a built-in emulator[^proton] called Proton that will let
you run the vast majority of Windows games on Linux with the click of a single
checkbox. Valve claims that proton will work with non-Steam games, but this 
requires more setup and your mileage may vary. 

**Long Answer:** Most Steam games run under Proton without any configuration.
There's a wonderful website called [ProtonDB](https://www.protondb.com/)
where users will review games and rate how well they run under Proton. On the
rare occasion that they require setting launch options to start properly, 
someone on ProtonDB has probably already figured it out. Just copy and
paste the suggested options into the text box in Steam. 
[Valve outlines the steps to add launch options here.](https://help.steampowered.com/en/faqs/view/7D01-D2DD-D75E-2955)




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
<!-- TODO: Move the telemetry footnote to body text and add a screenshot of the slider -->
