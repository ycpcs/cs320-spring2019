---
layout: default
title: "Lab 6: ORM"
---

# Getting Started

Download [CS320\_Lab06.zip](CS320_Lab06.zip). Import it into your Eclipse workspace (**File&rarr;Import...&rarr;General&rarr;Existing projects into workspace&rarr;Archive File**). You will see a project called **CS320\_Lab06** in the Package Explorer.   (You will also need to have the **CS320_Derby** project in your workspace, which should already be there from [Lab 4](lab04.html).)

**NOTE:** You MUST refactor the name of the **CS320\_Lab06** project to include your username - BEFORE YOU EXPORT IT AND SUBMIT IT TO MARMOSET.  Submissions that DO NOT adhere to that guideline will not be graded until they are refactored and resubmitted.

Example: If I was submitting Lab06, I would refactor the **CS320\_Lab06** project to **CS320\_Lab06\_djhake2** as soon as I imported the project into Eclipse.

Start by creating **test.db**, which is the [books database from Lecture 13](../lectures/lecture13.html).  Execute the **DerbyDatabase** class as a Java application: you should see the following output:

    Creating tables...
    Loading initial data...
    Success!

If you refresh your **CS320_Lab06** project, you should see the **test.db** directory.

**NOTE:** You must work individually on this lab.  It is imperative that everyone on your team be able to construct SQL queries, to establish a connection between a Java program and a SQL database, and to write SQL queries embedded in Java code.  This **WILL** come up on the exam.

**You will also automatically fail the course, as well as receive an Academic Integrity Violation, if you submit work that was completed by someone else, and/or submit any portion of code taken from the Library Example Project that I provide as part of the course.**

# Task

In the lab skeleton you will find a program called **TitleQuery** which demonstrates using an ORM interface to find all books that have the title entered by the user (along with the author information).

Your task is very similar to [Lab 5](lab05.html), except that rather than directly executing database queries/statements, you will add methods to the **IDatabase** interface and implement them in **BOTH** **FakeDatabase** and **DerbyDatabase**.

Tasks:

Using **TitleQuery** as a model, write your own programs (separate classes with main() methods) to do the following:

1. Create class **BooksByAuthorLastNameQuery** that finds all books written by the author whose last name is specified by the user. Return the books in the same form as the **TitleQuery** program, but sorted in ascending order by **Title**.  This is the same SQL query as **problem 1** from [Lab 5](lab05.html).  You are welcome to reuse your code from that solution.

2. Create class **InsertNewBookWithAuthor**: Given the full (first and last) name of an author, a title, an ISBN, and a publish year, insert the book into the database. The program should add a new tuple to the **authors** table if the author doesn't already exist. If the author already exists, the program should use that author's **author\_id**.  Use the SQL **insert** statement to insert the new tuple(s).  **NOTE:**  This is the same set of SQL queries as **problem 3** from [Lab 5](lab05.html).  You are welcome to reuse your code from that solution.

## Hints

For the first task, add the following method to **IDatabase**:

    public List<Pair<Author, Book>> findAuthorAndBookByAuthorLastName(String lastname);

Implement it in **FakeDatabase** and **DerbyDatabase**.  Start by implementing the method in **FakeDatabase** (just have the method in **DerbyDatabase** throw an **UnsupportedOperationException**.)

For the second task, first do a query to see if the author exists.  If the author doesn't exist, insert the new author into the **authors** table.  (Note: you will want to allow the database to automatically assign an **author\_id**).  Then, retrieve the **author\_id** so that you can insert a new tuple into the **books** relation (again, the database will automatically assign a **book\_id**).  Note that the entire operation should be executed as part of a **single transaction**.

Submitting
==========

When you are done, submit the lab to the Marmoset server using the method below.

From a web browser
------------------

Save your project (**CS320\_lab06\_username**) to a zip file by right-clicking it and choosing

> **Export...&rarr;Archive File**

Upload the saved zip file to the **Lab06** project on the Marmoset server. The server URL is

> [https://cs.ycp.edu/marmoset/](https://cs.ycp.edu/marmoset/)