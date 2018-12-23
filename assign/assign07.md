---
layout: default
title: "Assignment 7: Using Static Analysis"
---

**Due: Monday, April 18h by 11:59 PM**

This is an **Individual** assignment

Your Task
=========

Download the latest version of FindBugs (<http://findbugs.sourceforge.net>). Find an open-source software application or library which is written in Java.  Use FindBugs to analyze the application.

When you set up the project in FindBugs, make sure that only the Jar files that are properly part of the application are selected in the "Class archives and directories to analyze" section; all other Jar files should be entered in "Auxiliary class locations". Also, make sure the application's source directory or directories are added under "Source directories", so that the application source code will be visible when you view the reported warnings.

> **Note**: The source directory of a Java project is often called **src** or **src/java**, and will typically contain subdirectories with names of top-level internet domain names, such as **com**, **org**, **net**, etc.

Find one static analysis warning reported in the "Correctness" category that appears to identify a significant bug in the application. (Infinite recursive loops, null pointer exceptions, and redundant null checks are good candidates.)

Write a brief report containing the following information:

1.  A screen shot of FindBugs displaying the warning. Make sure the affected application source code is visible in the screen shot.
2.  Explain why the code identified by the warning contains a bug.

Submitting
==========

Submit a PDF document to the Marmoset server as **assign07**. The server URL is

> <https://cs.ycp.edu/marmoset>

<div class="callout">
<b>Important</b>: Only submissions in PDF format will be accepted.
Do not submit a document in any other format!
</div>
