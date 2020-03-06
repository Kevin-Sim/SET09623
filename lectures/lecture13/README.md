# Lecture 13: The Second Way of DevOps - Feedback

In this lecture we will cover the technical practices of feedback.  Feedback is our ability to gain information from our peers and systems to improve our work.  Feedback, and using feedback effectively, is important in all aspects of your life, and in development we must ensure we are doing the right work effectively.

## Behavioural Objectives

- [ ] **Define** *telemetry in software development*.
- [ ] **Describe** *how to use telemetry in software development*.
- [ ] **Describe** *how to use hypothesis-driven development*.
- [ ] **Describe** *peer reviewing for software development*.

## Create Telemetry to Enable Seeing and Solving Problems

Telemetry is defined in *The DevOps Handbook* as:

> **Telemetry**: an automated communications process by which measurements and other data are collected at remote points and are subsequently transmitted to receiving equipment for monitoring.

We need to create telemetry from applications, environments, build pipelines, etc. in our pre-production, production and deployment environments.  Our aim is to provide information to allow developers and operations to solve problem collaboratively.  This is to overcome the following scenario:

> When something goes wrong in production, we just reboot the server.  If that doesn't work, reboot the server next to it.  If that doesn't work, reboot all the servers.  If that doesn't work, blame the developers, they're always causing outages.
>
> -The DevOps Handbook

Rebooting servers is not a good sign of service profession.  It has been shown that organisations with higher service levels reboot servers 20% less often.  Rather, we use telemetry to understand contributing factors.

To enable problem-solving our systems need to continuously provide telemetry.  Developers should add telemetry to their features as part of daily work to make deployments safe.

### Create Our Centralised Telemetry infrastructure

We have to go beyond the standard methods: more than logs that are useful to developers, or system status that is interesting to operations.  We must develop applications and environments that sufficient telemetry that will allow us to understand system behaviour.  We enable capabilities such as graphing and visualising metrics, anomaly detection, proactive alerting and escalation, etc.  We also need information from deployment.  How long to build?  How long to test?  And so on.

Telemetry architecture has the following components:

- Data collection at the business logic, application, and environments layer.
- An event router responsible for storing our events and metrics.

Ideally we should have APIs to allow easy access to the telemetry data.  We want these to transform logs into metrics.  This allows statistical analysis to, for example, detect anomalies.  Instead of *SQL query failed* we get *10 SQL query fails per week*.

### Create Application Logging Telemetry That Helps Production

If you've built it, you should measure it:

> Every feature should be instrumented: if it was important enough for an engineer to implement, it is certainly important enough to generate enough production telemetry so that we can confirm that it is operating as designed and that the desired outcomes are being achieved.
>
> -The DevOps Handbook.

*The DevOps Handbook* also provides a list of logging events:

- Authentication/authorization decisions (including logoff).
- System and data access.
- System and application changes (especially privileged changes).
- Data changes, such as adding, editing, or deleting data Invalid input (possible malicious injection, threats, etc.).
- Resources (RAM, disk, CPU, bandwidth, or any other resource that has hard or soft limits).
- Health and availability.
- Start-ups and shutdowns.
- Faults and errors.
- Circuit breaker trips.
- Delays Backup success/failure.

Finally, these events can be logged at different levels:

Logging levels:

- **DEBUG**: anything that happens in the program.
- **INFO**: actions that are user-driven or system specific.
- **WARN**: conditions that could potentially become an error.  Should initiate an alert.
- **ERROR**: error conditions (e.g., API call failures, internal error conditions).
- **FATAL**: when we must terminate (e.g., failed to create network socket).

### Use Telemetry to Guide Problem-solving

Remember we want to promote a culture of learning and collaboration.  In a culture of blame, outages and problems are not documented and displaying telemetry where everyone can see them to avoid being blamed for outages.  In a culture of learning and collaboration, telemetry enables the scientific method to formulate hypotheses about what is causing problems and what we need to do to solve them.

Examples of questions we can answer (from *The DevOps Handbook*):

- What evidence do we have from our monitoring that a problem is actually occurring?
- What are the relevant events and changes in our applications and environments that could have contributed to the problem?
- What hypotheses can we formulate to confirm the link between the proposed causes and effects?
- How can we prove which of these hypotheses are correct and successfully effect a fix?

### Enable Creation of Production Metrics as Part of Daily Work

Production telemetry as part of daily work means we improve out capability to visualise problems as they appear for both development and operations. It should be as simple as writing one line of code to create a new metric that is displayed in a dashboard for everyone to see.

### Create Self-service Access to Telemetry and Information Radiators

Telemetry must be fast, easy to get, and sufficiently centralized.  This allows everyone to see what is happening.  Telemetry should be highly visible as so to be where people work.  Therefore everyone know how services are working.

An information radiator is defined by the Agile Alliance as:

> the generic term for any of a number of handwritten, drawn, printed, or electronic displays which a team places in a highly visible location, so that all team members as well as passers - by can see the latest information at a glance: count of automated tests, velocity, incident reports, continuous integration status, and so on.

Placing information radiators in highly visible places promotes team responsibility.  The team has nothing to hide from visitors (customers, stakeholders, etc.), and the team has nothing to hide from itself.  The team acknowledges and confronts problems.  We may also broadcast internally and externally to customers.

### Find and Fill Any Telemetry Gaps

We must create telemetry for all levels of the application and environment, as well as the deployment pipeline.  This includes the following levels:

- **Business level**: e.g., the number of sales transactions, revenue of sales transactions, user signups, churn rate, A/B testing results, etc.
- **Application level**: e.g., transaction times, user response times, application faults, etc.
- **Infrastructure level**: e.g., web server traffic, CPU load, disk usage, etc.
- **Client software level**: e.g., application errors and crashes, user measured transaction times, etc.
- **Deployment pipeline level**: e.g., build pipeline status, change deployment lead times, deployment frequencies, test environment promotions, and environment status.

#### Application and Business Metrics

Not only application health (e.g., memory usage, transaction counts, etc.), but also meeting of business goals (e.g., number of new users, user login events, user session lengths, percent of users active, how often certain features are being used. and so forth).  Business metrics should be actionable - how to change our product and inform experimentation and A/B testing.  If they cannot be actioned they are vanity metrics.

The information radiators should make sense to everyone and align to business goals (e.g., revenue, user attainment, etc.).  Each metric should link to a business outcome and measure these in production.

#### Infrastructure Metrics

We need telemetry to see if problems are occurring in the environment.  The telemetry needs to highlight which part of the infrastructure is a problem, e.g.,:

- database.
- operating system.
- storage.
- networking.
- etc.

#### Overlaying Other Relevant Information Onto Our Metrics

Changes should be visibly mapped to the graphs.  This makes work visible and highlights where a problem may have occurred.  For example, a system with a large number of transactions may take time to return to normal operation.  We want to see how quickly this is, and to spot any anomalies.  

## Analyse Telemetry to Better Anticipate Problems and Achieve Goals

The whole point of having telemetry is to spot problems and measure success.  But having data is not enough.  We need to analyse the data and from this analysis highlight issues or take action.  Data analysis is a large field in its own right, so we will skim some of the ideas only.

### Use Means and Standard Deviations to Detect Potential Problems

Calculating the mean (or average) of our data is a useful starting point.  Combining with standard deviation (the amount of variation in the data) allows to filter events so that we only respond to results outside the norm.  Below is a diagram illustrating a normal (or Gaussian) distribution and standard deviations.

<p><a href="https://commons.wikimedia.org/wiki/File:Empirical_Rule.PNG#/media/File:Empirical_Rule.PNG"><img src="https://upload.wikimedia.org/wikipedia/commons/a/a9/Empirical_Rule.PNG" alt="Empirical Rule.PNG" height="464" width="640"></a><br>By <a href="//commons.wikimedia.org/w/index.php?title=User:Mathprofdk&amp;action=edit&amp;redlink=1" class="new" title="User:Mathprofdk (page does not exist)">Dan Kernler</a> - <span class="int-own-work" lang="en">Own work</span>, <a href="https://creativecommons.org/licenses/by-sa/4.0" title="Creative Commons Attribution-Share Alike 4.0">CC BY-SA 4.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=36506025">Link</a></p>

We are trying to improve the signal-to-noise ratio by spotting outliers.  We analyse the data set for a metric and alert if it is significantly varied from the mean.  For example, if failed login attempts for a day is three standard greater than the mean.

### Instrument and Alert on Undesired Outcomes

Post-mortems of severe incidents allows us to determine what telemetry would have helped spot the problem earlier.  *The DevOps Handbook* details such indicators for a web server going down:

- Application level: increasing web page load times, etc.
- OS level: server free memory running low, disk space running low, etc.
- Database level: database transaction times taking longer than normal, etc.
- Network level: number of functioning servers behind the load balancer dropping, etc.

By continually undertaking this post-mortem work we allow faster problem finding and therefore improve our quality of service.

### Problems that Arise When Our Telemetry Data Has Non-Gaussian Distribution

If our data does not form a normal distribution we have to use other techniques of analysis.  At this point, deeper statistical analysis is required.  Although under-reporting is a major problem, over-reporting will mean people do not take errors seriously, or people may be woken up in the middle of the night for a non-event.

### Using Anomaly Detection Techniques

Anomaly detection is *the search for items or events which do not conform to an expected pattern.*  One such technique is smoothing, where we average across a range of the data points rather than at a single data point.  Other techniques include Fast Fourier Transforms, and the Kolmogorov-Smirnov tests.

## Enable Feedback So Development and Operations Can Safely Deploy

Deployment should be a safe act.  This can be done via improved telemetry, peer review, and automated testing.  The aim is to encourage small yet well informed changes so that risk is reduced.  Small changes that anyone can understand is the goal.

### Use Telemetry to Make Deployments Safer

Telemetry for application and system health is important, but don't forget gathering metrics about the deployment pipeline.  Again, using the techniques of finding gaps, doing post-mortems, etc., will help identify what telemetry will make our deployments safer.

### Dev Shares Pager Rotation Duties With Ops

We are trying to avoid developers marking work as done because they have finished a feature and passed it to the operations team.  The goal of DevOps is to have development and operations working together.  By ensuring everyone on the team (dev and ops) has responsibility for operational incidents, everyone will take ownership of the decisions they make.

We do this so defects are given priority by the development team.  If problems keep occurring and operations cannot resolve these problems, then our system is becoming more fragile and our quality of service is reducing.  The side effect of this practice is development sees done as features working in production rather than code being written.

### Have Developers Follow Work Downstream

User Experience (UX) design uses contextual inquiry.  This is a practice where product teams watch a customer use an application in their natural environment.  We can use this approach for developers.

Developers normally do not watch people using their software.  When they do, developers are often dismayed by how users actually work, stating that they didn't realise all the problems they were causing their customers.

Developers should follow their work downstream.  That includes testing and operations as well as customers.  By doing so, development better understands the problems that occur with the work they do, and thereby improve their practices.

### Have Developers Initially Self-manage Their Production Service

When new products are initially worked on, development should self-manage their production environment.  This helps development understand production.  Once the product is of a significant size, operations can come in to support the production.

Product launch guidance can be produced to support new development teams.  *The DevOps Handbook* defines such guidance and requirements:

- Defect counts and severity: Does the application actually perform as designed?
- Type/frequency of pager alerts: Is the application generating an unsupportable number of alerts in production?
- Monitoring coverage: Is the coverage of monitoring sufficient to restore service when things go wrong?
- System architecture: Is the service loosely - coupled enough to support a high rate of changes and deployments in production?
- Deployment process: Is there a predictable, deterministic, and sufficiently automated process to deploy code into production?
- Production hygiene: Is there evidence of enough good production habits that would allow production support to be managed by anyone else?

## Integrate Hypothesis-Driven Development and A/B Testing into Our Daily Work

Our aim is to meet business goals.  Developers working on long-term features and products need to confirm that the work they are doing is meeting these business goals, or indeed is being used at all.

Before building a feature, we should ask ourselves the question: should we build it, and why?  We then need to undertake the cheapest and fastest experiment to check our thinking.  This will require some form of user research.  The faster our experiment-iterate-feedback cycle, the faster we can produce products the customer wants.

### A Brief History of A/B Testing

A/B testing is where we provide two different versions of a product to different groups of users.  We then analyse how these versions are used and pick which one provides the outcomes we are looking for.

A/B testing was initially used in direct response marketing.  This meant sending physical mail (e.g., postcards, flyers) asking customers to accept an offer by calling a telephone number, returning the card, or placing an order. The offer was modified and adapted (e.g., reworded, changing design, etc.) to determine which version gained the highest response.

A/B testing has also been used for political fundraising and Internet marketing.  Amazon and Google are well known for using this technique on their websites.  Users may see a slightly different version of Amazon or Google and the usage monitored to determine which version improves the metrics under test. The UK government has even used A/B testing for tax collection letters.

### Integrate A/B Testing into Our Feature Testing

A/B testing on websites involves visitors randomly being shown either a control (**A**) or a treatment (**B**).  By performing statistical analysis on visitor behaviour we can determine if certain features (e.g., design element, colour) cause different outcomes (e.g., conversion rate, order size).

Without user research, we will build features that deliver no, or worse negative, value to the organisation.  At the same time, we increase the size of our codebase, and thus maintenance costs.  A/B testing ensures we meet our goals.

### Integrate A/B Testing into Our Release

We can integrate A/B testing into our releases using [Feature Toggles](https://en.wikipedia.org/wiki/Feature_toggle).  Thereby we can deliver multiple versions of code on-demand to different customer groups.

### Integrating A/B Testing into Our Feature Planning

Hypothesis testing should be part of our backlog.  We can write cards in the following form:

> We believe **[TYPE OF USER]** has a problem **[DOING THING]**. We can help them with **[OUR SOLUTION]**. We'll know we're right if **[CHANGE IN METRIC]**.

## Create Review and Coordination Processes to Increase Quality of Or Current Work

Peer review is one of the most powerful techniques available to reduce risk.  *The DevOps Handbook* provides an example from GitHub.  Pull requests are used to tell others about changes pushed to a repository on GitHub.  People review the changes and discuss further modifications and produced further commits if necessary. Pull requests get votes (+1, +2, or @mention). GitHub flow integrates this feedback into its development cycle:

1. New descriptive branch created from master (e.g., `new-login-feature`).
2. Commits made to local branch, and regularly pushed the same on the server.
3. When feedback or help is required, or when the branch is ready to merge, a pull request is opened.
4. After review and any necessary approval, merge it into master.
5. Once the code is merged and pushed to master deploy into production.

### The Dangers of Change Approval Processes

*The DevOps Handbook* retells the story of Knight Capital.  A software deployment failure resulted in a 15 minute error that incurred a $440 million trading loss (or almost $30 million per minute). The loss resulted in Knight Capital being sold that weekend just to allow continued operation.

When failures happen there are often two counter-explanations:

1. The failure was due to change control failure, and we believe better change control practices could have prevented the problem, or at least allowed faster detection.
2. The failure was due to a testing failure, and we believe better testing practices could have detected the problem and prevented it happening or escalating.

Actually, low-trust, command-and-control cultures are likely to result in problems reoccurring, and sometimes worse.

### Potential Dangers of "Overly Controlling Changes"

Change controls will lead to:

- Longer lead times.
- Reduce the strength of feedback.
- Slow feedback.

This is because change control typically:

- adds more questions that need to be answered.
- adds more authorisations (e.g., one more level of management approval, more stakeholder approval).
- adds time so that changes can be properly evaluated.

All we are doing is increasing the number of steps involved in making a change, and thereby increasing batch sizes, and thus deploy times.  All of these we know increases our work and introduces risk.

The Toyota Production System states: 

> People closest to a problem typically know the most about it.

The further the person doing the work is from the person deciding the work, the worse the outcome.  Reading a long textual description of a change or using a checklist does not predict success.  Reading all the lines of code that have changed also does not tell us anything.  Peer review reduces our reliance on external bodies to authorize our changes.

### Enable Coordination and Scheduling of Changes

If multiple groups are changing dependant systems, we need to coordinate to ensure we do not interfere with each other.  We may even have to schedule changes where groups work together to schedule the sequence of changes to minimise problems.

### Enable Peer Review of Changes

Code review can be used in any part of development and operations.  Reviewing before committing to master minimises the impact change has on a global level.  We also use small batch sizes.  The larger the change, the longer we need to review, and the likelihood of missing a problem is increased.

*The DevOps Handbook* outlines some guidelines for code review:

- Everyone has a reviewer before committing to master.
- Everyone monitors commits to identify and review any conflicts.
- Define which changes are high risk and require an expert.
- Any change to large to understand is split into smaller changes.

*The DevOps Handbook* also defines types of code reviews:

- Pair programming.
- Over-the-shoulder - one developer looks over shoulder as the author walks through the code. 
- Email pass-around - source code management system emails for reviews automatically.
- Tool-assisted code review.

### Potential Dangers of Doing More Manual Testing and Change Freezes

If testing is only occurring at the end of the project, increasing the testing when failure occurs may cause more problems.  Avoid large batch testing that is scheduled during work freezes.  Integrate testing into daily work.  This will build quality in, allowing test, deploy, and release in smaller batch sizes.

### Enable Pair Programming to Improve All Our Changes

Pair programming is when two programmers work together at the same machine.  A common model is one programmer acting as the driver writing code, and the other as the navigator reviewing the work.  The navigator can come up with improvements while the driver can focus on completing the task.  Skills are also transferred between the two programmers.  Another model from **Test-Driven Development (TDD)** - see [Lecture 14](../lecture14) - is one programmer writes the test and the other writes the code to pass the test.

One advantage of this approach is knowledge increases throughout the organisation as people work together.

#### Evaluating the Effectiveness of Pull Request Processes

We also need to monitor the peer review process to ensure it works effectively.  One technique is analysing any problems and then the peer review process of any associated changes.  Also, we need to ensure our changes are properly documented.  Having little documentation means the reader does not understand the change in context, and therefore may accept a bad change.

### Fearlessly Cut Bureaucratic Processes

As processes can increase lead times, preventing us from delivering value and increasing the risk to the organisation, we need to be willing to change these processes.  A good metric to publish is the meetings required to perform a release, with the goal to reduce this to only those that are necessary.

## Summary

We have covered a lot in this lecture, but the core ideas we have examined are:

- We defined telemetry in software development - an automated communications process by which measurements and other data are collected at remote points and are subsequently transmitted to receiving equipment for monitoring.
- We described how to use telemetry in software development - examining what to measure, how to fill gaps, and the infrastructure to support it.
- We described how to use hypothesis-driven development - looking at A/B testing and backlog hypothesis items.
- We described peer reviewing for software development - especially the benefits of pair programming.

## Recommended Reading

*The DevOps Handbook* Part IV goes into far more detail about how to practice these ideas.

![The DevOps Handbook](img/devops-book.jpg)