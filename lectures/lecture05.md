---
layout: default
title: "Lecture 5: GWT, User interfaces"
---

GWT
===

GWT = [Google Web Toolkit](https://developers.google.com/web-toolkit/)

Translates Java into Javascript that runs in the web browser. The GWT classes strongly resemble traditional GUI toolkits such as Java Swing, Windows Forms, etc.

One way in which GWT is *not* like traditional GUI toolkits: part of your application runs on the client, but part of it runs on the server. Usually, the server-side of the application uses a database to load and store persistent data.

RPC
---

GWT provides an *RPC* (remote procedure call) mechanism to make it easy for code in the client to call methods on the server. Behind the scenes, a remote procedure call works like this:

-   the client-side code invokes an RPC method, passing Java objects as parameters, along with a *callback object* that will receive the (eventual) result of the call
-   the data in the Java objects is serialized (encoded) to form the contents of an HTTP message
-   the client's HTTP message is sent to the server
-   the server receives the client's message and determines which server-side method to call
-   the Java object data in the client's HTTP message is deserialized (decoded) to turn it back into Java objects
-   the deserialized Java objects are passed to the server-side method
-   the result value of the server-side method is serialized and sent back to the client as an HTTP message
-   the result value in the server's HTTP method is deserialized by the client and passed to the client's callback object

GWT RPC is *asynchronous*, meaning that when a remote procedure call is made, the client code does not wait for the response to be received by the server. Instead, the client's callback object is notified of the server's response at some later time. This is necessary because some amount of time will elapse between the call and the server's response being received, and it is important that the user interface remains responsive during this time.

User Interfaces
===============

You have used lots of programs that have GUI user interfaces, so you're already familiar with the basic elements: text, buttons, lists, menus, etc.

In this course, we will focus on how to implement user interfaces using GUI toolkits such as GWT. There is one principle that, above all else, captures the essence of how a user interface should be added to a system:

> The problem domain classes **never** know about the user interface

Let's consider some of the advantages of adhering to this principle:

-   All of the problem domain code can run without a user interace: in unit tests, as a library callable from other programs, etc.
-   Multiple user interfaces can be supported easily: for example, command line, Swing, GWT, etc.
-   The design of the system is simpler because the problem domain code and the user interface are separate, and the complexity of the user interface does not leak into the problem domain code

Another way of thinking about this principle is that the user interface is a way for the user to visualize and interact with problem domain objects.

User Interfaces in GWT
======================

GWT has pretty much all of the user interface components that you would expect: labels, buttons, text boxes, drop down lists, etc. However, because GWT components (which are called *widgets* in GWT) run in a web browser, they are actually implemented as elements of the DOM (Document Object Model) tree in the web browser. To a large extent, you can use GWT without having to know about the underlying HTML/DOM nature. However, for controlling the layout and appearance of GWT widgets, it is sometimes necessary to use CSS.

Some basic GWT UI concepts and terms:

-   *Entry point* - the class containing the "entry point" of the application. This is similar to the **main** method of a standard Java application. The main purpose of the entry point is to create the user interface of the application and attach it to the web page in which the application is displayed.
-   *Widget* - any user interface element. This includes things like buttons and textboxes (the **Button** and **TextBox** classes, respectively), but also containers (panels). All widgets implement the **IsWidget** interface or extend the **Widget** class.
-   *Panel* - a container for widgets. Examples are **FlowPanel** (which is really an HTML **div** element), **LayoutPanel** (a **div** element that allows flexible positioning of child widgets placed within it), and **DockLayoutPanel** (a resizable center panel with optional top, bottom, left, and right panels around it.) Panels are the key to laying out user interface elements.

Views
=====

A *view* in a user interface is a user interface component for visualizing a problem domain object and allowing the user to interact with it.

For example: consider a text box. You can think of a text box as a view for a string: it displays a string, and when the user types text it changes the string.

Creating a rich user-interface can be simplified by creating views for the model objects that will be displayed in the user interface. Views can be hierarchical: a view may be created by combining several other views.
