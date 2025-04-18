---
layout: post
title: "State of the Blog (Live Document)"
excerpt: "2024-11-13: This blog will eventually move to blog.rk800.xyz due to the upcoming deprecation of the .io TLD."
date: 2024-11-23 01:03:00 -0700
tags: meta web-development blog
pin: true
--- 

## 2025-01-27
### LLM scrapers banned by robots.txt
This blog's build process now includes fetching an updated list of LLM scraper
user agents from [Dark Visitors](https://darkvisitors.com) and disallowing them via robots.txt. This is done using the [jekyll-darkvisitors](https://github.com/pettazz/jekyll-darkvisitors)
plugin. 

I was unable to get the Dark Visitors API token to magically substitute into the
jekyll config file as the docs for the jekyll plugin seem to suggest, so I had
to add an extra build step where I use `sed` to substitute the API key into the
config file from GitHub Secrets. 

## 2024-11-23
### Eventual domain change 
As some of you may know, the 
[.io Top Level Domain (TLD) is going away eventually.](https://every.to/p/the-disappearance-of-an-internet-domain)
It doesn't stand for Input/Output, it stands for Indian Ocean. This TLD is 
assigned to the British Indian Ocean territories, which are about to stop
existing, since Britain has promised to cede them to Mauritius. You may notice
that *this blog* (and every other GitHub static site with a default domain) has
a .io TLD. That means all of us will need to change domains! Yikes! 

The timeline for retiring of the .io TLD has not yet been set. When it comes
time, this blog will eventually move to **blog.rk800.xyz**. I will announce my
migration timeline as soon as I actually have one.
If you like reading
my blog, write that down (or write my contact info down) so you can find it when
I make the switch, since this page will no longer be here. 

### Considering adding comments
I'm considering adding comments to the blog, since I like interacting with 
readers. (Please send me your comments!) I haven't decided on a method, but
since this is a static site, my options are either host it dynamically or employ
a horribly cursed hack. Since I enjoy not paying for hosting, it'll probably end
up being the latter. 

### Considering CSS improvements
After increasing my intake of other people's wonderful blogs, I'm considering
altering my blog's style substantially. At present, it's just the Chirpy theme
for Jekyll, with only some slight tweaks from stock. I'm thinking it needs more
color and sillier text options, such as those from 
[oatmealine's markdown plus.](https://oat.zone/markdown-plus/) ([Internet Archive link in case the original goes down](https://web.archive.org/web/20241217212935/https://oat.zone/markdown-plus/))
Basically nothing on this front is decided yet, so if you have opinions, let me 
know. 


I will always prioritize accessibility over fun visual customizations. If there
are ever fun customizations that impair accessibility, I will provide an option
to toggle them. If you think there's something that needs an accessibility
toggle and doesn't have one, let me know and I'll get on it. 

Some blogs with fun visual design: 
- [https://izzys.casa/](https://izzys.casa/)