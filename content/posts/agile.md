# Continuous Coding with Agile

A quick summary of agile inspired by [the tweets](https://twitter.com/christianhujer/status/1217919353460408320)‍ of Christian Hujer [@christianhujer](https://twitter.com/christianhujer)

## Nothing is more agile than gaining quick confidence

After making a change, you have 90% confidence within 10 seconds, and 100% confidence within 10 minutes that the change can be released, and then you do so. This ability gives you more continuous certification, than any actual certificate. Continuous Coders embrace change, with fast feedback and Continuous everything. XP calls this "courage"

You don't need high level Scrum or SAFe certificates, if you have the technical discipline, and technical practices which enable this kind of confidence. These are known as Software Craft, Clean Code, Extreme Programming, and DevOps.

Attention to detail and discipline about the craft, which begins with whitespace discipline, proper source code formatting, names that reveal intent, and related code conventions. [@unclebobmartin](https://twitter.com/unclebobmartin) calls this "Clean Code". XP calls this "Common Coding Standard".

Rigorous coverage and automation of static and dynamic verification of the required behavior and structural quality on development, architecture, and user requirements level.

Test Automation Pyramid:

- Acceptance Tests for users
- Integration Tests for architecture
- Developer (aka Unit) Tests for programmers (By [@mikewcohn](https://twitter.com/mikewcohn) and [@unclebobmartin](https://twitter.com/unclebobmartin) ) Tailor it. Example: Separate driver test layer for the firmware HAL.

TDD - Test-Driven Development:

- 3 Laws (start with test, no more test than is sufficient to fail, no more prod code than is sufficient to pass)
- Red-Green-Refactor Cycle
- TPP - Transformation Priority Premise
- TCR - test && commit || revert
- Code Coverage with 100% line and 100% branch coverage
- Mutation coverage with 0 surviving mutants
- BDD: separate test spec and implementation, especially if it's for the user. (By [@KentBeck](https://twitter.com/kentbeck), [@unclebobmartin](https://twitter.com/unclebobmartin), [@WardCunningham](https://twitter.com/WardCunningham), [@tastapod](https://twitter.com/tastapod), and many others)

Refactor continuously and mercilessly to keep the simple design up. Don't just try to find a way that works. Try to find the best (aka simplest, easiest/cheapest to change in future) way that works. Slow in the short term. Fast in the long term.

Refactor continuously and mercilessly to keep design smells away.

- Rigidity causes predictable cost aka effort.
- Fragility causes unpredictable cost aka risk.
- Immobility/Inseparability makes you and the business cry when you try to reuse.
- Viscosity just makes you slow.

Static Code Analysis with tools like PC-Lint, CheckStyle, PMD, FindBugs, IntelliJ IDEA Inspections, SonarLint/SonarQube, ESLint, golint, whatever works for your programming language and environment.

Make sure that all team members are proficient in and have access to all tools, practices, and processes for quality assurance. The easiest way is to use open source, don't create license or political barriers between people and quality.

The 4 Rules of Simple Design:

- Reveals Intent
- No Duplication (DRY)
- Fewest Number of Elements
- Passes the Tests (By [@KentBeck](https://twitter.com/kentbeck) )

Automate rigorously. Ensure that feedback is

- fast
- easy to obtain
- difficult to bypass Fail the build if stuff is even slightly fishy! Your verification should be fast and exhaustive at the same time. When it passes, you should have 100% confidence that your software is releasable. And it should pass within minutes. Use parallelization and good caching to enable such fast builds and tests.

Good Design. SOLID Principles. Applies to Object Oriented and Functional Programming styles

- Single Responsibility: On its level of abstraction, stuff should have only one reason for change.
- Open/Closed: Implement features by adding new code (modules), not changing existing code.
- Liskov: Type hierarchies mustn't cause trouble.
- Interface Segregation: Keep unrelated users out of each other's way.
- Dependency Inversion: Depend on stable abstractions, not unstable implementations. Also:
- Avoid cyclic dependencies
- Colocate cohesive things, don't colocate non-cohesive things
- Depend in the direction of stability and abstraction. (By [@unclebobmartin](https://twitter.com/unclebobmartin), LSP by Barbara Liskov, OCP by Bertrand Meyer)

Last but not least, make sure the way to the users is short in time and space. Done should mean no less than "in the happy hands of the users". XP called this Continuous Integration, and this is also known as Continuous Release/Delivery/Deployment and DevOps.

And besides providing your stuff to the users it also means communication with, especially listening to, the users. Listening is one of the 4 practices of Extreme Programming. The other 3 are Coding, Testing, and Designing, covered above.

You can listen to the words of users directly, but you can also listen to their behavior, using metrics, KPIs, and LEAN practices.

Thanks to [@WardCunningham](https://twitter.com/WardCunningham) [@KentBeck](https://twitter.com/kentbeck) [@RonJeffries](https://twitter.com/RonJeffries) [@unclebobmartin](https://twitter.com/unclebobmartin) [@martinfowler](https://twitter.com/martinfowler) [@tastapod](https://twitter.com/tastapod) [@jbrains](https://twitter.com/jbrains) [@tottinge](https://twitter.com/tottinge) [@jwgrenning](https://twitter.com/jwgrenning) [@pragdave](https://twitter.com/pragdave) [@PragmaticAndy](https://twitter.com/PragmaticAndy) [@Grady_Booch](https://twitter.com/Grady_Booch) [@jcoplien](https://twitter.com/jcoplien) etc for these insights. Misquotations and errors are mine. Plus, buy their books, read their blogs, watch their videos.

And as always, things are exaggerated and simplified. There are no absolutes. You'll come up with "but you can't verify within 10m whether XYZ works". Is your project that big? What's your excuse for not gaining 100% release confidence within a reasonable time? Do it as fast as you can, and then make it faster.
