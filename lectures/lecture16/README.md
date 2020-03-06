# Lecture 16: Continuous Delivery

In this lecture we will extend our discussion on Continuous Integration from [Lecture 15](../lecture15) to include Continuous Delivery.  We will examine the additions we have to make to our process, as well as examining the risks addresses by Continuous Delivery.

## Behavioural Objectives

- [ ] **Define** *Continuous Delivery*.
- [ ] **Describe** *how to implement Continuous Delivery*.
- [ ] **Evaluate** *Continuous Delivery in the software project lifecycle.*
- [ ] **Describe** *risk within the context of Continuous Delivery*.

## What is Continuous Delivery?

From [Wikipedia](https://en.wikipedia.org/wiki/Continuous_delivery):

> Continuous delivery (CD or CDE) is a software engineering approach in which **teams produce software in short cycles**, **ensuring that the software can be reliably released at any time** and, **when releasing the software, doing so manually**.

CD extends CI by ensuring that software can be released at any time.  Notice that Continuous Delivery requires releases to be done manually.  This is unlike *Continuous Deployment* where release and deployment is automated.  We can therefore map the various continuous methods:

- **Continuous Integration** *automates testing and integration*.
- **Continuous Delivery** *extends Continuous Integration by ensuring software can be released at any time*.
- **Continuous Deployment** *extends Continuous Delivery by automating the release and deployment of software*.

We will use delivery and deployment interchangeably here, using the acronym CD. CD (like CI) requires a sequence of stages to enable release building.  We call this a deployment pipeline.  A deployment pipeline just automates the following stages:

- Build.
- Deploy.
- Test.
- Release.

The deployment pipeline aims to:

- Making the stages of the pipeline visible to the team to aid collaboration.
- It improves feedback so problems are identified and resolved quickly.
- It allows the team to deploy and release any version of their software.

Below is an illustration showing how CD produces releases:

<p><a href="https://commons.wikimedia.org/wiki/File:Continuous_Delivery_process_diagram.svg#/media/File:Continuous_Delivery_process_diagram.svg"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Continuous_Delivery_process_diagram.svg/1200px-Continuous_Delivery_process_diagram.svg.png" alt="Continuous Delivery process diagram.svg"></a><br>By <a href="//commons.wikimedia.org/w/index.php?title=User:Gr%C3%A9goire_D%C3%A9trez&amp;action=edit&amp;redlink=1" class="new" title="User:Grégoire Détrez (page does not exist)">Grégoire Détrez</a>, original by Jez Humble - This file was derived from:&nbsp;<a href="//commons.wikimedia.org/wiki/File:Continuous_Delivery_process_diagram.png" title="File:Continuous Delivery process diagram.png">Continuous Delivery process diagram.png</a>, <a href="https://creativecommons.org/licenses/by-sa/4.0" title="Creative Commons Attribution-Share Alike 4.0">CC BY-SA 4.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=43977816">Link</a></p>

### Aims of Continuous Delivery

CD attempts to deliver software as quickly as possible.  When we think of a new idea, we want to deliver it fast.  CD does so by allowing us the ability to deliver software whenever we want.

CD also aims to reduce the stress and fear of performing software releases.  Performing releases is normally considered a difficult process full of potential pain points.  It comes from the risk that has built up prior to the release which induces fear.  CD addresses this painful process by doing releases frequently.  By increasing the frequency of releases we reduce the pain.

### Principles of Continuous Delivery

CD enables many of the principles that we have discussed in Agile, Scrum, Lean, and DevOps:

- Create a repeatable, reliable process for releasing software.
- Automate almost everything.
- Keep everything in version control.
- Build quality in.
- Done means released.
- Everybody is responsible for the delivery process.
- Continuous improvement.

### Problems Overcome via Continuous Delivery

CD also addresses a number of problems seen in modern software engineering:

- **Deploying software manually**: deployments will tend towards automation over time, with humans only selecting the version and pressing *deploy*.
- **Running to a production-like environment only on deployment**: testing, deployment, and release is integrated into normal development.
- **Manual configuration management of production environments**: configuration is stored in version control and used in the automated processes.

## Implementing Continuous Delivery

We can decompose software into four components:

1. Executable code.
2. Configuration.
3. Host environment.
4. Data.

We have been working with these stages already via Maven, Docker, Travis, MySQL and Git.  So we already have the components of our CD system in place.  So what else do we need?

### Pre-deployment Feedback

First, we need our CI system to provide enough feedback so we know we can release.  We need the following automated checks:

- The build works showing the syntax of the code is correct.
- The unit tests pass.
- Software quality metrics are met (e.g., code coverage of tests).
- Acceptance tests pass ensuring the business value of the product.
- Nonfunctional tests pass.
- Exploratory testing and demonstration to the customer.

Tests at the start of the pipeline:

- Are fast.
- Try to cover as much of the codebase as possible.
- On failure stop the release, so must be tests that stop defects (e.g., correct UI colour is not a test).
- Are environment-neutral so can be simple.  They do not need a production environment.

As far as possible we automate the decision process to move to the next stage.  The machine is much better at spotting problems that small changes make to our large system.

### Release Lifecycle

Generally releases go through the following stages:

- Pre-alpha.
- Alpha.
- Beta.
- Release Candidate.
- Gold.

<p><a href="https://commons.wikimedia.org/wiki/File:Software_dev2.svg#/media/File:Software_dev2.svg"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/07/Software_dev2.svg/1200px-Software_dev2.svg.png" alt="Software dev2.svg"></a><br>By <a href="//commons.wikimedia.org/wiki/User:Heyinsun" title="User:Heyinsun">Heyinsun</a> - <span class="int-own-work" lang="en">Own work</span>, <a href="https://creativecommons.org/licenses/by/3.0" title="Creative Commons Attribution 3.0">CC BY 3.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=6818861">Link</a></p>

CD doesn't use this staged method as every commit can be a release.  Therefore, every change is potentially a version which has added value.  Therefore, every commit is a release candidate.

### Configuration Management

Anything that changes between environments must be captured as configuration information and any change to that information must be tested.  Configuration management is the process of storing, retrieving, identifying, and modifying our configuration information.  If you have a good configuration management strategy you should be able to answer yes to the following questions (from *Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation*):

- Can I exactly reproduce any of my environments, including the version of the operating system, its patch level, the network configuration, the software stack, the applications deployed into it, and their configuration?
- Can I easily make an incremental change to any of these individual items and deploy the change to any, and all, of my environments?
- Can I easily see each change that occurred to a particular environment and trace it back to see exactly what the change was, who made it, and when they made it?
- Can I satisfy all of the compliance regulations that I am subject to?
- Is it easy for every member of the team to get the information they need, and to make the changes they need to make? Or does the strategy get in the way of efficient delivery, leading to increased cycle time and reduced feedback?

#### Smoke Test

Deployments should be smoke tested.  This is just an automated script that makes sure that a system is up and running.  It can be as simple as running the application and making sure the main screen appears.  It should also check all the services required by the application are up and running.

### Business Change

CD has raises concerns for a business as we have to address the following contradictions:

- A business wants to release software fast to gain value.
- A business wants to avoid risk from such problems as violation of regulations.

This is the conflict of **performance and conformance.**  If we don't deliver software frequently we build up risk and sink resources into a non-released product.  So we use our ideas from lean to improve the organisation:

- Reduce cycle time.
- Reduce defects so less time is spent on support.
- Increase predictability.
- Adaption to new regulations quickly.
- Determine and manage the risks.
- Reduce costs due to improved risk management and delivery process.

## Continuous Delivery Project Lifecycle

Although creating a pipeline manages most of our CD process, we want to consider CD within the entire project lifecycle.  From a high-level, a software project has the following stages:

- **Identification**: based on business objectives.
- **Inception**.
- **Initiation**.
- **Development and deployment**.
- **Operation**.

### Inception

Depending on your method, the inception stage will produce some of the following (from *Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation*):

- A business case.
- A list of high-level functional and nonfunctional requirements to estimate the work.
- A release plan which includes a schedule of work and the cost associated with the project.
- A testing strategy.
- A release strategy.
- An architectural evaluation, leading to a decision on the platform and frameworks to use.
- A risk and issue log.
- A description of the development lifecycle.
- A description of the plan to execute this list.

### Initiation

*Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation* defines the following stages in initiation:

- Making sure that the team has the hardware and software that they need to begin work.
- Making sure that basic infrastructure is in place - such as an Internet connection, a whiteboard, paper and pens, a printer, food, and drinks.
- Creating email accounts and assigning people permissions to access resources.
- Setting up version control.
- Setting up a basic continuous integration environment.
- Agreeing upon roles, responsibilities, working hours, and meeting times.
- Preparing the work for the first week and agreeing on targets (not deadlines).
- Creating a simple test environment and test data.
- A slightly more detailed look at the intended system design: exploring the possibilities is really the aim at this stage.
- Identify and mitigate any analysis, development, and testing risks by doing spikes.
- Developing the story or requirement backlog.
- Setting up the project structure and using the simplest possible story, including a build script and some tests to get continuous integration under way.

Notice that this is very similar to our method in the module.

- The University has provided the hardware and software, or it can be downloaded.
- The University has provided the facilities.
- The University has provided email accounts.
- We set up version control in week 1.
- We set up CI in week 1.
- We agreed roles and setup teams in week 1.
- We set the coursework in week 1.
- We set up test environment and data in week 2.
- We started the system design in week 2.
- We identified stories and backlog in week 3.
- We set started the simplest story in week 3.

### Develop and Release

In the develop and release stages we need to meet the following basic conditions:

- Software is always working
- Working software is deployed at each iteration.
- Iterations are no longer than two weeks.

We prioritise features based on high business value.  By using an iterative process:

- We get feedback.
- Things are done when the customer signs them off and this is done during regular showcases.
- The software works at all times.
- Software is production ready at all times.

CD provides this value.

### Operation

Operation is when the software is out in the real world.  With CD we do this as soon as possible.  Thus, operation becomes part of the development lifecycle.  Once our software is in operation we can get feedback from our customers quickly.

## Risk Management in Continuous Delivery

Risk management is the process of making sure that:

- Main project risks are identified.
- Risk mitigation strategies have been put in place.
- Risks are continuously identified and managed throughout the project.
- A standard structure for project teams to report status.
- Regular updates on progress.
- Information radiators and dashboards to allow tracking of status.
- Regular audits from someone outside the team.

Not all risks can have a mitigation.  CD allows automation of progress and information, improving our risk mitigation strategies.

### How to do Risk Management

To manage risks we ask ourselves the following questions (from *Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation*):

- How are you tracking progress?
- How are you preventing defects?
- How are you discovering defects?
- How are you tracking defects?
- How do you know a story is finished?
- How are you managing your environments?
- How are you managing configuration, such as test cases, deployment scripts, environment and application configuration, database scripts, and external libraries?
- How often do you showcase working features?
- How often do you do retrospectives?
- How often do you run your automated tests?
- How are you deploying your software?
- How are you building your software?
- How are you ensuring that your release plan is workable and acceptable to the operations team?
- How are you ensuring that your risk-and-issue log is up-to-date?

### Common Delivery Problems

So what type of problems are involved in CD?  Below is a list:

- Infrequent or buggy deployments.
- Poor application quality.
- Poorly managed Continuous Integration process.
- Poor configuration management.
- Compliance and auditing.
- Automation over documentation.
- Enforcing traceability.
- Working in silos.
- Change management.

We will only examine auditing and change management as these directly address risk.

#### Compliance and Auditing

Our version control system allows us to identify for every change:

- The lines of code changed.
- Who changed them.
- Who approved the changes.

This is useful information in industries with auditing such as finance and health-care.  We can further enforce regulations by:

- Locking access to certain environments.
- Having an effective and efficient change management process.
- Requiring approvals from management before deployments can be performed.
- Requiring every process be documented.
- Creating authorization barriers to disable parts of the automated process.
- Requiring every deployment to be audited.

#### Change Management

*Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation* suggests the following process for managing approvals:

- Create a Change Advisory Board with representatives from your development team, operations team, security team, change management team, and the business.
- Decide which environments fall under the purview of the change management process. Ensure that these environments are access-controlled so that changes can only be made through this process.
- Establish an automated change request management system that can be used to raise a change request and manage approvals. Anyone should be able to see the status of each change request and who has approved it.
- Any time anybody wants to make a change to an environment, whether deploying a new version of an application, creating a new virtual environment, or making a configuration change, it must be done through a change request.
- Require a remediation strategy, such as the ability to back out, for every change.
- Have acceptance criteria for the success of a change. Ideally, create an automated test that now fails but will pass once the change is successful. Put an indicator on your operations management dashboard with the status of the test.
- Have an automated process for applying changes, so that whenever the change is approved, it can be performed by pressing a button.

## Summary

In this lecture we have:

- Defined Continuous Delivery as an extension to Continuous Integration that incorporates release building.
- Described how to implement Continuous Delivery examining items such as configuration management and business change.
- Evaluated Continuous Delivery in the software project lifecycle, discussing how it meets different stages of the lifecycle.
- Described risk within the context of Continuous Delivery, examining risk management, and conformance.

## Recommended Reading

*Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation* provides a complete overview of CD and how it can be integrated into an organisation.

![Continuous Delivery Book](img/cd-book.jpg)