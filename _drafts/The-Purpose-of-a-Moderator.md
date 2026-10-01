---
layout: post
title: "The Purpose of a Moderator is to Make Decisions"
date: 2026-9-22 16:00:00 -0700
tags: community moderation politics bluesky
category: drafts
hidden: true
--- 
<!-- Insert audience statement -->
<!--
- A human's primary asset is their discretion
- Stop trying to invent rule systems that absolve moderators of exercising discretion 
- Stop trying to invent a system that is rules lawyer-proof. It's impossible. 
  - Just fucking ban rules lawyers 
  - Humoring rules lawyers means you give more of a shit about arbitrary rule sets than minorities
- At some point you have to trust your moderators 
  - You can't design a system that doesn't require at least a little mod trust (because that requires removing discretion and therefore doing automation)
  - Having a process for dealing with mod abuse is good. Assuming no trust in your mods by default means you need new mods. 
- Nobody is entitled to your platform
- Rather than have a policy that they point to in order to justify their decisions, places that have been around the block will just ban users who harass mods based on disagreements of discretion. If someone doesn't know how to agree to disagree, you probably don't want them in your community anyway. 
-->
## Some context
In [this thread](https://app.wafrn.net/fediverse/post/01a0ac80-e914-762a-92b5-5789fb1e8455)[^1],
someone asks Bluesky team member Aaron Rodericks why threatening trans people
with concentration camps isn't against community guidelines. The person in question was
not actually saying that, but were saying something similarly unpleasant: that they think
hypothetical trans people who voted republican are getting what they deserve with respect
to the current administration. This is still bigoted, and I certainly wouldn't want that
person in any community I'm part of. To be fair to Bluesky, it
appears they took the post down. What's more interesting than the original post is Aaron's
response. 

<!-- This is a screenshot instead of an embedded post for archival reasons. -->
<img src="{{site.url}}/assets/purpose_of_a_moderator/aaron_rodericks_questions.png" alt="A bluesky post by @aaron.bsky.team. It says 'Let's address a couple of questions here. 1) Is this user toxic? 2) are they making a threat sending trans people to camps? 3) how do you address harassment? 4) how does toxicity currently work? How will it work? Apologies, this should be a blog.' The post is quote replying to a post from @jane.inurhead.lol, which says '@aaron.bsky.team hi Aaron, sorry to bother you but can you explain why it's not against ToS/Community Guidelines for cis people to threaten trans people with concentration camps? People have been actioned for less than this - why is this not also considered toxic discourse?">

At this point, I ask the reader to read [the thread](https://app.wafrn.net/fediverse/post/01a0ac80-e914-762a-92b5-5789fb1e8455)
on their own, so that I can reference it with blockquotes rather than inserting 7 more
screenshots. If the original thread gets taken down, or if Bluesky has rolled out the
accursed age verification to your region, you can instead view it 
[on the internet archive.](https://web.archive.org/web/20260916232455/https://bsky.app/profile/did:plc:ksjfbda7262bbqmuoly54lww/post/3mvobdemx6v25)

## Aaron's Approach
Aaron basically says that harassment is hard to moderate, because: 
> It's a combination of behaviour + content, and the second you publish the details of 
> the rules, people change their behaviour to avoid enforcement. 

Basically, people will rules-lawyer to continue the harassment while not crossing any of
Bluesky's stated hard lines. On its face, it might sound reasonable, but there's an
important lesson you learn if you work as a moderator for long enough: rules lawyers are 
not good faith actors, and therefore need not be given any grace. People often find that 
hard to swallow, because they've internalized the idea that others are entitled to
space in their platform or community. This is simply not true. Those wishing to grow
their community might worry that banning too many people will make their community
unattractive. To that, I ask, unattractive to whom? Further, who will you scare off by
*failing* to ban bad faith actors?[^2]

Unfortunately, this is a story I've witnessed firsthand. If you let assholes stick around,
they'll tell their friends that this is a place that tolerates assholes. It doesn't matter
if your rules theoretically prohibit toxicity. If you're unwilling to actually
take action against them, they'll share that knowledge around like the world's worst
speedrunning tech. Soon you'll be
swimming in assholes, and the people you actually want--who engage constructively and make 
art and generally form your community--will leave. You're left with a festering pit of
toxicity and the reputation to match, just like Twitter. You'll have a long, hard 
road ahead of you if you want to fix it. I don't know that I've ever seen anyone make it. 
Usually, the community just dies (or worse, persists as a 
[nazi bar](https://en.wiktionary.org/wiki/Nazi_bar)), and people find a home elsewhere.

Aaron also says that automated toxicity scores will help with moderating harassment: 
> The goal of toxicity scores is to cut down on having to make those calls, and reduce 
> exposure for the average user by default. Putting toxic replies below the fold made 
> anti-social reports drop by 80%! Imagine the impact when applied to our most toxic users!

This carries the implication that automated toxicity scoring is tractable, but automated 
harassment scoring is somehow not. While machine learning toxicity classification is
[actually pretty good](https://github.com/unitaryai/detoxify), 
it has the same issue as Aaron's described approach to
harassment: It relies on users meeting rigid criteria before a moderator action can be 
justified. It follows that that users not meeting the rigid criteria
will never recieve a moderation action, regardless of whether their behavior is actually 
harmful. (And that's not even getting into the accuracy and opacity of the automated
toxicity assessment. The current LLM craze is showing me that the average person knows
diddly squat about how machine learning replicates the biases present in its data set.)

I can already hear people clamoring: "What? Are you suggesting that moderators
bend the rules? That's mod abuse!"

<img src="{{site.url}}/assets/purpose_of_a_moderator/guidelines.jpg" alt="A screenshot from Pirates of the Carribbean: Curse of the Black Pearl. Barbarossa is saying 'The code is more like what you would call guidelines than actual rules.'">

## They're community *guidelines* for a reason
Somewhere along the line, we started calling a platform's definition of acceptable conduct
the "community guidelines" rather than rules. People recognize that language is infinitely 
evolving,[^3] and context complicates assessment of acceptable behavior. A set of rigid rules that
defines appropriate behavior is not possible to create, because rules don't live in a
vacuum. Rules and the actions they govern are surrounded by an intractable web of context:
the immediate conversation, the identities of the people talking, the venue of the
conversation, the political climate, and much more. Ultimately, the best tool we have 
to account for these factors is the judgement of our squishy organic brain. Therein lies the key
distinction between *rules* and *guidelines*: rules exist to constrain judgement, while 
guidelines exist to guide it. 

## Why constrain judgement?
That begs the question, why would we want to constrain judgement, rather than guide it? 
The only reason is that you don't fully trust the judgement of your moderators. If you
don't trust them, why are they moderators at all? There's some amount of nuance here.
If you're a massive platform (as Bluesky is), or a real life community or venue, a ban 
can have a serious impact on someone's life. In cases like that, action should require 
at least a second opinion, but crucially rules should not constrain the initial action
invoking a review. If that becomes necessary, it means your review process doesn't work.

Another reason I see people adhere to rigid rules is managing reputation 
with the community. If you clash with your people often about the actions you and your 
mod team take, it can be tempting to construct a rule set that lets you position yourself
as acting objectively and beyond criticism. This is rarely effective as a long-term
solution, because it misunderstands the problem. Your community isn't angry with the
rules, they disagree with your judgement. Your actions have undermined their trust
in you, and it doesn't matter if you thought they were justified at the time. Regardless 
of who was "right" (and it's almost *never* that simple), there was a mismatch of
expectations that led to a disagreement on the correct course of action. There's only
one way to fix that, and it's *fucking talking to people!* Talking is not optional![^4]  
<!-- Note for later: make this text vibrate on mouse over, after implementing opt-in for silly effects -->
And I mean *dialogue.* Come to the conversation prepared to change your mind, not 
shout them down. The conversation might get heated, but any conversation where people
care deeply runs that risk. 

When it comes down to it, communities are by people and for people. Moderators are here 
to exercise their judgement and their communication skills with the community.

## References
[^1]: I'm providing a Wafrn link instead of a Bluesky link, even though this thread originally too, place on Bluesky, because that's the platform I use. Also because they don't do age verification, and Bluesky does.

[^2]: Defining or detecting bad faith actors is tough, but not impossible. I am categorically not a fan of [I know it when I see it](https://en.wikipedia.org/wiki/I_know_it_when_I_see_it), and believe it to be a failure of the writer to articulate the matter at hand. Generally, I would say that bad faith actors are those whose intent is to harm the community or someone in it, but intent is often impossible to know. More practically, if there is no good-faith explanation for an individual's actions, I consider them a bad faith actor. People who have been warned their behavior is unacceptable, and go right back to it, should also be ejected posthaste. 

[^3]: In Mario Kart 8, text chat in the lobby is restricted to a number of pre-set phrases. One of these is "I'm using tilt controls!" Since players consider tilt controls to be inferior and less precise, they would spam this pre-set phrase as a means of deriding another player's skill. ([KnowYourMeme](https://knowyourmeme.com/memes/im-using-tilt-controls))

[^4]: I emphasize this so strongly because I've met lots of well-meaning leftists, moderators, etc. who will do absolutely anything except learn how to do interpersonal conflict resolution. Many people who don't know how to resolve conflicts will instead resort to declaring the other person unreasonable, and trying to excommunicate them. Individuals who act that way are not safe for marginalized people, which I'll say more about in a later post.
