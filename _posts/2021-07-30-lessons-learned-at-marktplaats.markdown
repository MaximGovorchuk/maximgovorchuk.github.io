---
layout: post
title:  "Lessons learned at Marktplaats"
date:   2021-07-30 15:00:00 +0200
categories: miscellaneous
---

### Being pragmatic / Good enough / Solve for 9x%

While sorting out old papers taken from the office, I've found an interesting one. It had 'It is not likely to happen' written with marker on it, next to the listed concerns about how things might go wrong in particular feature/flow. To be fair, most of the concerns were edge cases. At the time we've decided to ignore them while building the feature and fix them post-factum if they were to manifest. Because it takes time to design and build a perfect solution. Better yet, first 80-90% are quite easy to get right, all remaining subsequent ones are harder in increasing difficulty.

### Receiving and giving a feedback
It turns out I was receiving feedback for a long time without realizing that. There is a whole process/algorithm on how to do that too. In particular situation I was frustrated with performance of my teammate engineer. It grew up until the point of me accidentally mentioning it to our common manager who had a one-to-one talk with a person afterwards relaying generalized feedback. At the next retro my teammate expressed desire to receive a feedback face to face instead. Point being that it's much more useful and actionable to get to know concrete feedback with no risk of unintentional information twisting or miscommunication. So that it's possible to adjust one's behaviour.

### Question things

One time I got asked to work on a story. Its description was quite technical, saying that we should integrate with particular automotive API in Belgium. There was API Flemish documentation (around 50-100 pages long) attached. It was a struggle to understand machine translated English version.
I spent couple days trying to wrap my head around it and figure out a possible integration way. It resulted in couple questions, most of about showstoppers and inconsistencies between API (doc) and Jira story.
At certain point we gathered in a room to discuss them. It was discovered that the actual story is instead about (just tm) adding a text field to store user provided URL + format validation for URL itself + domain whitelisting.
I've seen similar examples of people taking at face value whatever was written in a ticket. Say it was saying there is an issue X in A, without stopping for a second to think is there an issue in A indeed (symptoms vs root cause) or whether X is an issue at all.

### Customer focus

Working in product company where employees paychecks come from end users, either directly (features) or indirectly (advertising/banners) makes you think a lot on how to make your users life easier and make them more successful. Regardless what role/position you have, it's possible to bring your very own idea from ideation to implementation. Similarly, when you're working together with customer support to solve immediate issue users are facing, you're also thinking of ways to make sure particular issue won't happen again. It serves as reminder to build new features in the least disruptive way too.

### Adjusting a message

Standup update vs one-to-one conversation. Short and understandable story to a large audience. Technical savvy person vs business one.

A) Needs a lot of details at the start
B) Needs a concise/brief problem statement and start conversation from there

Understand others needs, wants and perspective

Precise words, concise meaning.
Explain a concept using fewer words.
Explain a concept by paraphrasing it.

### Embracing power/story telling of graphs

Picture is worth of thousand words.
Graphs in Grafana (time series). Business metrics, tech metrics
A/B experiment result graphs.
User research graphs.

### End to end responsibility / ownership

Once an idea is fully formed and looks promising to give it a shot, a designing phase starts. It's about figuring out what are we going to build given existing code base, data and constraints, capacity planning (expected work load and its impact on design). After design is clear/clarified to enough degree, implementation phase kicks in by coding up the solution, covering it with sufficient tests, adding enough logs (for observability) and metrics (does my system work? business metrics). Once implementation and user acceptance testing is finished, it's time to put the change live (via canary release if especially risky), where it sits running providing values to users until eventually decommissioned or replaced by another functionality. Until it happens, the team is responsible for its operations, maintaining the codebase and metrics.
The whole process forces one to think hard and careful about how to build services, including how to test them.

### Wearing a hat of user / business person

I used to be far from thinking about business, even from how production environment looks like. Partially because of working before in service companies only and partially out of ignorance.
Computers are deterministic, people are not, so are your users. Even occasional attempt to understand their needs and wants can go a long way in seeing opportunity to make an impact. You're missing out if choose not to do that since while being capable of building things you won't know what is worth building.
Skill of sizing an opportunity will help you prioritize them in terms of what to go with first.

### Different/All teams belong to the same organization

Separate teams comprise organization. Everyone has its own goal and focus area. Everyone has its own priorities and deadlines. Sometimes these might be conflicting. The way to handle it is to remind oneself that everyone is in the same boat and learn to trade-off with each other. 

### Information/knowledge sharing

To be able to share information efficiently, following properties needs to be in place:

- Discoverability / Searchability. Unless you know exact place to look for information you're looking for you'll search for it by using search query. Quality of search results is paramount. Since if it cannot be found it effectively doesn't exist.  

- Every participant needs to understand when to ask a question to an individual versus to a group/channel. Few heuristics come to mind. Will the answer be useful for posterity/other participants today or/and tomorrow, one week from now? Will the answer likely to stay the same for a week/month/year?

- Groups / Channels for particular (ideally non-overlapping) topic/project. For participants to not be overwhelmed with messages (due to too few channels) and won't miss important question/update. 

- Structure. One question per post/message, so that corresponding reply can be easily found. No flatten (out) conversation spanning (and spamming) the main/root thread.

### Initiate long-running/waiting processes as early as possible

Consider example of integration with external API. Before even getting to coding up the backend, make sure API is accessible and performant enough (simply using JMeter will do). In case there is an issue, it can be raised immediately and started to be addressed right away.

Another examples include requesting translations, legal considerations.

### Being able to sell your idea

A litmus test to make sure idea is worthwhile. A defense mechanism against complete chaos / absence of focus.