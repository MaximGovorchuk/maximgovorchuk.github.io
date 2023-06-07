---
layout: post
title:  "Intimidating system design interviews"
date:   2023-06-17 00:00:00 +0000
categories: miscellaneous
---

<p align="center">
  <img
    src="/assets/whiteboard-interview.jpg"
    width="50%"
  >
</p>

As opposed to coding interview which are not subjective and verifiable by means of test cases passing or not, system design interview is an open-ended question/conversation which doesn't have a single (or a few) ultimate answer. It is because a discussion, though steered by interviewer into a general definite direction, will flow individually based on interaction between interviewee and interviewer.

Interviewer being a human contributes to an open-endedness even more by mixing in their subjective experience and perception, either consciously or subconsciously. For example, an interviewer who cares a great deal about concurrency performance and maybe recently worked on optimizing a particularly tricky use case would expect interview to know performance characteristics of low-level concurrency primitives and will make sure to spend time emphasizing why it is important. 

Many companies nowadays give a high-level overview of what do they expect from a candidate to be qualified as an acceptable solution. Combined with to-be-interviewers going through interview training it is meant to maximize objectivity.

# Being effective communicator
<p align="center">
  <img
    src="/assets/guess-who.png"
    width="50%"
  >
</p>

'Guess who' is a two-player board game where players each guess the identity of the other's chosen character. Well-crafted questions allow players to eliminate one or more possible cards, thus minimizing number of questions required to win. Similarly, during time-limited interview your ability to ask right questions will give you an edge.

Things to consider:
- Prioritize asking questions which will affect overall design drastically  
- Be mindful of interviewer so that you will notice if they are confused/bored/etc. Recap the current state of design and a direction you're going next and either confirm or pivot it.
- Exploit the fact that both of you share common tech vocabulary. Use tech jargon words (but make sure you understand it deeply and not just superficially) to save time. Contrast 'To distribute load we'll use load balancer' with 'To distribute load we'll use [insert a verbose paraphrazed definition of load balancer and how it works from Wikipedia]"

# Getting initial estimates

Would MySQL scale for use case X? Is it even possible to answer this question accurately? Because the details (amount of queries, query patterns, indices, server hardware) will affect substantially. What we can estimate is to come up with an upper bound using fundamental constraints / bounding factors / bottlenecks (as mentioned in [Google SRE book](https://sre.google/workbook/non-abstract-design/)):
- Network bandwidth (how much traffic we can physically pass back and forth)
- CPU / Processes / Threads
- RAM
- Disk (space)
- Take into account replication (Primary -> Replica in regards to network bandwidth)
- Number of connections/clients

It is not perfect since MySQL has to take care of writing data (hence it make sense to differentiate between reads and writes). Reads might  affect writes depending on the isolation level. What are the query patterns? Peak usage? Trends (day time vs nighttime). It if's too much for a single instance we could introduce sharding, assuming the data can be divided into independently used partitions.

# Back of the envelope calculations
Say we design a ticket master. One way to go about expected load is to reason about it from supply perspective. Sales of each venue are likely to be independent (unless we have a multi-venue booking feature), meaning we could distribute venues processing horizontally. Next question to ask - what is the max size of a venue? Will it be small enough for a single process to manage its booking? Besides a supply we need to consider demand, will it be able to handle all users requesting booking availability? Now we need to come up with an estimate of peak usage for demand side which will depend on overall amount of users and portion of them interested in particular event.

One way to approach estimation is https://en.wikipedia.org/wiki/Fermi_problem

Lastly, when doing math, one might use approximation to save time since generally interviewer will be satisfied with the same order of magnitude answer and won't care about it to be accurate to a single digit. To give an example when multiplying `123 * 456` without calculator you could approximate it as `~= 100 * 400 = 40000` (the actual answer is `56088` which is the same order of magnitude)

# Overthinking
If you're prone to this, you'll recognize a following situation:

You are asked to suggest an API of the system to be designed. You quickly came up with an initial proposal. But instead of asking your interviewer whether it's good enough you're proactively drilling down and start thinking how could you make it more generic (cause at your work recently you've been working on the similar situation, maybe even multiple times, so that you mind wants to tackle it first as a reflex).

Depending on your luck, interviewer will either:
- Interrupt you politely and bring you back on track by saying "Let's not get into details yet"
- Patiently keep listening to let you proceed for as much time as you keep going.

(Side comment, it raises an interesting question for a working setting. Is it okay to interrupt a colleague when they are going off track or keep circling around a topic? To interrupt - time is saved but your colleague might tell you a useful insight otherwise. Important distinction, interrupt does not mean start making your point/change on the subject, but merely moderating a conversation) 

One more example - when designing image processing system you keep misspeaking by referring to it as video processing system cause at work you've been focusing/wrapping your head around video processing system. The result - you might be perceived as incompetent by interviewer 🙃

# Making assumptions
It is a balancing act. Due to a time limit, if one meticulously to confirm every single assumption they are making, they will run out of time barely making any progress. On the other hand, if you assume (pun is not intended 👻) your assumptions are correct, you end up arriving at a solution to a different problem. Interviewer will spend time correcting you and also noting down that you needed to be steered back on tracking which will affect your final score.

As in software engineering, one way to go about it is to verify only assumptions which are significant enough, matter most, be a foundational requirements, or hard to change later on. And assume safely the rest, which could be corrected without much effort later on.

Sometimes you might make a correct assumption but your interviewer might think otherwise. Hence, it's important to stress/emphasise crucial aspects/assumptions to the interviewer.

# Rapport / Feedback / Communication
Occasionally it makes sense to ask your interviewer where to go next, especially if there are multiple alternatives. Some companies state that interviewees need to lead the discussion. Hence, to make such question proactive one way is to:
"So far we did X. And next things we could cover are A,B,C. I'm going to focus/proceed looking at A unless you would like us to focus on B or C"

# Justify your choices
Contrast "To do A, we will use B. Over to next point." vs "To do A, we will use B, because of C. Over to next point."

It is important in daily work/job as well to consider your choices by:
- Explaining why you chose a particular one
- What were the alternatives (if any)
- Extra concerns / considerations

The benefit is to rule out following:
- It's not just a buzzword you've heard of, or/and technology/API you are excited to try
- It's in a set of reasonable solutions to the use case at hand (vs use microscope as a hammer) and for the scale of the problem/system.

# Knowing building blocks and their use cases

For example, a queue. When does one need a queue for? What does it provide (pros)? What does it take away (tradeoffs, implications, pitfalls, downsides). Queue types.

Knowing one (or a few) implementations. Why - you'll get an idea on practical usage nuances and possible pitfalls / considerations.

# Ideas for practice

Start with the same problem to solve (design a ticket master). Come up with a first / initial design. Validate its feasibility. Introduce a change:
- Change in requirement(s). For example more strict SLA, memory constraint, a different scale / more users
- Take away possibility of using building block X (ban list)
- Building from given components only (allow list). For example - it's not allowed to use queue for delayed async processing. This is a bottom-up approach of changing a requirement.

# Understand domain area / problem

One idea is to go through existing large scale systems (and less) and expose oneself to it get an idea about their domain ahead of it. What are the actors, entities, relationship? So that you won't waste time doing that during interview.

Clarify scope and scale.
Scope - what? SLA - how many? How fast?

Confirm understanding (translated directly into daily work). So that you know your understanding matches interviewer's. One way is to summarize and/or paraphrase it.

# Flowcharts / diagrams

Picture is worth thousand words as they say. Given you have a clear idea on what to draw and it being insightful / explanatory, picture is also faster and takes less time to create (comparing to explaining it verbally) and is more information packed / dense. Especially for illustrating interactions between systems. Practice makes perfect, both using physical and software charts. Have a plan B though. You could have tried out the announced to-be-used during interview software, and it's very neat to use wireless stylus in it. However, at the deciding moment/day the distance between you and your interviewer makes it impossible to use, too slow and too glitchy.

Toying with different types of diagrams, exploring their pros and cons and trying out different notations might be beneficial for exercising one's visualization muscle.
