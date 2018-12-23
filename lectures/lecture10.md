---
layout: default
title: "Lecture 10: OO Analysis"
---

Analysis is the development activity where we try to fully understand the problem domain, and build a model of the problem domain that will help us create a system that solves the problem we want to solve.

The input to analysis is the requirements. Requirements can be specified as high-level requirements, detailed use cases, etc.

Basic idea:

> *Textual analysis*: mine the input for the important terms and concepts in the problem domain
>
> Model the problem domain: using a UML class diagram
>
> > classes
> >
> > *relationships* between classes [question: what kinds of relationships are there?]
> >
> > important methods - those showing the important *behavior* of the classes

That's really all there is to analysis.

Analysis acts as a bridge between requirements and design. The analysis model will serve as a starting point for the design model.

Note that there is an important conceptual difference between the analysis and design models:

> the analysis model models the problem domain
>
> the design model models the solution domain

For example: a GUI is necessary to allow the user to play TicTacToe, but it is not part of the problem of playing TicTacToe. For this reason, the GUI classes will be part of the design model for TicTacToe, but not part of the analysis model.

The classes which are part of the analysis model are often referred to as the "object model".

In-class activity
=================

Analysis model for Uber (ride-sharing app and system).  We will work from a common set of scenarios, requirements, and use cases.
