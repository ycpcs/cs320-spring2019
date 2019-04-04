---
layout: default
title: "Resources"
---

This page links to useful resources.

Hypertext Mark-Up Language (HTML) and Cascading Style Sheets (CSS)
===================================================================

[w3Schools.com](http://www.w3schools.com): **Go here first for HTML/CSS, SQL, JavaScript, PHP tutorials**

[Free Code Camp](https://www.freecodecamp.org): Covers HTML/CSS (you need to create a free account)

[Basic HTML Tutorial](http://www.htmliseasy.com/html_tutor/index.html): Tutorial site for Basic HTML

[HTML Forms Tutprial](http://www.htmliseasy.com/form_tutor/lesson01.html): Tutorial site for creating HTML Forms

[HTML Tables Tutorial](http://www.htmliseasy.com/table_tutor/index.html): Tutorial site for creating HTML tables

[Basic CSS Tutorial](http://www.htmliseasy.com/css_tutor/index.html): Tutorial site for using CSS

[CSS Reference](http://www.htmliseasy.com/wdgcss/index.html): CSS reference guide from Web Design Group

[Bootstrap](http://www.w3schools.com/bootstrap/default.asp): A visual editor for creating web front-ends

[Brackets](http://brackets.io/): A visual editor for working on HTML/CSS

Java Server Pages (JSP) and Java Standard Tag Library (JSTL)
============================================================

[JSP Tutorial](http://www.tutorialspoint.com/jsp/index.htm): Tutorial site for working with JSPs (note that this references Apache Tomcat, but much of it should apply to Eclipse Jetty)

[JSTL Tutorial](http://www.tutorialspoint.com/jsp/jsp_standard_tag_library.htm): Tutorial site for working with JSTL (linked from above site)

[Session Information](http://www.tutorialspoint.com/jsp/jsp_session_tracking.htm): Creating and using session information (linked from above site)

JavaScript (JS)
===============

[JavaScript Tutorial - w3schools](https://www.w3schools.com/js/default.asp): JavaScript tutorial w/sandbox from **w3shools.com**

[JavaScript Tutorial](http://www.htmliseasy.com/javascript/index.html): Basic JavaScript tutorial

[Free Code Camp](https://www.freecodecamp.org): Covers various JavaScript versions (you need to create a free account)

Unified Modeling Language (UML)
===============================

[UML Diagrams](http://usna86-techbits.blogspot.de/2012/11/uml-class-diagram-relationships.html): A concise explanation of UML relationships and diagrams

[Violet UML Download](violetumleditor-2.1.0.jar): Use Violet UML for your project UML diagrams

Git, GitHub, and eGit
=====================
[Git Branching Demo](https://learngitbranching.js.org/): Great JavaScript-based demo for using branches in Git

[Free Code Camp](https://www.freecodecamp.org): Covers Git and GitHub (you need to create a free account)

[Git Website](https://git-scm.com): Everything you ever wanted to know about Git, but were afraid to ask

[Git eBook: ProGit v2](https://git-scm.com/book/en/v2): Available free in PDF form

[Git Reference Manual](https://git-scm.com/docs): Git command-line reference

[Git Videos](https://git-scm.com/videos): Tutorials on getting started with Git

[Git Downloads](https://git-scm.com/downloads): Git Clients and Tools

[GitHub - Remote Repository Host](https://github.com/): Teams will create their remote repositories on GitHub

[eGit Home Page](https://www.eclipse.org/egit/): Documentation and tutorials on setting up and using eGit

[eGit: Fetching and merging changes from within Eclipse](fetchMerge.html)

Relational Databases and Structured Query Language (SQL)
========================================================

[SQL Tutorial - w3schools](https://www.w3schools.com/sql/default.asp): **Go here first for SQL tutorials w/sandbox from w3schools.com**

[Free Code Camp](https://www.freecodecamp.org): Covers SQL Databases (you need to creaate a free account)

[CS320\_Derby.zip](CS320_Derby.zip): Eclipse project with jarfiles for Apache Derby (relational database)

> <div class="callout"><b>When you implement the persistence layer using Derby for your team project</b>: when specifying the JDBC URL in the code where you connect to the database, you should use an absolute file name for the database name. For example, <code>jdbc:derby:H:/mydatabase.db;create=true</code> (this will create the database as <code>H:/mydatabase.db</code>).  If you use a relative file name, your web application will probably not find the database (because it runs in the <code>war</code> directory rather than the root directory of the project).</div>

Email address validation
========================

[A Java email validator class using regex (regular expressions)](https://www.mkyong.com/regular-expressions/how-to-validate-email-address-with-regular-expression/)


CS320 Library Example Project
=============================

[CS320\_LibraryExample-2019.zip](CS320_LibraryExample-2019.zip): Eclipse project that ties the [Web Applications Lab](../labs/lab02.html) together with the [ORM Lab](../labs/lab06.html).  This application places a web front-end on the SQL transactions from Lab06, as well as provides examples for creating a Derby database from CSV files, how to use session information after login, and how to use JSTL to display a list of complex objects in a JSP.  It has been updated to incorporate a many-to-many (M2M) relationship between **Books** and **Authors**, using a junction table (**booksAuthors**) that cross-references **book_id**'s with **author_id**'s.  It also contains some basic (non-exhaustive) JUnit Tests for testing the Derby database queries.

> <div class="callout"><b>NOTE: You are free to incorporate any of this code into your team project(s) - as long as you cite the source in your code, and refactor the names from **Lab02** and **Lab06** to something that pertains to your project.</b></div>

After you download the ZIP file, extract it into a new Java workspace separate from the others that you have used in the past.  This project is composed of 4 separate Java projects (**CS320_Jetty**, **CS320_Derby**, **CS320_LibraryExample_Lab02**, and **CS320_LibraryExample_Lab06**).

Before running the project, open up **DerbyDatabase.java** under **CS320_LibraryExample_Lab06->src->edu.ycp.cs320.booksdb.persist** and edit the Derby database location in the **connect()** method so that it has the absolute path where you want your database to be located.  Do the same thing in **SQLDemo.java** in the **main()** method.  If you don't change it, the default database location will be **C:/CS320-2019-LibraryExample-DB/**.

**DO NOT LOCATE YOUR DATABASE WITHIN THE LibraryExample PROJECT.**  You will likely be using the LibraryExample as the basis for your team project, and placing the database within the project will eventually result in numerous **Git** conflicts when you start working as a team from a common **Git** repository.

Run **DerbyDatabase.java** as an application to create the Library database from the **authors.csv**, **books.csv**, and **bookAuthors.csv** files. It might take a few seconds for the application to create the DB - you will see it in the console.  Afterwards, **library.db** will show up as a folder under the **C:/CS320-2019-LibraryExample-DB/** folder.  If you changed the LibraryExample database location, you will find **library.db** at that location.

Run **SQLDemo.java** as an application so that you can issue SQL queries to the LibraryExample DB.  If this step works - if you can issue queries and SQLDemo can locate the DB - then you have correctly updated the two Java source files from above.

To run the web application, first stop **SQLDemo**, then run **CS320_LibraryExample_Lab02->Main.java** as a Java application, followed by entering the following URL in your web browser:

> [http://localhost:8081/lab02/login](http://localhost:8081/lab02/login)

There are currently two sets of login credentials hard-coded into the application: User name: **student** with PW: **ycp** and User name: **faculty** with PW: **E&CS**.  After you have successfully logged in, the user name will be passed around as part of the Session information, and each subsequent servlet checks for a valid **Session** (a non-null "user" attribute) before responding to the request.  Note that this is **NOT** a secure method for handling credentials, but is used as an example for passing around and checking **Session** information.

**WARNING: You will receive an Academic Integrity Violation, as well as automatically fail the course, if you submit code as part of your Lab06 solution that was taken from any version of the LibraryExample Project that has ever been provided as part of this course.**

<!-- Commenting out Library Example until it's needed
-->