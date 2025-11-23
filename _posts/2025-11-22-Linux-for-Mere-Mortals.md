---
layout: post
title: "Linux for Mere Mortals"
date: 2025-11-22 20:52:00 -0700
tags: linux right-to-repair
--- 

With the Windows 10 end-of-life happening on October 14th, and Windows 11 being
transparently awful for just about everyone, lots of people are wondering what alternative
there is. Continuing to run Windows 10 puts you at risk, because there will no longer be
security updates, but inviting in Windows Recall and the rest of Windows 11's spyware 
is hard to stomach. Switching to Linux is one option, and this guide is about evaluating
whether it's right for you. 

## Foreword
### Accessibility Statement
I won't hesitate to acknowledge that the Linux community (and to be honest, 
tech spaces in general) have a problem with being elitist. Many competent and
well meaning people have long since forgotten how hard it was to be a beginner.
Less well-meaning people view tech competence as superiority, something to lord over
others rather than a shared goal. People who gatekeep technical spaces are holding back
the technological literacy of the entire population. 
This guide was constructed in an effort to make this tech more accessible
to the layperson. Everyone should be able to own their devices, and it
shouldn't take a computer science degree to do that. At the same time, the layperson
still needs more tech literacy than ever, and there's no way around that. The best 
we can do is welcome and teach newcomers.

### Is Linux right for you? 
Let me say right out the gate that *this guide is not for me to prosetylize Linux.* 
Some people are of the opinion that everyone should switch to Linux, and I just don't
think that's true, no matter how much I wish it were. Whether Linux will work for you 
depends on what you demand of your computer. If you need Windows-specific sofware
that won't run under a compatibility tool like Wine or Proton, you're just SOL 
and have to use Windows. Only you can evaluate for sure whether using Linux will be worth
the work. 


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
A **package** is a single piece of software, and a package manager is a program
that provides a centralized way to install and remove software. Some package managers
are command line only, but distributions like Ubuntu and Fedora provide easy to use
graphical package managers. 

On Windows, you might download an installer to install a program. You have to search the 
internet, avoid malicious pages pretending to be the real download page, and
even avoid fake download buttons on the real download page. 
The installer might  have boxes you have to uncheck to prevent it from
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
One of the big issues with the Windows 10 EoL is that many perfectly functional devices
don't meet Windows 11 system requirements. The two big changes
they're making are that you must sign in with a Microsoft account, and your
device must support <abbr title="Trusted Platform Module">TPM</abbr> 2.0.[^TPM]
Tons of people are throwing out devices that don't support TPM 2.0, but they
don't have to be e-waste. Linux will let you install it on any device that has
the storage for it. 

![A meme about system requirements]({{site.url}}/assets/linux/system_requirements_meme.png)
*Figure 2: A meme about system requirements. A bear peering at the camera labeled Windows 11 says "Must have TPM 2.0, intel 8k or better, Ryzen 3k or better." A deranged wolf looking into the camera labeled "Linux" says "You need a CPU (optional)."*

Part of 
[Microsoft's reasoning](https://techcommunity.microsoft.com/blog/windows-itpro-blog/tpm-2-0-%E2%80%93-a-necessity-for-a-secure-and-future-proof-windows-11/4339066) 
for requiring a TPM 2.0 is that the TPM stores
keys for full disk encryption, and stores biometrics for biometric login such
as facial recognition or fingerprint. The security benefits of using a TPM 2.0 are real, 
but preventing people from running the OS without one suggests that more is at play. 
Pushing for 100% biometric support is, in all likelihood, a prerequisite for
mandatory biometric usage. That would be a grave and unprecedented privacy threat,
and without alternative operating systems, people would have no choice but to roll
over. Additionally, prematurely turning millions of devices into e-waste is clearly
generating more profits for their partners, so Microsoft has a 
[perverse incentive](https://en.wikipedia.org/wiki/Perverse_incentive)
here. 

There are many ways to store disk encryption keys that don't require a TPM. 
Sometimes they're stored
on device but themselves encrypted with a password, sometimes they're stored
on an external USB drive that's required to decrypt your drive. The long
and short of it is that if you're not using biometrics, you probably don't
actually need a TPM. Microsoft should not be requiring a TPM to use their operating system,
only to use the features that utilize one. 


## Frequently Asked Questions
### Can I still play video games?
**Short answer:** Nearly all Steam games will run well out of the box.
Your mileage may vary with non-Steam games.

**Long Answer:** Most Steam games run under Proton, Steam's built-in emulator,
without any configuration.[^proton] Some require minor tweaks. 
There's a wonderful website called [ProtonDB](https://www.protondb.com/)
where users will review games and rate how well they run under Proton. You can check
the compatibility of your favorite games here, and use that to inform whether you want 
to make the switch. On the
rare occasion that they require setting launch options to start properly, 
someone on ProtonDB has probably already figured it out. Just copy and
paste the suggested options into the text box in Steam. 
[Valve outlines the steps to add launch options here.](https://help.steampowered.com/en/faqs/view/7D01-D2DD-D75E-2955)
You can even filter by hardware to look for performance reviews and troubleshooting tips
from people running the same hardware as you.

Surprisingly, indie games are more likely to run on Linux. You'd think that large
studios would have the resources to develop for many operating systems, but most of them
are stuck in their ways, and use custom engines or legacy code without Linux support. 
This is not necessarily
an age thing, since older Source engine games like Team Fortess 2 support Linux natively.
Factorio and Baldur's Gate 3 are popular non-AAA games with native Linux support. 
Visual novels made with the RenPy toolkit, including many on itch.io, also support Linux 
natively.

### What is a desktop environment?
You might have heard Linux users debating the merits of one desktop environment or another.
The desktop environment (sometimes abbreviated DE) is the graphical part of your operating 
system. It's
the program that renders the windows you click on, and controls things like your taskbar
and window behavior. Desktop environments usually ship
their own set of basic utilities, such as your file manager and basic text editor.
If you're coming from Windows, these are equivalent File Explorer and Notepad.
Coming from MacOS, these would be Finder and TextEdit.

DEs come in all shapes and sizes. On the light end is something
like XFCE, which is designed to be performant even on older computers. 
Some people find stock XFCE to be overly plain, but it can still be customized
to your liking. 

![A plain XFCE installation]({{site.url}}/assets/linux/xfce_1.jpg)
*Figure 3: A plain looking XFCE installation*

![A customized XFCE installation]({{site.url}}/assets/linux/xfce_2.jpg)
*Figure 4: A prettier and more customized XFCE installation with transparent terminal windows*

The lightness of XFCE is one of the things that makes Linux Mint w/ XFCE a great
choice for breathing life into older computers.

GNOME is a desktop environment that comes default on Debian and Ubuntu, and is available
for Fedora. It's a little prettier than XFCE, and consequently a little less performant. 
Notably, GNOME has a 
[strong commitment to accessibility](https://developer.gnome.org/documentation/guidelines/accessibility.html).
Its developers maintain compatibility with accessibility software such as the Orca screen 
reader and the Dasher input method.[^dasher] If you need to use accessibility software,
you may want to use GNOME. Below are screenshots of a stock GNOME installation, and one 
that's customized to show more performance values in the top bar. 

<!-- I regret that neither of these screenshots show window decorations, but this post
needs to be done more than it needs to have perfect GNOME screenshots. If they want
better advertising, they can pay me. --> 
![A stock GNOME installation]({{site.url}}/assets/linux/gnome_stock.png)
*Figure 5: A stock GNOME installation. Photo credit tristan-f-r on GitHub.*

![A customized GNOME installation]({{site.url}}/assets/linux/gnome_customized.png)
*Figure 6: A customized GNOME installation. Photo credit jackattack9999 on Discord.*


[KDE Plasma](https://kde.org/plasma-desktop/) is one of the prettiest and most 
customizable desktop environments, but some may find 
the extensive configuration options overwhelming. For example, you can customize the exact
layout and data sources used for activity monitor (the task manager equivalent). It also
runs the heaviest out of these options, so it's less suitable for older devices. 
This is what I use, so here's a picture of my desktop. It's pretty close to stock, 
and you can "rice" (customize) your desktop to be much fancier than this. 

![My desktop]({{site.url}}/assets/linux/my_desktop.png)
*Figure 5: My desktop, a relatively plain KDE Plasma installation with a HTTYD wallpaper.*

### What the heck is a distribution?
A distribution (or distro for short) is a set of software chosen to run your operating system. 
The most significant things that your distribution determines are your package manager
and your desktop environment. For example, Debian and its derivatives use the `apt`
package manager. Any time you see a tutorial suggesting something like `apt install program`,
you know they're using a Debian-based distribution. Some popular Debian-based distros are
Ubuntu, Raspberry Pi OS, Mint, Lubuntu, and Kubuntu. The last three are all derivatives of 
Ubuntu. Lots of distros come with multiple choices for a desktop environment. You can
even install desktop environments that don't come default, so you're not locked into
the graphical choices of your distribution.[^liquidglass] Switching desktop environments
manually is an advanced task, but very possible and less scary if you have a technical
friend to help you.

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
actually need to.) Sometimes this leads you down a rabbit hole. 
You can still choose not to work on your own system, but with all the new insights, 
you may find it hard to resist poking around.

The long answer is that some distributions, called **rolling release** distributions,
publish bleeding edge new packages to their package manager.
These packages are more up to date, but also not as thoroughly tested. Arch
is an example of a rolling release distribution, but is also famously difficult to use.
Not all rolling release distributions are as extreme, but they *are* more likely to
have rough edges and weird issues. 

**Stable release** distributions, like Debian, Ubuntu, Mint, and Fedora, thoroughly
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

## My Recommendations
If you've made it this far and are considering switching to Linux, my recommendation for 
a beginner distribution is Fedora with the KDE desktop environment.
Debian and its derivatives Ubuntu and Mint are acceptable starter distributions, but I 
have
[ideological disagreements]({{site.url}}/posts/Btw-I-Use-Arch) with Debian's 
design philosophy. It's not designed for users to install software willy-nilly, but in
my opinion, empowering users to do what they want is the entire point. 

Regardless of your choice, if you want help installing Linux but none of your friends know 
how to help, the [End of 10 project](https://endof10.org/) has an index of repair cafes 
and other organizations that will help you install Linux for free. 

> Thanks for reading. I'd hoped to publish this post before the Windows 10 end-of-life
> date, but writing my undergraduate thesis is taking more time than I expected. 
> Consequently, posting will be pretty slow through May 2025. Post-thesis, I want
> to do a major redesign, including comments if it's not too much work to fend off
> spammers. 
{: .prompt-info }

## Appendix: Forum Etiquette
Most linux distributions have an extremely limited number of paid staff, especially
compared to Apple or Microsoft. That means support will come from forums. Even official
forums are mostly run by volunteers, with possibly a few paid moderators or community
managers in larger forums. This is mostly a plus, since everyone on the forum is happy
to be there, but you must abide by forum etiquette and remember that you're not entitled
to their time.
Most places will treat you right if you follow a few rules: 

1. Make sure you're in the right forum for your issue. If the issue involves your OS in some way, then your distribution's forum is a good place to start. (Another distribution's forum is not!)
2. Read the individual forum's rules before posting. 
3. Be polite. 
4. You are not entitled to any individual's time, effort, or timely response. Act accordingly.
5. When troubleshooting, describe the symptoms of your problem, not your guess at what the root problem is. (See also: https://xyproblem.info)
6. [Don't ask to ask.](https://dontasktoask.com/) 

For a much more thorough explanation of the etiquette of technical forums, I highly recommend 
[How to Ask Questions The Smart Way](http://catb.org/~esr/faqs/smart-questions.html.)

Finally, if you have absolutely done your homework on an issue, followed all the rules, and asked
an informative and concise question, and someone on the forum insists on being a dickwad, 
it's quite reasonable to sic a moderator on them. If a moderator is unwilling to step in, 
find another forum. Places that force you to spend half your time fending off bad-faith
jerks are not worth your time. 

## Footnotes
[^1]: Your mileage may vary depending on your CPU.
[^2]: The actual amount of telemetry and ease of configuration depends on your distribution. I use EndeavourOS with the KDE Plasma desktop environment, which gives me a nice labeled slider describing the different levels of telemetry I can allow. 
[^TPM]: The Trusted Platform Module (TPM for short) is a microcomputer separate from your main system, and it's used to store disk encryption keys and biometrics like fingerprint or face scans. Storing them here keeps them out of reach of malware, so your biometrics can't be stolen.
[^proton]: Proton is technically not an emulator, it's a software translation layer. It doesn't emulate the entire Windows environment, it only translates the program's requests for Windows-specific tasks into Linux-specific tasks.
[^dasher]: https://en.wikipedia.org/wiki/Dasher_(software)
[^liquidglass]: Apple's horrendous liquid glass UI is guaranteeing that I won't update my laptop to Mac OS Tahoe, and in fact I'll be switching to Asahi linux as soon as I'm done with my undergraduate thesis.
