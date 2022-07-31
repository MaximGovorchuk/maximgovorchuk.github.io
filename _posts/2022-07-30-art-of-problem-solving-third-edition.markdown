In software engineering occupation, skill of problem-solving is a crucial to have. Since one often finds himself or herself encountering an expected (or unexpected) issue (or two) while working on a task at hand. One might even say that everything we do is solving problems. Ability to deal with it in systematic and structured way makes one efficient and effective. Here are some strategies and tactics which might help with that. 

# State of mind

Emotions are what make us human. Emotions also can stand in a way of making progress. Specifically in problem-solving, it is not a rare occasion to experience multiple subsequent setbacks or get overwhelmed by issues pilling in. It all invites feelings of frustration, irritation and sadness. Few strategies can be applied to deal with it:

- Low to no expectation. The popped up issue might take a second to resolve, or a minute, or a day. Having no time estimate makes you less likely to experience negative emotions 
- Name it to tame it. When you feel frustrated already, acknowledge it to yourself by stating the emotion. After that shift focus back on a problem

<p align="center">
  <img
    src="/assets/keep-calm-and-problem-solve.jpeg"
  >
</p>

# Identifying the problem

Though it's possible to solve some problems without getting too much into their details, solving a challenging and novel one often requires taking the time to fully understand it.

It sounds trivial and unnecessary to spent time studying the problem as opposed to jumping into finding a way to solve it. If you are to be tempted into doing that you risk to:
- Solve a wrong problem
- Solve symptoms only

<p align="center">
  <img
    src="/assets/caroline-carpet.gif"
  >
</p>

## "A problem well stated is a problem half-solved" - Charles F. Kettering

The reason why it works is that by structuring problem and covering all its aspects you are surprisingly more likely to get an insight into its solution once you see fully. Whereas otherwise you might be running in circles inside your mind haphazardly trying to land on the right path.

You might have had situation in the past of describing a problem to a coworker and getting struck with a potential solution before he/she even talks back. In fact, you can explain it to inanimate objects too, such as a small rubber duck. 

## Why? Why? Why? Why? Why?

Being curious and keep asking questions is one of the ways to get to a root cause ([5 whys technique](https://en.wikipedia.org/wiki/Five_whys)). It helps to clear out assumptions and reduce thinking traps.

## "A question opens the mind, a statement closes the mind" - Robert Kiyosaki

To rephrase, asking questions promotes further questions and so it goes until you went deep enough.

## Danger of assumptions

Assumptions allow us to not check every single detail hence saving energy to be spent elsewhere. It works well in general however sometimes it backfires. If you are at the point of being confused and exhausted paths to explore it might be a time to verify the assumptions you made.

<p align="center">
  <img
    src="/assets/mark-twain.jpeg"
  >
</p>

## Reverse engineer a problem

There are two directions to tackle a problem. Going forward from it to its root cause. Opposite way is to make an educated guess of a potential root cause and trying to reach the problem by going backwards. To be able to make educated guesses you need to be aware of fundamental root causes and how they can be combined in variations.

## Logical tree

To give an example of fundamental root causes, let's say you investigating issue of a metric going outside usual threshold. First obvious direction most people would explore is checking what causes the metric value. There is second direction though, a measurement process itself, meaning it's possible for underlying metric value to be as usual but measured metric value to be wrong, for multiple reasons, incorrect units of measurement, incorrect place of measurement etc. [MECE principle](https://en.wikipedia.org/wiki/MECE_principle)

# Occam's razor

Imagine a tree with a problem at its root. All root's branches are potential root cause areas. All branches' leafs are root causes themselves. We will have probability of root cause to be assigned as a weight for each leaf. The remaining step left is to traverse root causes in descending order of their likelihood. This is what [Occam's razor](https://en.wikipedia.org/wiki/Occam%27s_razor) is about.

For example, you are about to look into particular issue. Though it's possible that it's caused by rare tricky operating system bug, it's more likely that the issue is somewhere closer to the source code you've written. 

## Binary search

Binary search algorithm can be useful beyond finding number in a sorted list in logarithmic time. Another application of it is finding a faulty commit which introduced the issue [Git bisect](https://git-scm.com/docs/git-bisect). Similarly, it can be used to troubleshoot very long regular expression. Or, though it's not clear-cut logarithmic, to troubleshoot an absence (or lack) of behaviour in a program by commenting out code sections in order to see program's behaviour shift.

## Imagination

Long time ago my niece sent me the photo somebody took in winter. There is a parking lot covered with a layer of snow. There is trail of footprints going to one of the parking spots completely free of snow. The photo is titled with 'How is it possible?', presumably asking how did the car go from there without leaving extra trails.

It's good exercise of coming up with hypothesises. To make it even more fun they should be not realistic, to give few ones:
- The person went to the vehicle (which turns out to be airborne) and flew away in it
- The person went to the empty parking spot with a shovel, cleaned it all and came back tracing his/her steps
- The parking spot is heated hence preventing snow from forming on it 

# Multiple ways to get to the solution

Some problems are trivial and coming up with an answer is super easy, barely an inconvenience:

<p align="center">
  <img
    src="/assets/easy.png"
  >
</p>

Whereas others present a challenge:

<p align="center">
  <img
    src="/assets/harder.png"
  >
</p>

Unless you know what A's and total areas are (contrived example) 

[The barometer story](https://www.mrao.cam.ac.uk/~steve/astrophysics/webpages/barometer_story.htm)

# Clustering algorithm

If you have plenty of issue samples you can try to find similarities in them which might reveal a pattern, key insight to their common root cause.

# Affirming root cause

Since [correlation does not imply causation](https://en.wikipedia.org/wiki/Correlation_does_not_imply_causation), to make sure you got the relevant root cause one strategy would be to worsen it and observer whether the problem will follow becoming worse too. If it is the case, the found root cause is more likely to be causing the problem. 

# If you hit the wall

At times of seemingly exhausting all strategies and tactics and a problem being untackled still, consider switching to another activity, ideally one which gives your mind a rest. Taking a walk, doing light exercise, brewing a tea or coffee will do.

To use the metaphor of a pinball game ([learning how to learn by Barbara Oakley](https://www.coursera.org/learn/learning-how-to-learn)) when you are focused on the problem, ideas your mind could take leap to are located not far from it. Contrast this with a diffused mode when your mind able to take longer leaps often inaccessible in focused mode.  

<p align="center">
  <img
    src="/assets/focused_and_diffused_mindset.png"
  >
</p>

Another way to explain it is to use words 'Labyrinth' and 'Maze'. Some languages have both defined as synonyms. While others, including English, differentiate them.

As opposed to maze, labyrinth won't make you puzzled or lost hence requiring mental effort to resolve since there is only one entrance which happens to be the only exit too and it leads to single place, its centre. Hence, while you're walking inside of maze you are more prone to make your mind wandering.

<p align="center">
  <img
    src="/assets/maze_and_labyrinth.png"
  >
</p>
