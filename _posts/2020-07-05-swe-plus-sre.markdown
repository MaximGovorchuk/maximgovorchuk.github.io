---
layout: post
title:  "(Software + Site reliability) engineer"
date:   2020-07-05 23:22:00 +0200
categories: SRE
---

# (Software + Site reliability) engineer

Most companies have separate roles and people assigned when it comes to working on a product (software engineers - SWEs) and making sure a site is operational (site reliability engineers - SREs).

Some however have SRE role being rotational so that every SWE acts as SRE once in agreed period.

Life is about tradeoffs and so is this decision.

Let's cover its cons first:

![How it feels like going PD oncall](/assets/my-watch-begins.gif)

- there is a bit of stress, at least given that person cares about the outcome 😃. Quiet periods alternate with waves of alerts sometimes caused by single/same root cause. One needs to keep cool, mitigate the issue and then get to the bottom of it to make sure it won't happen again.

- it's 24/7 (at least for the time of duty), meaning there is a possibility of being waken up in the middle of a night to assess whether it requires immediate intervention or its resolution can wait until office hours. 

- one can argue that having dedicated team of SREs makes the process more effective since the person will achieve optimal performance at certain point and be skillful in resolving common incident types.

Now for the pros:

- It teaches you how to build systems which are observable. how your system is doing? what do its API usage metrics show? what's its latency percentiles? do downstream dependencies respond promptly?

- It teaches you how to build systems which are troubleshoot-friendly. Do you have too much logging? Do you have too little logging? Are logging messages helpful? Do messages' current logging levels make sense?

- It teaches you to build systems which are resilient. Are there timeouts in place in case downstream dependency responds slowly? Is there circuit breaker in case downstream dependency misbehaves frequently? So that single failure won't cause cascading ones. Is it fine to fail processing request or does it need to be retryable?

- It teaches you about internals of PROD infrastructure. Site might be running in the cloud, it is an abstraction, it's dockerized and isolated and fair, until it's not, and you just learnt a new phrase, noisy neighbors)

- It teaches you about internals and nuances of technologies when slowness or/and failure triggers a behavior which was not the case in PRE-PROD (and on your machine)

- It makes you more empathetic. Next time you're about to release minor change (which just does X and should not break anything) in the end of office hours, issue mitigation from the past (which occurred around same hour) crosses your mind and makes you reevaluate a need to do release, is it so urgent? what's the gain of deploying it now as opposed to waiting until next morning (assuming it's not Friday of course 😈 )? 

- It strengthens a bond with fellow Ops and gives you common language to communicate.

## Summary

For SWE to wear a hat of SRE once in a while is strikingly similar to the idea of eating your own 🐶 food (which is typically applied to product side), this time it's an operational food 😉 

Lastly one can play devil's advocate and argue that all pros can be addressed by mentoring, design sessions, pair programming and code reviews. There is some true in that however I think beats nothing hands-on experience and lessons it instills.

On top of that there is no greater feeling than when your watch is over:

![How it feels like going off call](/assets/dobby-is-free.gif)
