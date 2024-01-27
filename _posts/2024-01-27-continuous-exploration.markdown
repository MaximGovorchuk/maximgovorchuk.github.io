---
layout: post
title:  "Continuous exploration / Mindfulness"
date:   2024-01-27 10:00:00 +0000
categories: miscellaneous
---

## TL;DR
Any solution is better than nothing. An even better solution is a more optimal one (or ideally the best one). Sadly often we are content with the former. Below are a few ideas on how to hopefully change that.


## Anecdote
<p align="center">
  <img
    src="/assets/chainsaws.jpg"
    width="75%"
  >
</p>

A man goes to a tool store to buy a chainsaw. The server sells him the top-of-the-line model, saying that it will cut through over 100 trees in one day.
The man takes the chainsaw home and begins working on the trees but after working for over three hours he only cuts down two trees.
“How can I cut for hours and hours and only finish two trees?” he asks himself.
The next morning he gets up early in the morning and works until nighttime, but still only manages to cut down five trees.
The very next day the man brings the chainsaw back to the store and says it doesn’t work properly.
“Hmm, it looks okay,” says the server, and starts the chainsaw.
The man jumps back in shock and cries, “What’s that noise??!!”

## Motivation
We are all busy. Working on the current project(s), thinking about the next ones, making things happen... Occasionally we encounter an obstacle in a way. Depending on its difficulty it might take quite some time to find any solution to deal with it. The issue is that sometimes we end up finding a suboptimal solution as opposed to the best one, thus ending up being in position of the aforementioned man. The next time the same obstacle occurs we happily apply the learned solution without giving a thought on how effective it is.


## Be curious / attentive / mindful
A general piece of advice is to:
Set time aside for deliberate exploration of the current learned ways of doing things. Otherwise, you are unlikely to alter the current habits and instead fallback to what served you good so far. In terms of the time it could be either time-boxed slot when working on a particular task or be exclusively dedicated one for exploration's sake alone.
Explore the problem and solution space, ideally with 'fresh pair of eyes' perspective. It's easier said than done thus following sections will provide concrete actionable advices.


## How difficult it is / Resistance
Referring back to the chainsaw's example, if something is way harder that it should be, it's good indication that you're likely doing it the hard way. In all other cases there is a potential to improve things by inventing a better way for common good. Meaning it's a win-win in any case.


## Limit yourself / disallowed list
One way is to temporarily forbid oneself to rely on the learned solutions completely and instead try to find out completely different unexplored ones, thus discovering them in bread-first-search fashion.


## Focus / allowed list
The counterpart way is to refine the already learned solutions and try to optimize, searching for potential optimizations in them, in deep-first-search fashion.


## Deliberate practice
To solidify the newly discovered or improved-upon solutions you need to practice them sufficient amount of time. So that the old solutions get reliably pushed out from recalling.


## Gamification
Us being social creatures, one way to motivate oneself to explore longer is by:
- Sharing your discoveries with others and getting thanked
- Playfully competing with others in finding the most efficient or faster solutions


## Marginal gains
Sometimes we tend to underestimate potential of making seemingly tiny improvements, such as mastering keyboard shortcuts. Typical reasoning goes that since it doesn't matter much whether you've ran a command in a split of a second vs second(s). However, if you consider amount of times you run the command, even minor improvement's effect will be beneficial (aside from reducing context switch!).


## Guidance
Besides one being a user looking for better ways of doing things, there is another party involved. In case of your in-house systems, tools and frameworks, you, as developer, can make your users' life easier by pushing them gently towards more optimal ways of doing things.
# UI
Tracking number of steps the user has taken to achieve a certain goal and showing a hint with a faster way when applicable. We could distinguish input method (keyboard vs mouse/trackpad) and consider each of them by its efficiency.
Notifying the user in case they haven't used particular functionality (at all or very rarely) VS a) everyone in the company b) everyone on the user's org/team etc. The alternative outcome might be reconsidering the UI and restructuring it.
Hinting users about newly shipped features. Only one objection I've seen in the past for not doing that was to supposedly keep A/B test as unbiased.
# Terminal / CLI
Displaying to the user the other people's variations (sorted in descending order by usage) used when running a particular command (text-based interface is tailored nicely for doing that). It aids both for self-discovery (of how to use the tool) and promotes the common ways other people use it. Though there is a danger of herd effect, if majority of people unknowingly use inferior way of running the command.
