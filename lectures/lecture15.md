---
layout: default
title: "Lecture 15: ORM, Designing a Persistence Layer"
---

# ORM

ORM is *Object-Relational Mapping*, meaning the use of relations in a relational database to store object data.  Since all data in an object-oriented system is represented as objects, having an effective approach for ORM is an important requirement.

In this lecture we will go over some principles for implementing ORM.

# Principles

Implementing ORM does not need to be complicated.  Here are some principles to keep in mind.

## Principle 1: ORM is for storing objects

The point of ORM is to store object data persistently. It is the *objects* that are important, not the database.   The database exists only to store object data.  The design of the database (the relations and the way they are connected to each other) follows the way the classes in the system are related to each other.

Another way of looking at this is that your ORM approach should allow your system to be completely oblivious to the fact that the relational database is there.  It should just give the system a way to load and store object data.

## Princple 2: Create an interface for your persistence operations

Following from Principle 1, we don't want the code in the system that performs persistence operations to be aware of what mechanism is being used to load and store object data.  So, you should define an interface to describe the *persistence operations*, which are the methods that load and store objects.

Each persistence operation should

* Load object data from the database (returning one or more objects), or
* Store object data in the database (taking one or more objects and storing their data), or
* Do both (load and store objects)

## Principle 3: Create a "fake" implementation of the persistence interface

One of the most important motivations for creating an interface to describe the persistence operations is that it allows you to define multiple implementations of your persistence operations.

The first implementation you create should not actually use a database at all.  It should implement the persistence operations using in-memory containers such as **ArrayList**s.

Having this "fake" persistence implementation yields the following benefits:

* It allows you to make progress on the rest of the system: you are never held up because of difficulty integrating the actual relational database
* It allows you to write unit tests for the controllers that perform persistence operations (unit testing with an actual database, especially one that requires a server, can be difficult)

Eventually, you will want to create a "real" implementation of the persistence interface that uses a real database, but the "fake" implementation should be maintained alongside the real implementation.

## Princple 4: Use dependency injection to access the persistence interface

As noted earlier, your system should not know or care what implementation of the persistence interface it is using.  A technique called *dependency injection* allows the implementation of the persistence interface to be created dynamically (when the program runs).

Here is a very simple approach to dependency injection.  Let's say the persistence interface is called **IDatabase**.  A class called **DatabaseProvider** could be defined as follows:

    public class DatabaseProvider {
        private static IDatabase theInstance;
        
        public static void setInstance(IDatabase db) {
            theInstance = db;
        }
        
        public static IDatabase getInstance() {
            if (theInstance == null) {
                throw new IllegalStateException("IDatabase instance has not been set!");
            }
            return theInstance;
        }
    }

Sometime early in the initialization of your system (before any code that performs persistence operations is executed), a call to **setInstance** should be used to install an object that implements the **IDatabase** interface.  

All of the code in the system that needs to perform persistence operations should then use

    DatabaseProvider.getInstance()

to get a reference to the object that implements **IDatabase**.

# Practical considerations

There are many practical details that need to be worked out to implement ORM.  This is not an exhaustive list, but does highlight some things you should keep in mind.

[Lab 6](../labs/lab06.html) has a small but realistic example of a database application with an ORM layer that should be useful as a reference.

## Make your model objects POJOs

A "Plain Old Java Object", or [POJO](http://en.wikipedia.org/wiki/POJO), is an object belonging to a Java class that consists of fields and getter/setter methods.

Using POJOs simplifies the task of mapping classes/objects to database relations/tuples because each field of the POJO class maps onto an attribute (column) of the corresponding relation (table).

All of your model classes should have

* a constructor that does not take any parameters
* getter methods for each field
* setter methods for each field

You may implement some behavior in your model classes: however, it may be easier to move behavior as much as possible to controller classes, leaving the model classes as passive containers for data.

## Automate the creation of the database and the loading of initial data

When you create your "real" implementation of the persistence interface, write code that will create the database and load any required initial data.

## Use try/finally to ensure that database resources are cleaned up

In JDBC, all **Connection**, **PreparedStatement**, and **ResultSet** objects must be closed when they are no longer needed.  Always use the **try/finally** construct to ensure that these objects are cleaned up.  This is especially critical for web applications (and other server applications), where the system will run for an extended period of time, and resource leaks will degrade performance and possibly result in a crash.

## Use transactions to guarantee atomicity

Sometimes, your persistence implementation may need to execute multiple SQL queries or statements to perform a persistence operation.  For example, before inserting a new book in the database, using a query to check whether or not the author already exists, and if not, adding a new tuple to the authors relation.

Because web applications (and most other types of server applications) will support many clients concurrently, the persistence implementation needs to ensure that data remains consistent.  For example, the system should guarantee that if two clients are attempting to add different books written by the same author to the database, only a single tuple will be added to the authors relation for that author.

A [database transaction](http://en.wikipedia.org/wiki/Database_transaction) is a technique that allows the database application to group a sequence of database operations into a single transaction that will either succeed or fail in its entirety.  So, if two transactions attempt to add the same author, only one will succeed.

Executing transactions in JDBC is relatively straightforward: call **setAutoCommit(false)** on the **Connection** object, and then call the **commit()** method on the connection after executing all queries/statements that are part of the transaction.  Note that if two transactions interfere with each other, one will fail, typically with an exception indicating deadlock.   So, it may be necessary to retry a transaction several times until it can be committed successfully.  Creating objects to represent transactions can help, since you can create an "execute transaction" method that will attempt to execute the transaction as many times as required until it suceeds, avoiding the need to replicate the retry code in many places.

<!-- vim:set wrap: ­-->
<!-- vim:set linebreak: -->
<!-- vim:set nolist: -->
