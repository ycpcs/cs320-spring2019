---
layout: default
title: "Lab 5: JDBC"
---

Getting Started
===============

Download [CS320\_Lab05.zip](CS320_Lab05.zip). Import it into your Eclipse workspace (**File&rarr;Import...&rarr;General&rarr;Existing projects into workspace&rarr;Archive File**). You will see a project called **CS320\_Lab05** in the Package Explorer.  (You will also need to have the **CS320_Derby** project in your workspace, which should already be there from [Lab 4](lab04.html).)

The lab contains a database called **test.db**, which is the [books database from Lecture 13](../lectures/lecture13.html).

**NOTE:** You must work individually on this lab.  It is imperative that everyone on your team be able to construct SQL queries, to establish a connection between a Java program and a SQL database, and to write SQL queries embedded in Java code.  This **WILL** come up on the exam.

Task
====
**NOTE:** You MUST refactor the name of the **CS320_Lab05** project to include your username - BEFORE YOU EXPORT IT AND SUBMIT IT TO MARMOSET.  Submissions that DO NOT adhere to that guideline will not be graded until they are refactored and resubmitted.

Example: If I was submitting this lab, I would refactor the **CS320\_Lab05** project to **CS320\_Lab05\_djhake2** as soon as I imported the project into Eclipse.

In the lab skeleton you will find a program called **TitleQuery** which demonstrates basic JDBC tasks such as loading a driver, connecting to a database, creating and executing a prepared statement, and iterating through results returned from a query.

Using **TitleQuery** as a model, write your own programs (separate classes with main() methods) to do the following:

1. Create class **BooksByAuthorLastNameQuery** that finds all books written by the author whose last name is specified by the user. Return the books in the same form as the **TitleQuery** program, but sorted in ascending order by **Title**.

2. Create class **InsertNewBookWithAuthor**: For an existing author, given the full (first and last) name of an author, a title, an ISBN, and the year that the book was published, insert the new book into the database.  Your program must first retrieve the existing author's **author\_id** before inserting the new book entry into the **books** table.

3. Modify **InsertNewBookWithAuthor** to allow insertion of a new book for an author that is not already in the database.  In this case, the program must first add the new author to the **authors** table, and then retrieve the auto-generated **author\_id** for the new author, before inserting the new book into the **books** table.  Hint: This requires multiple steps: attempt to retrieve the **author\_id**.  If the result set is empty, add the new author to the **authors** table.  Then, retrieve the **author\_id** that was automatically assigned for the new author.  Now you can insert the new book into the **books** table.  Use the SQL **insert** statement to insert the new tuple(s).

Submitting
==========

When you are done, submit the lab to the Marmoset server using the method below.

From a web browser
------------------

Save your project (**CS320\_lab05\_username**) to a zip file by right-clicking it and choosing

> **Export...&rarr;Archive File**

Upload the saved zip file to the **Lab05** project on the Marmoset server. The server URL is

> [https://cs.ycp.edu/marmoset/](https://cs.ycp.edu/marmoset/)