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
computer, is the operating system really yours?


## Addendum: Linux has an attitude problem 
I won't hesitate to acknowledge that the Linux community (and to be honest, 
computer science in general) has a problem with being elitist and/or ableist. 
The Linux community at large especially has an issue with looking down on noobs
or users of other operating systems. 
It's time we do better. We're all in it together, and we should act like it. 
This guide is constructed with existing attitudes in mind, and as an attempt 
at improving them. 

Outline: 
- Less overhead (your computer gets faster for free)
- Package managers 
- No bloatware 
- Escape from capitalism 
- Your system is yours (no constant UI changes just to make things shiny)\

## Footnotes
[^1]: Your mileage may vary depending on your CPU.
[^2]: The actual amount of telemetry and ease of configuration depends on your distribution. I use EndeavourOS with the KDE Plasma desktop environment, which gives me a nice labeled slider describing the different levels of telemetry I can allow.
