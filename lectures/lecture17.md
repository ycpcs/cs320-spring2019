---
layout: default
title: "Lecture 17: Ensuring Code Quality"
---

# Ensuring code quality

Testing is the main way that we can ensure that the software is sufficiently free of defects.

However, there are many other techniques and practices that are valuable to us.

## Code Inspections, Pair Programming

A very useful way to ensure that software has high quality and is free from defects is to inspect the code after it's written.

Ideally, the person who inspects the code is not the same person who wrote the code.  If the goal of a code inspection is to try to find defects in the code, the person who wrote it has an inherent bias towards seeing it as correct.

We've all had the experience of trying to debug a program, and having someone walk by, look at the code, and immediately spot the error.

Advantages:

-  Humans are good at playing the "adversary"; trying to think of situations in which the code will fail

Disadvantages:

-  A thorough code inspection takes time.
-  Code inspections can be very tedious.
-  Developer time is expensive.
-  Developers tend to be assigned to other tasks.

Because code inspection is time consuming, it should not be be applied too frequently.  One idea is to conduct code inspection of only newly-written code.

Pair programming is a special case of code inspection.  In pair programming, all code (and unit tests) is written by a pair of developers, working together.  Basically, this is two people sitting at the same mouse/keyboard/monitor.

Pair programming works like a code inspection that is applied continuously; there is always a second set of eyeballs looking out for problems.

In general, we can reasonably expect code written using pair programming to contain fewer bugs than code written by a single developer.  One phenomenon that makes programming difficult is that it is often difficult to "see" a defect once it has been introduced; we often see what the "intent" of the code is, rather than looking at what the code actually does.  Pair programming takes advantage of the fact that two different people will have largely different "blind spots" - bugs that are "invisible", i.e.:

<img style="width: 500px;" src="figures/blindSpots.png" alt="Blind spots">
