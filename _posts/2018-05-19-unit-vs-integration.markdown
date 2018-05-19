---
layout: post
title:  "Unit tests vs Integration tests"
date:   2018-05-19 19:30:00 +0200
categories: testing
---
I’ve been having conflicting thoughts lately about backend unit tests, in particular whether you need to cover almost entire code base by them as TDD guides to do and whether they can be replaced by integration ones.
One of ways to at least try figuring out the answers (for the time being at least cause they tend to change/evolve over time) is to write all thoughts down so hopefully in process of doing that or as a final outcome they will come out. So here we go:

# Unit tests
## Pros
* Fastest among all tests. No additional environment (server, database, external dependencies etc) is required, setup & teardown blocks are trivial/simple and usually about stubbing or mocking class dependencies. That’s why they are best/ideal candidates for conducting mutation testing.
* If test case fails, it is obvious/evident (at least should be) what is the root cause and how to fix the code (or adjust the test). Some mocking library might stand in a way of that due to obscure error messages about NPEs.
* Hopefully, is guidance for good software design principles (separation of concerns, loose coupling, encapsulation and other goodies).

## Cons
* In case of (major) refactoring a lot of mundane effort is required to incorporate changed implementation in test code itself (due to its nature of being close to implementation details).
* If cyclomatic complexity of class method under test is one, usefulness of test is questionable since the only thing it tests is passing values down the line and returning it back up the line.

# Integration tests
## Pros
* Entry point and result assertion can be most abstract / located at highest level. In case of web server those are incoming HTTP request and HTTP response. Due to that internal/business logic can be changed/updated alone without touching test itself. In most of the cases only configuration (endpoints, payloads, configuration files) is the cause instead.

## Cons
* Slow (the only thing slower is full-blown contract tests running in real/legit environment) due to need of setting up close to real/production environment (embedded server, in-memory database, mocking external dependencies at http/soap/whatever level). They aren’t well suited for mutation testing cause slowness will be multiplied by numbers of attempted mutations.
* Require time to understand, remember and think through the whole interaction chain/path in order to get necessary mock setup and teardown.
* In case of failure one would have to investigate/find out which part of system causing it and why.

# Conflict/debate/open questions
* All scenarios/cases of unit tests can be covered in integration tests. However price to pay would be tolerating of all their cons.
* Is there a place for partially integration tests? For instance if you need to test sending of email using in-memory SMTP implementation, at what level should be entry point and validation? Do you want to have separate configuration/base test/setup for it?

# Afterthoughts/Proposals/What ifs?
## Unit tests
* To make refactoring at tests side more efficient, common interaction with implementation part (if possible) can be defined and referred from one place/test helper.
* Cyclomatic complexity of code which test asserts can be measured. In case of value 1 advice/warning can be given in report/IDE/etc that there is no need/point to test it at unit level and instead it can be covered at integration.
* Choosing of debug-friendly mocking library might be great time saver.
* While working on story/feature/task/etc consider reviewing rest of unit tests   up the line / above change itself in order to identify new invariants or/and decommission deprecated ones (for instance adding possible new or removing old type of exception which can be thrown)

## Integration tests
* In my opinion tests should have highest possible entry level and mock dependencies at (the same) lowest possible level.
* Extensive debug logging might be of a great help while troubleshooting test failures. It also will help with troubleshooting issues across all environments including the most important production one.
* Test with comprehensive assertions has reliable/proven coverage in comparison to unit test since it exercises all code for the scenario under testing and use mocks at lowest possible level.

# Summary
For now I don’t think it’s feasible and wise (in terms of further maintanability and productivity) to replace unit tests entirely with integration ones. Both of them can be used in conjunction, taking into consideration pros and cons. If it makes sense, trivial unit tests can be merged into/be part of integration test(s).
