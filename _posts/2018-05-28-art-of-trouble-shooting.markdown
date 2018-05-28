---
layout: post
title:  "Art of Troubleshooting"
date:   2018-05-28 23:40:00 +0200
categories: troubleshooting
---

![GitHub Logo](/assets/despaired.jpg)

## Everything goes smoothly, oh nooo... it is not working (+ it was working before!!)
I heard long time ago about humorous happiness formula. It looks as follows:

`happiness = reality / expectation`

As it is evident the more you expect from your reality the less happier you are end up.

To give an example - imagine a situation when you are about to solve unknown and unfamiliar task. Due to its uncertainty there are no predefined steps to follow. So if challenge is faced along the way there is no disappointment since there is no expectation.

Consider contrary case - a well-known, many times done before, similar task to do. Easy peasy. In your head you've already plotted the steps and even guesstimated time it will take to accomplish. But, as it sometimes happens quite often, the very first step annoyingly fails, with an odd problem on top of that. Following the urge of getting it away of your way asap, you hastily try few things which came to mind but none works. At that point there is great chance to slip into cycle of trying more or less same variation of the few things, hoping problem will easily be gone.

Right thing to do is to acknowledge this situation and be aware of your reaction so emotions will be toned down. Next thing is to lower expectations and proceed with problem solving ways / techniques. Keep calm and you will get there!

## Systematic approach
### Understand the issue
When you stuck, there is an option of describing the matter to inanimate object (pick a favorite or use rubber duck so more people will get to know about the approach) or your teammate (which works much better for myself):

- What is the issue about?
- Why it is an issue?
- What prevents you from fixing it?
- What fixing methods have you tried?
- Why fixing methods do not work?

More often than not, once you’ve finished explanation, thought/insight strikes you about few more possible approaches or tiny adjustment to the ones you considered so far, which makes it a solution.

Two things contribute to that most of the time:
- Switching from hard thinking (aka fixed mindset) to more defuse one ([Term's author coursera course](https://www.coursera.org/learn/learning-skills)). In a nutshell it is a way to stop thinking of an Elephant and to get Archimedes's Euruka!
- Formulating and expressing yourself verbally. It is believed that one who posses clear speech has clear thinking. There is some truth in that. 

### No assumptions
Reason why we assume is to spare cognitive/mental capability by using deductions our brain is pretty sure about. It helps in life generally however might be a cause of wasting, meant to be saved, aforementioned capabilities while troubleshooting unexpected or tough problem.

I cannot stress it enough. **Assumptions are evil**. When you’re troubleshooting certain path, make sure there are no in it at all, neither yours nor your peers’. Basically you want a health dose of paranoia towards fact checking, questioning each one of them to be proven/verified or otherwise rejected.

### One change at a time
Similar to its relevance for performance testing when you’re troubleshooting by testing hypotheses, make sure to have them sequentially one after another, reverting previous one (or if applicable mixing them together while keeping track of possible combinations). By adhering to that you won’t get surprised or puzzled. 

### No (wild) guesses
Even though you might get lucky here and there by exercising this tempting way, probability of finding solution is quite random and decreases with the size of system/place you’re looking for the issue.

### Binary search
In order to effectively identify root cause(s) one needs to posses complete understanding of system under study. It opens an option of finding problem quicker to you.

The same way existing element in sorted collection can be found by diving it in half and preceding with one of halves until it is found we can troubleshoot system in halves by verifying input and output at certain path points.