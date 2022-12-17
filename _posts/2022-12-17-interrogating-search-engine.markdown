---
layout: post
title:  "Interrogating search engine"
date:   2022-12-17 11:15:00 +0200
categories: search
---

## Motivation

Let’s say you are working on a current project/task when suddenly there is an unknown thing, either an issue you are not familiar with or an absent functionality which needs to be built:

<p align="center">
  <img
    src="/assets/question.jpg"
  >
</p>

Both searching for a particular solution and a problem to solve could be thought of as essentially the same goal, so for simplicity's sake lets refer to it as ‘solve X’.

Faced with an X there are at least two choices:
- Proceed on your own, trying to leverage one’s knowledge. In this case there is a chance of you reinventing the wheel, i.e. putting an effort to produce yet another solution to a known and previously solved problem.
- Realize that other people probably have encountered the X before and solve it, one way or another. The only tricky part is to find the reference of it 🕵️‍️

## Search
There are multiple factors which determine success (or failure) in an endeavour of finding what you are looking for.

# Search engine effectiveness

To start off with an extreme example - if there is a data which is not to be found in results (either relevant or at all), it is as good as non-existent. To a lesser degree, if results are not relevant it detracts trust from the search engine and makes people use it less often.

# Search engine API

API defines:
- Input format, such as words or keywords
- Search options, for example, a case (in)sensitivity
- Output shape (typically match results)

As a user you have no choice but to comply with the API since this is the way to talk to the search (engine). However, you have control over how you utilize each of API components.

# Input
Following strategies might help search engine to give you more relevant results:
- Being specific to narrow down the results
- Being laconic to give power to the search terms which matter most
- Using synonyms if no results found
- Making the query more abstract if no results found
- Transition to querying semi-related areas
- Reverse engineering / Bottom-up approach. Say you look for a way to log a data to certain downstream. While top-down approach is searching for how it could be done (either from documentation or posts/articles), a bottom-up way is to search for the existing services' source code which (already) logs data to the downstream

# Search engine internals / abstraction leaks
In most cases one doesn't need to bother about learning and understanding how the search works under the hood, similar to how one uses a car to drive without being a mechanic. Occasionally however it is beneficial to know its inner workings to be able to adjust the input to exploit particular nuance to obtain the results (ex3 showcases it)

# Search options
The options are a powerful way to amend the way search is performed. Typical options include case (in)sensitivity.

My current personal favourite is the intersection search mode which allows one to get results for documents which contain words from a search query not necessarily appearing together. An example of such search option is available in
[confluence's proximity search](https://confluence.atlassian.com/doc/confluence-search-syntax-158720.html)

# Content under search
As a content creator/author you could contribute to the results quality and relevance by following:
- Thinking about how people might search for a particular topic and incorporating best fitted keywords in the content. Consider using specific words as opposed to generic. To give an example - say you are writing a post about the encountered error. One way is to be vague and omit exact details of the error. Another way is to put as much as possible into the details (including the stack trace), so that people facing the error will be able to find it easily and there won't be as many duplicate posts as a nice bonus.
- Leveraging the way search engine works to make the content searchable-friendly. Imagine you have a system with a set of errors it might return in response. One way is to model the errors under a single class (maybe to make it slightly better with extra parameter to differentiate between the error types, or worst case having a single free format error description). However, for search engine it might be challenging to correlate particular error to a known type. Contrast it with modelling errors as separate distinct classes so that searching for class instance alone will yield unambiguous result.

## Search examples (warning 🚨 following might appear contrive 👻)

# Ex1 - how to access static constant in Java?
<p align="center">
  <img
    src="/assets/java_static_final.jpg"
  >
</p>

One could simply google it by knowing the right question to ask, but lets for a moment be ignorant of that.

Alternately we could realize that other source code more than likely has constants in it, and they are referred. Thus searching for ‘static final’ keyword in Java classes and opening up one of the matched documents reveals the answer (by example).

# Ex2 - How can I validate/strip tags of html string in Java?
Intersection search might give good starting points to explore in this case, i.e. 'strip tag html' query.

# Ex3 - Finding table origin by name
Suppose you are trying to figure out which part of a code creates a particular table 'some_prefix_2022_12_01_00_00_00_some_suffix' (ideally you should have tooling in place to determine table’s lineage, but say you have none).

### Attempt #1
You’ve searched the whole table name and got zero to none results from the search engine 😭

### Attempt #2
You speculate that since the table name has a timestamp component it is probably constructed either via string interpolation (String.format) or plain concatenation. Given that you strip out the timestamp component from the query and split it into two parts, prefix and suffix. This time the search shows relevant result 🎉

## Can we do better?

# Mindfulness

Unless the time is set explicitly, usually the way one learns how to work with a particular tool (including search) is in transition between tasks with an itch to resolve the encountered obstacle as soon as possible. Thus learning as little as possible to make the obstacle go away. Based on luck, the acquired knowledge will range from optimal to suboptimal.

Another factor is that tools are not set in stone and keep evolving by getting improvements and new useful features.

Because of that it is beneficial to keep exploring the tool from time to time with a fresh eyes perspective to potentially break out of old ways of doing things and to embrace better alternatives.

So go ahead and open the search engine at your disposal and examine its UI thoroughly:
- What are the elements available in UI?
- Is there anything I haven’t used recently or at all?
- Is there anything new available from the last time I studied it?

# Sharpen your tools
<p align="center">
  <img
    src="/assets/sharpening_the_axe.jpg"
  >
</p>

<p align="center">
  <img
    src="/assets/we_are_too_busy.jpg"
  >
</p>

## Misc 
In spirit of referring to existing information as opposed to copying it (though trading off availability if they go offline 🌅), here are additional resources to explore:
- [http://www.oas.org/search/ixtiphlp.htm](http://www.oas.org/search/ixtiphlp.htm)
- [https://www.mindtools.com/abtmh5z/seven-ways-to-find-what-you-want-on-the-internet](https://www.mindtools.com/abtmh5z/seven-ways-to-find-what-you-want-on-the-internet)
- [https://support.google.com/websearch/answer/134479?hl=en](https://support.google.com/websearch/answer/134479?hl=en)
- [https://support.google.com/websearch/answer/2466433](https://support.google.com/websearch/answer/2466433)
- [https://www.aarp.org/home-family/personal-technology/info-2021/tips-to-use-search-engines.html](https://www.aarp.org/home-family/personal-technology/info-2021/tips-to-use-search-engines.html)
- [https://www.freecodecamp.org/news/how-to-google-like-a-pro-10-tips-for-effective-googling/](https://www.freecodecamp.org/news/how-to-google-like-a-pro-10-tips-for-effective-googling/)
