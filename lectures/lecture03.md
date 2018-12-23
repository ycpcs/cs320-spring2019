---
layout: default
title: "Lecture 3: Dynamic HTML, JavaScript, jQuery"
---

Dynamic HTML
============

An HTML document is a tree. Each node of the tree is an element or a chunk of text. The visual appearance of the tree nodes can be specified using CSS. The data structure representing the tree of nodes is called the **DOM**, for **D**ocument **O**bject **M**odel.

In a static HTML document, the tree is fixed.

In a *dynamic* HTML document, the tree changes in response to events (including user input events): nodes can be added or removed, and CSS properties can be changed. Dynamic HTML allows a full GUI to be implemented in a web page!

Because dynamic HTML supports arbitrary runtime behavior, it needs a programming language to specify the behavior. This language is JavaScript.

JavaScript
==========

Features:

-   Dynamically typed
-   Object-oriented (every value is an object)
-   Syntax is superficially similar to Java
-   Supports closures (anonymous functions which can access/modify variables in their lexical scope)

When using JavaScript to implement dynamic HTML, the general idea is to use JavaScript to access elements in the DOM tree and call methods on them to change their properties, register event handlers, etc.

jQuery
======

Because doing operations on elements of the DOM tree is so important in JavaScript, various libraries have been implemented to make it easy to do this. One of the most important and widely-used libraries is [jQuery](http://jquery.com).

Using jQuery typically involves selecting one or more nodes in the DOM tree: this is the "query" part of jQuery. Then, you perform some operation on the selected nodes.

Examples
========

Here are some examples of fun things you can do with jQuery.

Showing/Hiding Elements
-----------------------

~~~ html

    <!DOCTYPE html>

    <html>
      <head>
        <style type="text/css">
        #clickhere {
          width: 120px;
          background-color: #80ff80;
          color: #000080;
          font-size: 150%;
          font-weight: bold;
          border: 4px solid #000080;
          margin-bottom: 10px;
        }

        #sometext {
          display: none; /* hide this div initially */
          background-color: #FAFAD2;
          font-style: italic;
          padding: 6px;
          border: 1px solid black;
        }
        </style>

        <!-- Get jQuery from google CDN -->
        <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js" type="text/javascript"></script>

        <script type="text/javascript">
          $(document).ready(function() {
            $("#clickhere").click(function() {
              $("#sometext").slideToggle();
            });
          });
        </script>
      </head>

      <body>
        <div id="clickhere">
          Click here!
        </div>

        <div id="sometext">
          Oh freddled gruntbuggly<br />
          thy micturations are to me<br />
          As plurdled gabbleblotchits on a lurgid bee.<br />
          Groop I implore thee, my foonting turlingdromes.<br />
          And hooptiously drangle me with crinkly bindlewurdles,<br />
          Or I will rend thee in the gobberwarts with my blurglecruncheon, see if I don't!
        </div>
      </body>
    </html>
	
~~~

[Link](lecture03/showhide.html)

Some things to notice:

The **&lt;script&gt;** tag references some JavaScript code, either in a separate document or inline

jQuery operations involve calling a function called "$".

**$(document).ready(...)** executes some code when the web page is fully loaded, meaning that the entire DOM tree is in place and all JavaScript code has been loaded.

JavaScript of the form **function() { ... }** is a *closure*. A closure is an anonymous function which can use variables defined in the current scope.

A jQuery call of the form **$("***selector***")** selects all DOM elements matching the given selector. The selector syntax is the same as for selectors in CSS rules. So, for example, **$("\#clickhere")** selects the element with the id **clickhere**. Note that the call does not return a DOM element (or a list of DOM elements): it returns a "jQuery object" which represents the results of the search. The idea is that when you call a method on a jQuery object, you are effectively performing an operation on all DOM elements that matched the query.

For example, the **slideToggle()** method on a jQuery object performs an animation that shows or hides the matched element(s).

Client-side data processing
---------------------------

~~~ html

    <!DOCTYPE html>

    <html>
      <head>
        <style type="text/css">
        td.label {
          font-weight: bold;
          text-align: right;
        }
        </style>

        <!-- Get jQuery from google CDN -->
        <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js" type="text/javascript"></script>

        <script type="text/javascript">
          function getFirstNumber() {
            return parseFloat($("#firstNumber").val());
          }

          function getSecondNumber() {
            return parseFloat($("#secondNumber").val());
          }

          $(document).ready(function() {
            $("#addButton").click(function () {
              $("#result").text(getFirstNumber() + getSecondNumber());
            });
            $("#subtractButton").click(function () {
              $("#result").text(getFirstNumber() - getSecondNumber());
            });
            $("#multiplyButton").click(function () {
              $("#result").text(getFirstNumber() * getSecondNumber());
            });
            $("#divideButton").click(function () {
              $("#result").text(getFirstNumber() / getSecondNumber());
            });
          });
        </script>
      </head>

      <body>
        <table>
          <tr>
            <td class="label">
              First number:
            </td>
            <td>
              <input id="firstNumber" type="text" size="15" />
            </td>
          </tr>
          <tr>
            <td class="label">
              Second number:
            </td>
            <td>
              <input id="secondNumber" type="text" size="15" />
            </td>
          </tr>
          <tr>
            <td class="label">
              Result:
            </td>
            <td>
              <span id="result"></span>
            </td>
          </tr>
        </table>

        <button id="addButton">Add</button>
        <button id="subtractButton">Subtract</button>
        <button id="multiplyButton">Multiply</button>
        <button id="divideButton">Divide</button>
      </body>
    </html>

~~~

[Link](lecture03/data.html)

Some things to notice:

Standalone functions can be defined using **function** *funcName* **(** *params* **)**.

**input** elements with attribute **type="text"** can be used as textboxes.

**button** elements are buttons: the jQuery **click(...)** method can be used to install a click handler.

The javascript **parseFloat(...)** function converts a string to a (floating-point) number.

The jQuery **val()** method gets the value of an input element (such as a text box.)

The jQuery **text(...)** method sets the text of an element. The code above uses it to change the text of a **span** element to the result of an arithmetic operation.

Drawing on a canvas
-------------------

~~~ html

    <!DOCTYPE html>

    <html>
      <head>
        <!-- Get jQuery from google CDN -->
        <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js" type="text/javascript"></script>

        <script type="text/javascript">
          $(document).ready(function() {
            var colors = [ '#FF0000', '#00FF00', '#0000FF' ];

            var circles = [];

            $("#makeCircle").click(function() {
              var x = Math.floor(Math.random() * 640);
              var y = Math.floor(Math.random() * 480);

              circles.push({ x: x, y: y, color: colors[Math.floor(Math.random() * 3)] });
            });

            window.tick = function() {
              var ctx = $("#canvas").get(0).getContext("2d");
              ctx.clearRect(0, 0, 640, 480);

              for (var i = 0; i < circles.length; i++) {
                var c = circles[i];

                ctx.fillStyle = c.color;
                ctx.beginPath();
                ctx.arc(c.x, c.y, 20,0, Math.PI*2, true);
                ctx.closePath();
                ctx.fill();

                c.y += 5;
              }

              setTimeout("tick()", 100);
            };

            setTimeout("tick()", 100);
          });
        </script>
      </head>

      <body>
        <div>
          <canvas id="canvas" width="640" height="480"></canvas>
        </div>

        <button id="makeCircle">Make circle</button>
      </body>
    </html>

~~~

[Link](lecture03/canvas.html)

Some things to notice:

JavaScript variables are introduced using the **var** keyword. Notice that they have no type.

A **canvas** element can be used as a 2-D drawing surface.

The **circles** array contains objects created as:

> { x: *value*, y: *value*, color: *value* }

where **x**, **y**, and **color** are the fields. These objects represent circles that will be rendered in the canvas.

The **setTimeout** method schedules a function to be called after a specified timeout (in this case, 100 milliseconds).

By increasing the values of the **y** fields of the circle objects on each timer tick, an animation is created.
