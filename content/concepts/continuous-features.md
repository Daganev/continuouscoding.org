---
title: Continuous Features
date: 2019-12-29T03:00:06.000Z
type: portfolio
category: ["continuous coding"]
description: "At the highest level, everything worth working on is a feature. Plan them out,
  have a goal, determine the customer, define the story."
caption: "Features, Use Cases, Stories"
tags:
  - agile
  - LEAN
  - SAFe
  - Scrum
  - Less
  - BDD
  - DDD
  - Feature
series:
  - main concepts
image: /images/feature/feature.jpg
---


There are numerous ways to define the feedback loop of planning. All of them have the same goal of generating the big picture.

- LEAN
- [Agile](/concepts/agile)
- Scrum , Kanban, [XP](https://ronjeffries.com/xprog/what-is-extreme-programming/)
- [SAFe](https://www.scaledagileframework.com/), [Less](https://less.works/)
- BDD
- DDD
- [Event Modelling](https://eventmodeling.org/)
- [Six Sigma](https://en.wikipedia.org/wiki/Six_Sigma)

As a Continuous Coder the how is less important than participating and speaking up if requirements and planning aren't clear. If you don't know why you are working on something, you will be less able to speak up and fix problems that only you are in a position to notice.

You may not have the authority, but you do have the responsibility.

# How do you know which tool is best for the job?

- Agile was designed to get small teams to iterate quickly. When is the best time to iterate quickly? When you are searching for marker fit, and seeking a solution which can go viral. This can be a startup, or an established company looking to spread.
- In contrast, Six Sigma was designed for important critical systems which could cause disaster if they failed. When the company is already established and doing well, you don't want to harm the main source of income.
- After a company has found a market fit, but before it's fully established there will be a period of chaotic and rapid growth. During this time, LEAN processes will help alleviate pressure while helping to learn which fires to focus on.

- Like most techniques in Continuous Coding, none of these strategies will be enough on their own. They need to be paired with other techniques that fit the culture of the company best.

## How does this apply to me as a developer?

- [Conway's law](https://en.wikipedia.org/wiki/Conway%27s_law) is most applicable during the feature definition phase of software development. This means that when practicing continuous coding, the language of the organization, and therefore the language of the variables and classes used within your code is going to be highly correlated to how features are organized.

  - For example, if you are working in a LEAN environment, your code will likely be set up as experiments, quick to throw away or be rewritten. If working in an Agile environment your code might be focused around UseCase Classes with the execute() function.

  - When using Domain Driven Design, you will have classes that reference repositories and boundaries.

  - Don't let the language of the domain scare you. They are all techniques with the same goals. Separation of Concerns, a common metaphor, and adaptability to change at the right level of abstraction.
