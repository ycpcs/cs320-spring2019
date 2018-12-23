---
layout: default
title: "Lab 1: HTML and CSS"
---

Your Task
=========

Use HTML and CSS to create your own personal resume, using the following example as a template (click for full-size):

> <a href="images/lab01/resume.png"><img style="width: 500px;" src="images/lab01/resume.png" /></a>

The text in the page title should be rendered in small caps.

The page title and the text of section headers should be dark blue.

The resume should have a title running across the top (with dark blue bars above and below).

The content area should be to the left and the sidebar (contact info) should be to the right.

Use **div** and **span** elements with id and class attributes to specify the body of the HTML document. All visual styling should be done separately in CSS rules.

**NOTE:** You must work individually on this lab.  It is imperative that everyone on your team be able to develop web page layouts using HTML and CSS.  This **WILL** come up on the exam.

Hints
-----

For additional information, I highly recommend this [great tutorial site for HTML, CSS, Java Script, SQL, PHP](http://www.w3schools.com).

Try floating the content and sidebar divs to the left.

Use **width** properties to set the widths of the content and sidebar divs. For example, I have

    width: 540px;

on my content div, and

    width: 240px;

on my sidebar div.

You can use an unordered list for experience section: something like

    <ul>
        <li>Item 1</li>
        <li>Item 2</li>
    </ul>

Use the **border** property to draw a solid border around the sidebar.

Use the **border-top** and **border-bottom** properties to draw the horizontal lines above and below the title.

You can use the tag

    <br />

to end a line of text.

You will need to use margins to spread things out a bit. (For example, you should have some vertical space between resume sections.)

Submitting
==========

When you are done, submit the lab to the Marmoset server using the method below.


From a web browser
------------------

Save your HTML and CSS files to a zip file named **CS320_Lab01.zip**.

Upload the saved zip file to the Marmoset server as **lab01**. The server URL is

> [https://cs.ycp.edu/marmoset/](https://cs.ycp.edu/marmoset/)

