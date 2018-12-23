---
layout: default
title: "Lecture 6: Development Process"
---

Development processes
===================

[From Chapter 2 in UML Distilled]

A development process is a structured collection of practices and guidelines that all team members follow.

At the beginning of the process, we start with a problem that we want to solve.

At the "end" of the process, we have a finished system.

"End" is a bit misleading; typically, the software we develop will be continuously modified and extended. It's more accurate to say that at some point, the software will be deployed and officially "in-use".

Having a process helps the members of the team work together.

As we've discussed, two of the most-widely-used kinds of processes are waterfall and iterative.

Waterfall is intended to be a single iteration through the following phases:

> Requirements → Analysis → Design → Implementation → Testing → Deployment (Release)

An iterative process is a series of short iterations (2 weeks), each of which is a "mini-waterfall".

Waterfall Process
-----------------

Waterfall can be easy to understand, and might sound attractive in theory because it ostensibly provides a high level of determinism in relation to project scheduling, required resources, and overall cost and development time.  In reality, however, the waterfall model is both impractical and too inflexible since there is no opportunity for feedback in the process. For example, we may discover new requirements during the Analysis phase, we may (and most likely will) discover more about the problem during the Design phase, etc.   And those discoveries will cause an iterative jump further back in the process.  Another major weakness of the waterfall model is that estimation is very complex: it's extremely difficult to predict how long we will need to complete each stage. It is also risky to assume that the entire system will "come together" at the end of the Implementation phase.

Let's work through an example of an actual project implemented using the Waterfall process and discuss where the failure mechanisms can (and do) arise.  We'll also discuss why the Waterfall model is still so attractive to upper-level management.