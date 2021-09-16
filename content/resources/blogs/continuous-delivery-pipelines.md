I recently finished reading [Continous Delivery Pipelines](https://leanpub.com/cd-pipelines) by Dave Farley.  While reading, I used post-notes to remind myself of things I thought were worth paying extra attention to. What follows is my take on sections where I placed post it notes, a month later.
Below are the things that stood out to me, having already gotten a pretty solid idea of what a basic CI/CD system looks like.

### The commit cycle
  A question for the author, Dave Farley.  What does it mean to commit code? Does it mean to commit locally, to commit to the central repository, or to start the CI job?
  It's unclear to me where the first set of automation should be run.  Perhaps we should split this up as follows:
  1. On save:  Run a linter, run unit tests for the current file.
  2. On local commit: Run unit tests for all files.
  3. On push to remote repository: Run the first steps of the CI to generate the artifacts.


### Time to Completion
The book recommends the following Timescales
* Complete the Commit phase in 5 min
* Complete a "fix" in 10 minutes, or just revert to the previous code state.
* All tests should be completed in under an hour.

These time scales surprised me. I would have thought it was worth spending more than 10 minutes on a fix before reverting, but after thinking about it. I think the book is correct. Be quick to revert to a last known good state.
However, I'm not sure tests taking an hour to run before deployment is still a viable practice. But perhaps this is why so many companies do CI but don't commit to CD. Automated tests over an hour is certainly faster than most manual review processes, and is also significantly more accurate.

### The 4 layer approach to Acceptance Tests
  This section of the book had the biggest impact on me, and I wish he went a bit more into the process of creating these four layers.
  The four layers are:
1. Test Cases, written in a DSL
2. The DSL itself
3. Protocol Drivers and External Dependenicies. The bridge between the DSL and the System Under test. (aka Cypress, Selenium, Mocks, etc)
4. System Under Test - The actual api of the thing you are testing.

The first layer seems like it should be simple to write, but honestly, I'm finding it difficult to know what the inputs and outputs of the DSL should be. The first few examples are simple, but when you try to emulate a complex scenario, it gets a bit more confusing.
I feel once you get 1 and 3 down, the rest should be easy.  And ofcourse, it's best if the SUT (System Under Test) is only written TDD, using these acceptance test as well as TDDed Unit Tests.


### The Acceptance Test DSL
What is the Acceptance test DSL? The Domain Specific Language for your acceptance tests is a way to focus communication on the ubiqutous language.  Acceptance tests should not change unless essential business pivots are made. Because the test is written in a DSL which reflects the goals of the bussiness.
The DSL implementation might change on a regular basis, but the tests themselves should be less fickle. With a good DSL, a system can have between 15-20K tests, with them rarely being deleted or significatly changed. That was the case of the LMAX system, which Dave Farely worked on, and is his main case study in this book and his videos.

### Data Migrations
The book also briefly covers database and data migration. He claims that tests could be written to confirm performance and backwards compatiblity for risky changes. For many this might sound like a pipeline dream, but over time, from my experience this is very doable.

### Tips for Writing Acceptance Tests

* Incoporate Acceptance Tests from the very beggining.
* Create an Executable Specification for the desired behaviour of each new piece before starting on the code.
* Think of the least techincal person who understands the problem domain. Does the test make sense to them?
* Create a new Acceptance Test for every Acceptance Criteria of the User Story
* Make it easy to differentiate Acceptance Tests from other Auotomated tests.
* Make the tests reproduceable via automation.
* Make it easy for developers to run the acceptance tests via your CI pipeline
* Automate the collection of test results coorelated to a specific build.
* Don't chase test coverage as a goal. It's a nice side effect. The main goal is confidence and accurate predictions of the code's acceptable behaviour.
* Leave room to scale up the number and complexity of tests as the project evolves.

### Manual Testing
Surprisingly, the book leaves room for manual testing. But importantly it should be a parralel process, and not one that is a bottle neck on releases.

### Immutable Infrastructure
The book favours immutable infrastructure over Synchronisation of configurations. However, there is a trade off here. Immutable infrastructure tends to result in longer deployments, and makes it hard to get a deployment done in under 5 minutes.
In theory, you can get faster deployments via a process like FTP to a PHP server. The code change/deployment is nearly instant. Or a serverless function might have the same effect. The book doesn't cover the pros and cons of having code which can deploy your entire infrastructure over 20 minutes, vs relying on a third party infastruture or a static infrastructure and deploying in under 5 mins.  
What's best for you will depend on what your doing and the culture of your company.

### Accelerate and Evidence Based Decisions
The book calls out to Accelerate which honestly, is a huge boon for our industry. I wish we had more evidence based discussions and industry wide surveys which can seperate the practices which are good for specific groups of people and the practices which are good for a large majority.

### Agile Practices
The book tries hard to give advice that will work regardless of your processes or chosen processes framework.
However, he does suggest four, very good questions to also engage in.
1. What is the current Status?
2. What is the Objective?
3. What is the next step?
4. How will we know if we have succeeded?

If you always ask yourself these questions, you can't go wrong.
This is true for the Pipeline, your day to day work, and for larger business strategies.

### Make everything Modular
In order to practice evidence based decision making, everything should be written so that it can be replaced. Don't focus on writing reusable components, focus on writing replaceable components.
Be it in your tests, your code, or your infrastructure.  The book claims that this is always worth the cost of extra thinking.


   
