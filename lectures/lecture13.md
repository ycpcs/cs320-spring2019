---
layout: default
title: "Lecture 13: Relational Databases"
---

A *relational database* is a system for storing and accessing data organized into *relations*.

A relation is a bag of *tuples*. Each tuple is an ordered sequence of *attributes*. Each attribute is a data value belonging to some data type. All of the tuples in a relation have the same number of attributes. In addition, the relation has a schema that is imposed on each tuple in the relation, specifying what the data type each attribute in each tuple will have. For example, the relation's schema might specify that the first attribute in each tuple is an integer.

The relation's schema also gives a name to each attribute. The attribute names give us a convenient way of referring to tuple attributes without having to say "the first attribute", "the fourth attribute", etc.

Typical relational databases support numeric and text data types as tuple attributes. Many relational databases also support "BLOBs" (Binary Large OBjects) as attributes. A BLOB is a large, uninterpreted chunk of data. BLOBs are useful for storing files, images, and other large chunks of data in a relational database.

Example relation
================

Let's say we are going to use a relational database to store information about books. We might define a relation called **books** to store information about each book:

> lastname | firstname | title | ISBN | published
> ---------------- | ----------------- | ----- | ---- | --------
> Hawking | Stephen | A Brief History of Time | 0-553-05340-X | 1988
> Hawking | Stephen | The Universe in a Nutshell | 0-553-80202-3 | 2001
> Hawking | Stephen | A Briefer History of Time | 0-553-80436-7 | 2005
> Mlodinow | Leonard | A Briefer History of Time | 0-553-80436-7 | 2005
> Hawking | Stephen | The Grand Design | 0-553-80537-1 | 2010
> Mlodinow | Leonard | The Grand Design | 0-553-80537-1 | 2010
> Adams | Douglas | The Hitchhiker's Guide to the Galaxy | 0-345-39180-3 | 1979
> Adams | Douglas | The Restaurant at the End of the Universe | 0-345-39181-0 | 1980
> Adams | Douglas | Life, The Universe and Everything | 0-345-39182-9 | 1982
> Adams | Douglas | So Long, and Thanks for all the Fish | 0-345-39183-7 | 1984

In this relation, there are five attributes called **lastname**, **firstname**, **title**, **ISBN**, and **published**. The first four attributes are strings, the last is an integer.

Databases with multiple relations
=================================

Databases will typically have many relations. One motivation for allowing multiple relations in a database is to avoid storing redundant information. For example, in the relation above, there are four tuples representing books by the same author, **Stephen Hawking**. Because the author name is represented four times, there is the possibility that this information might not be recorded consistently if the relation were modified.

We can avoid this redundancy by splitting the database into two relations, **books** and **authors**:

> The **books** relation:
>
> book\_id | author\_id | title | ISBN | published
> ---- | ---------- | ----- | ---- | ------
> 1 | 7 | A Brief History of Time | 0-553-05340-X | 1988
> 2 | 7 | The Universe in a Nutshell | 0-553-80202-3 | 2001
> 3 | 7 | A Briefer History of Time | 0-553-80436-7 | 2005
> 4 | 11 | A Briefer History of Time | 0-553-80436-7 | 2005
> 5 | 7 | The Grand Design | 0-553-80537-1 | 2010
> 6 | 11 | The Grand Design | 0-553-80537-1 | 2010
> 7 | 1 | The Hitchhiker's Guide to the Galaxy | 0-345-39180-3 | 1979
> 8 | 1 | The Restaurant at the End of the Universe | 0-345-39181-0 | 1980
> 9 | 1 | Life, The Universe and Everything | 0-345-39182-9 | 1982
> 10 | 1 | So Long, and Thanks for all the Fish | 0-345-39183-7 | 1984
>
> The **authors** relation:
>
> author\_id | lastname | firstname
> ---------- | ---------------- | -----------------
> 1 | Adams | Douglas
> 2 | Adams | Scott
> 3 | Breathed | Berkeley
> 4 | Chapman | Graham
> 5 | Cleese |  John
> 6 | Gilliam | Terry
> 7 | Hawking | Stephen
> 8 | Idle | Eric
> 9 | Jones | Terry
> 10 | Kahneman | Daniel
> 11 | Mlodinow | Leonard
> 12 | Newton | Isaac
> 13 | Palin | Michael
> 14 | Watterson | Bill

The **books** relation has been changed so that the author of each book is represented by a unique integer identifier, the **author\_id** attribute. This attribute also exists in the **authors** relation. So, the author of each book tuple in the **books** relation is represented indirectly, by reference to a matching author tuple in the **authors** relation.

Queries, SQL
============

A *query* is a request to retrieve information from a database.

**SQL**, the **Structured Query Language**, is a standard language for describing queries in relational databases. SQL is an interesting language because it is *declarative*: it describes *what* information is desired, but does not specify *how* that information is to be retrieved. It is the job of the database to figure out how to find the information requested by a query.

Example: let's say we want to find the titles of all books written by **Stephen Hawking**. In our original database, in which only the **books** relation exists, we could express that query as follows:

    select title
        from books
        where lastname = 'Hawking' and firstname = 'Stephen'

A SQL **select** statement specifies a query, and has three parts:

-   Which attribute values to retrieve. In the example above, only the **title** attribute is requested.
-   Which relations are involved in the query. In the example above, only the **books** relation is queried.
-   A *condition* describing which tuples contain the desired information. In the example above, the condition requires that tuples were **lastname = 'Hawking'** and **firstname = 'Stephen'** are desired.

This query will match multiple tuples in the **books** relation, and return the following **title** values:

> **A Brief History of Time**

> **The Universe in a Nutshell**

> **A Briefer History of Time**

> **The Grand Design**

Joins
=====

A *join* is a query which retrieves information from multiple relations. Joins are a powerful way to exploit *associations* between tuples in different relations. The idea is that a query retrieving information from multiple relations will specify a *join condition* which links attribute values in tuples of two relations.

Let's consider how to find the titles of all books by **Stephen Hawking** in the second version of the database, where we have two relations, **books** and **authors**. We will need to do a join of both relations in order to connect the author name and book title, which are now stored in different relations:

    select books.title
        from books, authors
        where books.author_id = authors.author_id and
              authors.lastname = 'Hawking' and authors.firstname = 'Stephen'

Note several interesting details of this query:

-   We are selecting **books.title** as the attribute to retrieve, explicitly noting that this attribute exists in the **books** relation
-   The **from** clause now specifies two relations, **books** and **authors**
-   The first part of the **where** clause, **books.author\_id = authors.author\_id**, is the join condition. It states that when considering pairs of tuples in the **books** and **authors** relations as candidates for retrieval, each tuple must contain the same value for the respective **author\_id** attributes.
-   In the **where** clause, each attribute is qualified by the name of the relation it is a part of. This is especially important when two relations have identically-named attributes, as is the case with the **author\_id** attributes of the **books** and **authors** relations.

Indices
=======

Obviously, a database system must be able to answer all queries by returning the requested information.

An important additional characteristic that database systems should have is that queries are answered *efficiently*, even if the database contains a large amount of data.

An *index* is an auxiliary data structure associated with a relation to increase the efficiency of queries on that relation. Specifically, an index is an auxiliary data structure which, given an attribute value or range of attribute values, quickly locates the tuple or tuples which match that value or range. An index may be applied to a single attribute, or to multiple attributes.

The idea is that an index helps the database focus the search for data matching a query by narrowing the number of tuples that must be checked.

Sequential scans
----------------

Consider queries involving a single relation. Any such query can be answered by performing a *sequential scan* over the tuples in the relation: checking each tuple to see if it matches the condition(s) specified in the **where** clause, and if so, returning the values of the selected attributes.

For very large relations, a sequential scan may do much more work than necessary. In particular, the **where** clause may have sub-conditions that are met by only a very small number of tuples: we say that a condition matched by only a small number of tuples has high *selectivity*.

To answer queries as efficiently as possible, the database should limit its scan to as small a subset of tuples as possible. This can be done using an *index*.

For example: let's say that in the book database, we will frequently need to search for authors by last name. To make those queries more efficient, we can build an index on the **lastname** attribute. Queries such as

    select author_id from authors where lastname = 'Hawking';

can be answered efficiently because the index on **lastname** will allow the database to ignore tuples in which the value of that attribute is not 'Hawking'.
