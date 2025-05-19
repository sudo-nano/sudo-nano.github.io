---
layout: post
title: "Linux for Mere Mortals"
date: 2024-01-26 22:00:00 -0700
tags: linux right-to-repair
categories: drafts
hidden: true
--- 

If your technological journey has led you to wondering what the deal is with Linux, 
but it all seems like a bit too much to take in, this is for you. Alternatively, 
if you're fed up with the alternatives (Windows or MacOS), but not sure where
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

Windows and MacOS run extremely extensive telemetry, almost all of which is
intentionally difficult to disable. <!-- Citation Needed -->
Linux, on the other hand, runs little to no telemetry, and the amount that it
runs is often easily user-configurable.[^2]

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



## Frequently Asked Questions
### Doesn't Linux produce weird and hard to troubleshoot problems?
The short answer is no, Windows just tries to hide the weird problems from you.
Microsoft doesn't want anyone except themselves touching the OS, so they don't
tell you how to work on your own system. Linux wants you to fix your own problems,
so the documentation tells you how to get your hands dirty.
You can still choose not to work on your own system, but with all the new insights
into the problems, you may find it hard to resist poking around.

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
<!-- TODO: Move the telemetry footnote to body text and add a screenshot of the slider -->
