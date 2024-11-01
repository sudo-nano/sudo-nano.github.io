---
layout: post
title: "Boops Be Upon Ye: Automating Tumblr Booping"
date: 2024-04-22 16:00:00 -0700
tags: tumblr http-requests
category: drafts
hidden: true
--- 

## Introduction
Yesterday, Tumblr reactivated its booping system, originally pioneered as an
April fool's joke, as a Halloween event. Users that opt into the booping system
have a button on their profile that allows others to boop them with a cat paw. 
Tumblr being the PvP website that it is, people immediately took to bombarding
each other with vast quantities of boops. 

[People have already automated it with autoclicker plugins.](https://www.tumblr.com/loredwy/746566017760755712/i-just-want-to-ask-you-how-the-fuck-you-did-boop)
Being, as my partner calls me, a massive dweeb, I figured I could do better.
Instead of automating clicking the button, I can cut out the middleman and 
automate sending the network request that happens when you click the button. 

## How do boops work? 
When you click the boop button, your browser sends an **HTTP Request** to 
tumblr's servers. You can view these requests in your browser's developer tools,
specifically in the *Network* tab. Boops use a POST request, which is a type
of HTTP request that involves sending something to the servers.[^1] More 
specifically, it sends a POST request to `https://tumblr.com/api/v2/boop`. This
is pretty easy to do in Python using the `requests` library.

```python
import requests 
session = requests.Session()
request = session.post("https://tumblr.com/api/v2/boop")
```

If you do this, you'll receive either a 400 response, meaning bad request, or 
a 401 response, meaning unauthorized.[^2] That's because a simple POST request
has no information about who you are or who you want to boop.

## Footnotes
[^1]: The most common type of request is a GET request, where your browser requests something from the server. 

[^2]:I'm putting together this write up at 00:34, so it's no longer Halloween. That means the boop API has closed down, so I can't actually test which of these
will happen. 