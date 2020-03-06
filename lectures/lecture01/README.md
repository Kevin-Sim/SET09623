# Lecture 01: Introduction to the Module

## Creating a Cooperative Learning Community Environment for the Module

Before starting the module, I want to create a suitable learning environment for everyone in the module.  I will do this from four resources:

1. Toyota Improvement Kata.
2. Ideas from the book *A Mind for Numbers*.
3. An industry perspective - *Meeting Norms at Skyscanner*.
4. Ideas from Lean and Continuous Improvement.

### Toyota Improvement Kata

Toyota is given a lot of recognition for lean organisation development and creating learning environments in organisations.  The *Improvement Kata* is a routine to move from the current situation to a new situation in a *creative*, *directed*, and *meaningful* way.  It has four stages:

1. In consideration of a vision or direction...
2. Grasp the current condition.
3. Define the next target condition.
4. Move toward that target condition iteratively, which uncovers obstacles that need to be worked on.

**Consider learning as an improvement kata**:

1. In consideration of the outcomes of your education...
2. Grasp your current level of knowledge and understanding.
3. Define what you want to learn next - e.g. the ideas in this module.
4. Move toward that target level iteratively, which will uncover areas you don't know that need to be worked on.

### A Mind for Numbers

This is a book I recommend everyone reads to improve their learning.  One of the key messages is that our mind has two ways of thinking:

1. **Focused thinking** requires active attention, and is conscious, analytical, and serial.  It could be called the *hard* thinking your brain avoids doing unless necessary.
2. **Diffuse thinking** requires passive attention, and is subconscious, creative and parallel.  It is more like daydreaming, and is more *easy* in that your brain does it automatically.

You need to use both types of thinking to learn.  Learning helps us to problem-solve, which is the key element of being a software developer;

- **Learning** is joining *chunks* of information together into larger structures.
- **Problem-solving** is identifying the necessary chunks to apply to a problem.

**Focused** thinking is gathering new information and forming new chunks, while **diffuse** thinking is connecting chunks together.  We learn poorly when we don't use both modes of thinking:

- We let ourselves get too distracted or too engaged with multiple attentional things to think deeply (focused), for example using your phone or laptop during a lecture.
- We fool ourselves into thinking that following and copying is the same as understanding - related to *ego is the enemy*.
- We think focused attention is all we need and fail to use diffuse thinking

### An Industry Perspective

![Skyscanner Meeting Norms](img/skyscanner-meeting.jpg)

- **Be present** both physically and mentally.
- **Ask why** to me and yourself.
- **All voices are equal**.
- **Listen actively** which normally means close your laptop - take written notes instead.
- **Don't call people resources** which is more about the work place than studying, but keep it in mind when working in teams.
- And one addition from me - remember that **ego is the enemy**.

### Continuous Improvement

One final point comes from ideas of lean.  We have two objectives:

1. Have **respect for people**.
2. **Continuously improve**.

Education is a form of continuous improvement - you will never stop learning.  However, a key concept is this:

- **Respect for people** supports **continuous improvement**.
- **Continuous improvement** does not in itself support **respect for people**.

This module has you working in a team, and you need to have respect for your team members.  That means doing your share of work, supporting them in challenges, and see this as a team effort.  This can be expanded to the class - *respect* each other, and give each other support, and you can improve yourself and your class mates together.

Fundamentally, you should recognise that **education is not a competition**.  You will learn more through collaboration rather than competition.

## Behavioural Objectives

At the end of this lecture you will be able to:

- [ ] **Define** what a *software engineering method* is.
- [ ] **List** the *three Software Development Lifecycle* types.
- [ ] **List** the *four points of the Agile Manifesto*.
- [ ] **Define** what *DevOps* is and its *five goals*.
- [ ] **List** the *seven parts of a DevOps toolchain*.
- [ ] **Define** the metrics of *lead-time*, *process-time*, and *%C/A*.

## What is a Software Engineering Method?

What is a Software Engineering Method?  We have two terms we have to define here:

- **Software Engineering**
- **Method**

### What is Software Engineering?

From [Wikipedia](https://en.wikipedia.org/wiki/Software_engineering) (emphasis mine):

> Software engineering is the **application of engineering** to the **development of software** in a **systematic method**.

#### What is Software Development?

The development of software you are probably familiar with in principle, at least from a *programming* perspective.  Software Development is bigger than programming though.  Again from [Wikipedia](https://en.wikipedia.org/wiki/Software_development) (emphasis mine):

> Software development is the process of **conceiving**, **specifying**, **designing**, **programming**, **documenting**, **testing**, and **bug fixing** involved in creating and maintaining applications, frameworks, or other software components.

So we have seven areas defined for software development:

1. **Conceiving** or coming up with an idea.  This is an open-ended question based on personal choice and market need.
2. **Specifying** is coming up with requirements to build the software.  We will only skim across this idea with use case modelling.
3. **Designing** takes the specification to produce some form of model for the software.  We will do a bit of UML in this module.
4. **Programming** is the one most students are familiar with.
5. **Documenting** is the part most people dislike, but is fundamental for software reuse.  We will touch on areas of documenting.
6. **Testing** is another area people dislike.  We will look at unit testing and test automation in this module.
7. **Bug fixing** is an area that a lot of time is spent on.  This is not debugging your local code, but fixing bugs in production software.

As you can see, it is likely your software development education has only scratched the surface of software development.  The focus will have been on programming.  We will cover the other areas (except *conceiving*) through this module.

#### What is Engineering?

From [Wikipedia](https://en.wikipedia.org/wiki/Engineering) (emphasis mine):

> Engineering is the **creative application of science**, **mathematical methods**, and **empirical evidence** to the innovation, design, construction, operation and maintenance of structures, machines, materials, devices, systems, processes, and organizations.

Engineering has three strands:

1. The **application of science** - you could say engineering is applied science.  There are a collection of theories underpinning software (*computer science*) which we apply in our development process.
2. **Mathematical methods** really just means any mathematical approach involved in modelling.  We do not do mathematical modelling in the module.  These ideas come from *computer science*.
3. **Empirical evidence** means that we measure something to gain information.  We do this in the module through testing and build automation.

#### What is a Systematic Method?

Is the next main section.

#### So what is Software Engineering?

A collection of techniques (e.g. designing, programming, testing) to develop software using ideas from computer science in a manner that is systematic.  We require evidence about our software to determine if it is working as expected.

### What is a Method?

Put simply, a method is just an approach.  We effectively have a series of steps that we follow to get a result.  You may have heard of the *scientific method*.  Method as used in *Software Engineering Methods* is related - we build a process for the development of software.

Most of the ideas of *Software Engineering Methods* can be underpinned by something called the **Software Development Lifecycle**.

#### Software Development Lifecycle (SDLC)

This is the process of developing software from conception through to deployment and maintenance.  The term has been around since about the 1960s.  The following image illustrates the main phases:

<p><a href="https://commons.wikimedia.org/wiki/File:Systems_Development_Life_Cycle.jpg#/media/File:Systems_Development_Life_Cycle.jpg"><img src="https://upload.wikimedia.org/wikipedia/commons/b/bb/Systems_Development_Life_Cycle.jpg" alt="Systems Development Life Cycle.jpg"></a><br>By US Department of Justice (redrawn by <a href="//commons.wikimedia.org/wiki/User:Mdd" title="User:Mdd">Eugene Vincent Tantog</a>) - <a rel="nofollow" class="external text" href="http://www.usdoj.gov/jmd/irm/lifecycle/ch1.htm">INFORMATION RESOURCES MANAGEMENT</a>, Public Domain, <a href="https://commons.wikimedia.org/w/index.php?curid=5530145">Link</a></p>
These stages are still used today, but how we use them has changed.  The software industry has produced three key approaches.

#### Three Key Methods in Software Development

1. **Waterfall** - original ideas from 1950s, formally defined in the 1970s.  Still common today.
2. **Spiral** or incremental development - originally from the late 1980s.
3. **Agile** is from the mid 1990s.

##### Waterfall

The waterfall model gets a lot of bad press, but is still successfully used in industry today.  The biggest criticism is the rigid format it uses, in that each stage must be completed before moving onto the next stage.  This means we cannot adapt to changing customer needs.  Below is a typical representation:

<p><a href="https://commons.wikimedia.org/wiki/File:Waterfall_model.svg#/media/File:Waterfall_model.svg"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Waterfall_model.svg/1200px-Waterfall_model.svg.png" alt="Waterfall model.svg"></a><br>By Peter Kemp / Paul Smith - Adapted from Paul Smith's work at <a href="https://en.wikipedia.org/wiki/File:Waterfall_model.svg" class="extiw" title="en:File:Waterfall model.svg">wikipedia</a>, <a href="https://creativecommons.org/licenses/by/3.0" title="Creative Commons Attribution 3.0">CC BY 3.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=10633070">Link</a></p>
The original phases are:

- **Requirements gathering** or defining what is needed in the software.
- **Analysis** of the requirements to define models and rules.
- **Design** to produce the software architecture.
- **Coding** to build the software.
- **Testing** to ensure the software is working as expected.
- **Operation** of the software where needed.

##### Spiral

The spiral model builds on some of the ideas of the waterfall model but provides ability to adapt due to its iterative nature.

<p><a href="https://commons.wikimedia.org/wiki/File:Spiral_model_(Boehm,_1988).svg#/media/File:Spiral_model_(Boehm,_1988).svg"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Spiral_model_%28Boehm%2C_1988%29.svg/1200px-Spiral_model_%28Boehm%2C_1988%29.svg.png" alt="Spiral model (Boehm, 1988).svg"></a><br>By Conny derivative work: <a href="//commons.wikimedia.org/wiki/File:Spiral_model_(Boehm,_1988).png" title="File:Spiral model (Boehm, 1988).png">Spiral_model_(Boehm,_1988).png</a>: Marctroy
derivative work: <a href="//commons.wikimedia.org/wiki/User:Conan" title="User:Conan">Conan</a> (<a href="//commons.wikimedia.org/wiki/User_talk:Conan" title="User talk:Conan"><span class="signature-talk">talk</span></a>) - <a href="//commons.wikimedia.org/wiki/File:Spiralmodel_nach_Boehm.png" title="File:Spiralmodel nach Boehm.png">File:Spiralmodel_nach_Boehm.png</a>, <a href="//commons.wikimedia.org/wiki/File:Spiral_model_(Boehm,_1988).png" title="File:Spiral model (Boehm, 1988).png">Spiral_model_(Boehm,_1988).png</a>, Public Domain, <a href="https://commons.wikimedia.org/w/index.php?curid=9000950">Link</a></p>

Spiral works by iterating through the following four stages until software is released:

1. **Determine objectives** for this iteration.
2. **Identify and resolve risks** for this iteration.
3. **Development and test** for this iteration.
4. **Plan the next iteration**.

##### Agile

Agile methods build on the iterative approach, but focus on **human-centric** ideas where software is evolved by collaboration between teams and customers.  Teams are self-organising, and support multiple parts of the development process.  The point is that the teams can adapt (*be agile*) as requirements evolve with the client and the problems in development are discovered.

### Linking to Module Learning Outcomes

How does all this relate to the module.  The learning outcomes are:

1. Demonstrate understanding of a modern software development lifecycle.
2. Explain the different techniques supporting modern software engineering methods.
3. Define and analyse systems requirements and needs and specify a system design to deliver these requirements.
4. Apply modern software engineering methods and techniques to a software development project.
5. Explain the role of a computing professional in relation to social, ethical and legal issues surrounding projects.
6. Consider information security requirements in the development and delivery of software.

Our assessment strategy is:

| Learning Outcome | Assessment |
| ---------------- | ---------- |
| Demonstrate understanding of a modern software development lifecycle | Coursework |
| Explain the different techniques supporting modern software engineering methods | Exam |
| Define and analyse systems requirements and needs and specify a system design to deliver these requirements | Coursework |
| Apply modern software engineering methods and techniques to a software development project | Coursework |
| Explain the role of a computing professional in relation to social, ethical and legal issues surrounding projects | Exam
| Consider information security requirements in the development and delivery of software | Exam |

We are going to use a SDLC to deliver a software product.  Our SDLC will be agile in nature - that is our method.  For our software, we will define requirements and specify a system to deliver.  Finally, we will build a software development pipeline to automate our product delivery.  This is the coursework you will deliver.  See the [Assessment Brief](../../assessment/) for details.

The exam will look at the theoretical aspects of what we are doing.  We will look at the different techniques underpinning modern software development, understand the professional aspects of being a software developer, and consider how security requirements integrate into our SDLC.  This will form the exam part of the assessment.

Both the lectures and labs intertwine to support both the coursework and exam.  The labs provide the step-by-step instructions on how to undergo our development process.  The exam will go into more detail around this process and augment it with areas of working in teams, professionalism, ethics, and security.

## History of Software Engineering Approaches

The following is some of the highlights in software development:

- **Pre 1965** work on defining a discipline, but the term Software Engineering unused.
- **1965** various letters to the ACM, lectures, and advertisements mention the term Software Engineering.
- **1965** to **1985** the software crisis - software runs over budget, schedule, causes faults that lead to loss of life.  Software quality becomes a key idea (not the focus of this module).
- **1970s** structured programming - using `if`, functions, etc.
- **1980s** Structured Systems Analysis and Design Methodology (SSADM) - waterfall method of software development.
- **1985** to **1989** *'no silver bullet'* idea - no single technology or approach will solve the software crisis.
- **1990s** Object-Oriented Programming (OOP).
- **1990s** Internet becomes dominant technology.
- **1991** Rapid Application Development (RAD) - still common in user-interface design methods.
- **1994** Dynamic Systems Development Method (DSDM) - the first **agile** method.
- **1995** Scrum introduced - a common product management method.
- **1999** eXtreme Programming (XP).
- **2000 to today** rise of lightweight methods (the focus of this module).
- **2000s** various agile methods defined.
- **2001** [The Manifesto for Agile Software Development](http://agilemanifesto.org/).
- **2008** DevOps (Development Operations) coined.

## Agile Manifesto

Signatories state that as developers they value:

- **Individuals and Interactions** over *processes and tools*.
- **Working Software** over *comprehensive documentation*.
- **Customer Collaboration** over *contract negotiation*.
- **Responding to Change** over *following a plan*.

This is where the term agile came from.  It is worth considering what the signatories meant:

- [ ] Reflect on the [Agile Manifesto](http://agilemanifesto.org/) and analyse what the individual points mean to you.
- [ ] Read the [Wikipedia section](https://en.wikipedia.org/wiki/Agile_software_development#The_Agile_Manifesto) on the Agile Manifesto.  Reflect how your original analysis is similar and different to that presented on Wikipedia.

## Lean Software Development

Lean as a concept comes from manufacturing, but has been successfully applied to a number of industries.  In software development, a number of areas have been impacted by lean principles.  We will touch on these areas as we move through the module.

Lean software development can be summarised as seven principles:

1. **Eliminate waste** - do not do work that does not add value to the customer.
2. **Amplify learning** - usually by short iteration cycles with feedback from the client and the team.
3. **Decide as late as possible** - wait until all the facts are available before deciding how features are implemented.
4. **Deliver as fast as possible** - can be broken down into agreeing what will be delivered in this iteration using a pull-based approach.
5. **Empower the team** - let the team make decisions on the work to be done: *find good people and let them do their own job* (Lines and Ambler, *Disciplined Agile Delivery: A Practitioner's Guide to Agile Software Delivery in the Enterprise*, 2012).
6. **Build integrity in** - keep the system simple to update and modify, for example by applying *refactoring* techniques.
7. **See the whole** - see the system as a whole and work to ensure the component interactions work.  *Think big, act small, fail fast; learn rapidly* (Poppendieck and Poppendieck, *Lean Software Development: An Agile Toolkit*, 2003).

## DevOps

The combination of agile, lean, and modern build tools has lead to the DevOps (**Development** and **Operations**) culture.  Here, developers (e.g. software engineers) work closely with the operators (e.g. system deployment) to automate and monitor the entire software development lifecycle.  It can be seen as the intersection of three core software delivery ideas:

<p><a href="https://commons.wikimedia.org/wiki/File:Devops.svg#/media/File:Devops.svg"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Devops.svg/1200px-Devops.svg.png" alt="Devops.svg"></a><br>By <a href="//commons.wikimedia.org/wiki/File:Devops.png" title="File:Devops.png">Devops.png</a>: <a href="//commons.wikimedia.org/w/index.php?title=User:Rajiv.Pant&amp;action=edit&amp;redlink=1" class="new" title="User:Rajiv.Pant (page does not exist)">Rajiv.Pant</a>
derivative work: <a href="//commons.wikimedia.org/wiki/User:Wylve" title="User:Wylve">Wylve</a> - This file was derived from:&nbsp;<a href="//commons.wikimedia.org/wiki/File:Devops.png" title="File:Devops.png">Devops.png</a>:&nbsp;<a href="//commons.wikimedia.org/wiki/File:Devops.png" class="image"></a>, <a href="https://creativecommons.org/licenses/by/3.0" title="Creative Commons Attribution 3.0">CC BY 3.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=20202905">Link</a></p>

1. **Development** is typically seen as the software engineer's role.  The focus of this module is software engineering so we will look at DevOps ideas through this lens.
2. **Operations** is the management of systems where software runs.  Software does not exist on a developers machine, but integrates with existing systems and on platforms managed by the business.
3. **Quality Assurance** is where testing typically resides, although software quality is a bigger area than just testing.  Ensuring *production* quality software is the key for a DevOps team.

DevOps is not just about tools and techniques - *DevOps is also a cultural idea in an organisation*.  It requires parts of the organisation traditionally seen as adversarial to work together in a trusting environment.

DevOps has five goals (taken from [Wikipedia](https://en.wikipedia.org/wiki/DevOps)):

1. Improved deployment frequency.
2. Faster time to market.
3. Lower failure rate of new releases.
4. Shortened lead time between fixes.
5. Faster mean time to recovery.

Notice that all these ideas are about speed and effectiveness.  **Flow of work** is a key idea in DevOps.  Ideas such as number of deployments per day are key concepts in DevOps that you should explore.

- [ ] Watch the video below about Flickr's adoption of DevOps.
- [ ] Reflect on what it would take to do multiple software deployments a day, and how your own software development practice should change to reflect this.
- [ ] Do some research (e.g. a web search) on other deployment frequency stories.  Google and Amazon are particularly frequent.

[![10+ Deploys Per Day](https://img.youtube.com/vi/LdOe18KhtT4/0.jpg)](https://www.youtube.com/watch?v=LdOe18KhtT4)

### DevOps-toolchain

A key concept in DevOps is the creation of a *DevOps-toolchain*: a series of tools and techniques that support the goals of DevOps.  There are different interpretations, but the image below illustrates one set of stages:

<p><a href="https://commons.wikimedia.org/wiki/File:Devops-toolchain.svg#/media/File:Devops-toolchain.svg"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Devops-toolchain.svg/1200px-Devops-toolchain.svg.png" alt="Devops-toolchain.svg"></a><br>By <a href="//commons.wikimedia.org/w/index.php?title=User:Kharnagy&amp;action=edit&amp;redlink=1" class="new" title="User:Kharnagy (page does not exist)">Kharnagy</a> - <span class="int-own-work" lang="en">Own work</span>, <a href="https://creativecommons.org/licenses/by-sa/4.0" title="Creative Commons Attribution-Share Alike 4.0">CC BY-SA 4.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=51215412">Link</a></p>
There are seven stages here:

1. **Plan** the work to be done and its requirements from both the development and operation side.  We will do very minimal planning in the module only looking at **use cases** and **user stories** for software requirements.  We will use **Kanban**-style boards via **GitHub** to support planning.
2. **Create** the software - that is design and code the application with consideration of quality and performance requirements.  This is more the realm of software development covered in other modules, but we do add **UML** and **model-driven development** into the mix of techniques available to you.  Extensive use of version control with **Git** is also used to ensure different parts of the development are managed.
3. **Verify** is the testing of the software, including that the code is of production quality.  **Unit testing** vaguely falls into this category, although is arguably also a *create* task due to its granularity.  We do look at **configuration testing** and **continuous integration** to an extent via **Travis CI** and **Docker**.
4. **Package** the software ready for release/deployment.  We do a *very* light approach to packaging via **Maven** and the creation of a deployable JAR file.
5. **Release** the software into production in the target environment.  We will deploy our software to **GitHub** as a simulation of this idea.
6. **Configure** the IT infrastructure that the software runs in.  This falls under the operations side of DevOps, and we will only touch on basic concepts such as **Docker** 
7. **Monitor** the running software on the target infrastructure.  Monitoring our system allows us to *plan* the next work.  We will do little on monitoring beyond  **bug-tracking** and **issue-tracking** via GitHub

## Metrics for Software Development

Our final section will be on three metrics we can use to discuss the work of software development:

- The **Lead Time** is the time from when the task is created to when it is completed.  This is what the customer experiences when you deliver software, or any other service or product delivery - it is the time we should aim to **reduce**.  Today you have been given the [coursework specification](../../assessment) which has created a lead time until the end-of-trimester.
- The **Process Time** is the time from when work on the task is started until when it is completed.  Our goal is to **increase the percentage** of process time in lead time while **minimising** process time.  In other words, we start work quickly, and get it done quickly.  We want work to **flow** rather than be held up waiting in queues.
- **%C/A** or **percentage complete and accurate** helps us measure the quality of the work produced.  We can do this by asking if the work produced was *usable as-is*.

Lead-time and process-time can be visualised as follows:

![Lead Time and Process Time](img/lead-process-time.png)

## Summary

The aim of this lecture is to cover the basic concepts underpinning the module.  We will examine several of these concepts in more detail as we continue through the module.  In summary, we have:

- Specified the learning environment for the module.
- Defined what a software engineering method is.
- Listed the three Software Development Lifecycle types.
- Listed the four points of the Agile Manifesto.
- Defined what DevOps is and its five goals.
- Listed the seven parts of a DevOps toolchain.
- Defined the metrics of lead-time, process-time, and %C/A.