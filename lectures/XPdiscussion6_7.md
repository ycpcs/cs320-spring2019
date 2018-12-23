---
layout: default
title: "XP Discussion Topics, Chapters 6-7"
---

Excerpted from "Extreme Programming Explained" by Kent Beck.

Chapter 6: Practices
============

The author breaks up the various practices of XP into Primary and Corollary Practices.  Practices are the application of the principles of XP.  We are going to discuss the Primary Practices.  

Chapter 7: Primary Practices
============

**SIT TOGETHER:** Frequent (constant) communication is a primary component of XP.  Th author proposes that teams must be co-located, in an open space, to foster communication and collaboration.  But he also recognizes that everyone needs a certain amount of privacy - either by providing small private spaces nearby, or by limiting work hours.

The author also suggests that this kind of work environment should be eased into - rather than having it suddenly thrust upon people who are used to having a sense of privacy and ownership of a space.

My experience is only with private offices and cube "farms".  Corporate HQ for my previous employer was looking at mandating this kind of layout - open collaborative spaces, with small private areas, but with low cube walls that did not provide the privacy that we were all used to.  Many people raised a big uproar over having this kind of layout thrust upon us.  Fortunately, our local management solicited our input, recognized the issues, and the transition was shelved for the immediate future.

**Have you done school work in this kind of environment - labs and assignments in CS101 and CS201, or other classes?  Which do you prefer, working alone, or working in a group?  Which do you find to be more productive?**

**WHOLE TEAM:** The author discusses identifying with the team, rather than with the function.  Teams should be comprised of people with a diversity of skills that covers the needs of the project.  The team may need to be dynamic, as requirements change and as tasks are completed, and new ones started.  But the author does emphasize that team members should be dedicated to the team - not splitting their time between multiple teams or functions.

**What experience do you have with being a member of a team - whether it is a sports team, a robotics team, or a team of developers?**

**Do you like to concentrate on one thing exclusively, or do like to mix things up, and have a diversity of problems to solve?**

**INFORMATIVE WORKSPACE:**  The author proposes a layout for team workspaces, including posting regular information on the status of the project in visual form - contributing to team identity and cohesion.

**When you look at the suggest workspace layout, how would you feel about your privacy, with the collaborative workstations sitting directly behind your private space?**

**What expectations do you have for privacy when you enter the workforce?**

**ENERGIZED WORK:** At least three times, the author mentions limiting work hours as a way to foster productivity.  He mentions a penchant for working long hours in this profession, but also states that SW development is a game of insight, and insight takes a prepared, rested, relaxed mind.

**When you are solving problems, working on a SW assignment, or an engineering project, how do you like to work - in long stretches, or in smaller chunks with breaks in between?**

**How do you think a manager will react to the author's limited work hours suggestion?**

**How would you feel about working 40, 60, or even 80 hours per week, when your co-workers/teammates are putting in less hours than that?**

**What are your expectations for the length of a work week?**

**PAIR PROGRAMMING:** The author states, "Write all production programs with two people sitting at one machine."  The author also talks about how intense and tiring pair pogramming can be, and also mentions that pairs should rotate partners every couple of hours, to as frequently as every 30 minutes for difficult problems.

**What are the advantages of this approach?**

**What disadvantages do you see?**

**How do you think this practice would work for you?**

**STORIES:** Stories describe customer-visible functionality, i.e., functionality the customer expects to see.  They do not describe what goes on in the background, or any level of implementation.  The author eschews the term "requirement" - estimating that as little as 5% of requirements are really ncessary for acceptable operation of the system.  Stories can also be used to break up the problem into its essential pieces, and then can be used to estimate and prioritize the work.

**What stories will you come up with for your project?**

**How will you come up with a complete enough set of stories that adequately describe the work you need to do, and how will you prioritize them?**

**WEEKLY CYCLE:** The author suggests planning work a week at a time.  Have the customer pick a week's worth of stories - thus, the customer is providing the priority list for the work to be done that week.  The author also suggests creating a stack of stories for that week, preferably small stories that require only a single developer - or pair of developers for pair progamming - and have people pull from the top of the stack so that they get a variety of tasks.

**How will you decide which stories to implement each week, and how will you assign those tasks to the members of your team?**

**How will you recognize if you are behind schedule, and what will you do to compensate if your schedule slips?**

**SLACK:** The author suggests building slack into the schedule - including some minor tasks that can be dropped if the team falls behind.  He discusses having team members only sign up for what they feel they can truly deliver, rather than overcommit to tasks, which can result in inefficient and wasteful development practices.

**How will you prioritize your tasks, in case you overcommit (which is almost inevitable for a project like this)?**

**How would you deal with a manager (or management culture) that fosters overcommitment, thus requiring long working hours?**

**TEN-MINUTE BUILD:** The author suggest building frequently, to receive timely feedback on the state of the system for all team members.  He suggests that the build be maintained at ten minutes, since a build that takes a long time will be used less frequently, resulting is less feedback.  He gives suggestions on how to limit the time of the build, but also states that the build time must also include automated unit tests.

**Your project will likely not take anywhere near 10 minutes to buid and test.  But, how often will you decide to execute a build and run your automated tests?**

**CONTINUOUS INTEGRATION:** The author suggests that integretion and testing of changes should occur no more than every couple of hours.  Integration of new code can be difficult and time-consuming.  The larger the chunk of code, the more problematic it can be to integrate - introducing a large defect load to correct before moving forward.  Individual team members (or pair programmers) generally work with their own local copy of the code, and then integrate by merging it into the master respository for the project, which is then followed soon after by a build.

**As each member of your team works on their own tasks, how often will you integrate their code, build, and test the system?**

**TEST-FIRST PROGRAMMING:** The author suggests writing automated tests that will fail, before changing any code.  You saw this with Klondike in CS201, and with the programming questions on the CS201 exams.  He lists several benefits of test-first programming, including limiting scope creep and coupling and cohesion of the code.

**What advantages do you see to test-first programming?**

**Do you plan to use it in your project, given your experience with CS201?**

**INCREMENTAL DESIGN:** The author suggests investing in the design of the system every day.  The primary point of this section is that "design is necessary, the question is when to design, and how much?"  The orthodox view, for decades, has been to design as much as possible up front, before any coding starts.  The idea has been to fully understand the system before coding it, and minimize/eliminate the need for changes after the design is created.  History and experience have shown that this goal is basically unattainable, and is inherently wasteful.  Design done close to use is more efficient, as there is a better understanding of the system, as it has come to exist at that time.

**The author talks about the need to refactor code as part of incremental design.  What is refactoring?  What are its benefits? What are its costs?**

**How do you identify when to design, and how much to design?**


