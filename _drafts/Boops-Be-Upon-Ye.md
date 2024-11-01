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

# Initialize a new session
session = requests.Session()

# Send a boop request
boop = session.post("https://tumblr.com/api/v2/boop")
```

If you do this, you'll receive either a 400 response, meaning bad request, or 
a 401 response, meaning unauthorized.[^2] That's because this POST request
has no information about who you are or who you want to boop.

## Request Body
The request's information is carried in its headers and body. Inspecting boop
requests shows that the body is pretty simple. 

```json
{"receiver": "blog-name-here", "context": "blog_view", "type": "normal"}
```

The blog name in the receiver field has been redacted, but the rest were left
as found when inspecting requests. 

- `receiver`: The name of the blog receiving the boop
- `context`: The page from which you're booping. This value is not actually
validated in any way. I set it to "lmao" in my code and the requests still went 
through. 
- `type`: The type of boop. "normal" will send a normal boop, and "abnormal"
will send an evil boop. I didn't check what the code is for a super boop before
the API closed for the day. 

Adding these fields to the body of the request is also pretty simple. According
to the `requests` syntax, we add a `data` field containing the body formatted
as a JSON object. 

```python
import requests

# Initialize a new session
session = requests.Session()

# Send a boop request with body information
boop = session.post(
	"https://tumblr.com/api/v2/boop", 
	data={
		"receiver": "blog-name-here", 
		"context": "whatever you want",
		"type": "normal" # can also be 'abnormal' for evil boop
	}
)

```

Sending this request will get you a `401 Unauthorized` response, since we still
haven't provided any authentication information. Auth information will be 
provided in the headers. 

## Request Headers
While the request headers look scary, they aren't so bad once you filter out
all the noise. Inspecting the headers of a boop request will show you something
like this: 

```json
    "Host": "www.tumblr.com",
    "User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:131.0) Gecko/20100101 Firefox/131.0",
    "Accept": "application/json;format=camelcase",
    "Accept-Language": "en-us",
    "Accept-Encoding": "gzip, deflate, br",
    "Authorization": "Bearer aIcXSOoTtqrzR8L8YEIOmBeW94c3FmbSNSWAUbxsny9KKx5VFh",
    "X-Ad-Blocker-Enabled": "0",
    "X-Version": "redpop/3/0//redpop/",
    "X-CSRF": "REDACTED", <-- important
    "Origin": "https://www.tumblr.com", 
    "DNT": "1",
    "Alt-Used": "www.tumblr.com",
    "Connection": "keep-alive",
    "Cookie": "REDACTED", <-- important
    "Sec-Fetch-Dest": "empty",
    "Sec-Fetch-Mode": "cors",
    "Sec-Fetch-Site": "same-origin",
    "Sec-GPC": "1",
    "TE": "trailers"
```

Out of all this information, only the "X-CSRF" and "Cookie" fields need to be
periodically updated. The rest of these fields stay the same. Confusingly, 
the "Authorization" field is not involved in user authentication, and actually
stayed the same since the last time the booping API was opened for April 1. 
The cookie field contains, among other things, your authentication token. This
is a unique string that Tumblr assigns to your session. (If you log in on 
another device, that session will get a different login token.) The token 
provides proof of identity after logging in with your password, and should not
be shared. Anyone with your login token can send requests to Tumblr as if they
were in your session, because for all intents and purposes, they are. 

X-CSRF is the *anti cross-site request forgery* token. It's an authentication
token issued to you in order to prevent *cross-site request forgery* (CSRF)
attacks. These happen when an attacker tricks you into taking an unwanted
action on a site where you're already logged in. For example, an attacker
could have a link with malicious URL parameters, such as 
`https://tumblr.com?delete-account=true`. (This is only an example, not how
Tumblr actually works.) Auth tokens are usually stored as a cookie, and cookies 
are automatically included in all requests, clicking this link would send a
legitimate-seeming request. X-CSRF tokens are managed by the JavaScript in
your browser, so the site can make sure they're only sent when you click
a button designed by the site. (It's much harder for attackers to inject 
JavaScript than a simple URL, and any competent site will have protection 
against it.)

We're going to steal our own authentication and X-CSRF tokens and use them to
authenticate our automated boop requests. When you copy the headers from the request in your browser, the cookie containing the auth token and the X-CSRF
token will be valid at first, but will eventually expire. 



## Footnotes
[^1]: The most common type of request is a GET request, where your browser requests something from the server. 

[^2]:I'm putting together this write up at 00:34, so it's no longer Halloween. That means the boop API has closed down, so I can't actually test which of these
will happen. 