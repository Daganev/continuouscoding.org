---
title: "Continuous Refactoring"
date: 2019-12-24T21:00:06+09:00
type: portfolio
category:  ["concepts"]
description: "Using TDD, focus on the Refactoring step after your tests are passing for safe design and architecture changes."
tags:
- tdd
- refactoring
series:
- main concepts
categories:
- continuous coding
image:  "images/feature/tdd.png"
---

![](/images/feature/tdd.png)

# Continuous Refactoring

Continuous refactoring is what we need to do to maintain Continuous Integrations and to make sure our pipelines for Continuous Delivery stay robust and maintain our confidence.

Continuous refactoring means that you are constantly improving the structure of your code so that the next change is easier to make, and the next developer is [realistically confident](https://www.sw-engineering-candies.com/blog-1/how-good-i-really-am-as-developer--the-dunning-kruger-effect-in-software-engineering) about the changes they are making.

### When does continuous refactoring happen?

Continuously! Ha ha, but seriously, when? Continuous refactoring happens between the red and green stages of TDD. TDD? Really? Yes, really.  [But TDD doesn't work!](https://duckduckgo.com/?q=TDD+doesn%27t+work&atb=v200-5&ia=web). Then you are [holding it wrong](https://knowyourmeme.com/memes/events/iphone-4-death-grip). TDD alone doesn't work. TDD alone isn't enough to get you creating well designed code. TDD however, DOES give you the quickest possible feedback loop for your code and design. It gives you the quickest feedback loop to know what to refactor. There is no faster feedback loop than TDD when developing software, and there is nothing more important for the Continuous Delivery pipeline than a fast feedback loop.  [TDD does work](https://duckduckgo.com/?q=why+tdd+works&atb=v200-5&ia=web), but so does any other equally fast feedback loop.

The important part here is that you have a test to confirm the expected behavior, you have that test fail to confirm the test doesn't give a false passing, you get that test to pass, and then you use the passing tests to certify that you are changing the structure, but not changing the behavior of your code.  This may sound like it only works in certain scenarios, like green field projects or bug fixing, but this works for any code which is being written after a [spike or tracer bullet](/posts/3_continuous-certification#spikes) has been written.



### How does this apply to me as a developer?

- This entire section is all about being a developer. The real question is; How does this apply to other team members?
- For the team leads. Every step in the red/green/refactor cycle should be quick. If it's not quick you don't have a [good plan](/posts/2_continuous-planning)
- For QA.  Get involved with the testing plans early. Prepare the end to end and acceptance tests which the TDD cycle can enhance.  This lets the TDD cycle focus on variations that will not be handled by most higher level tests, especially the error path.
- For everyone on the team. Test first. Know where you are going first. Have your expected outputs before you start "work".