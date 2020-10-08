---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Introduction to Databases
# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Understand the relational model and become proficient with basic SQL querying

# (Optional) Link to an image that represents your blog post.
# The aspect ratio should be ~16:9.
image: /assets/img/default.jpg

# You can hide the description and/or image from the output
# (only visible to search engines) by setting:
# hide_description: true
# hide_image: true

# (Optional) Each post can have zero or more categories, and zero or more tags.
# The difference is that categories will be part of the URL, while tags will not.
# E.g. the URL of this post is <site.baseurl>/hydejack/2017/11/23/example-content/
categories: [CS 101]
tags: []
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

A **database** supports the storage and retrieval of **structured** data. At its most basic, 
a database is just a way of storing and organizing information in such a way that it can be easily
accessed and managed. 

## Database Lingo

In a database, the data are organized into **tables** (aka **entities**), and those tables can be **joined**
together using **keys**. Each table has **rows** (aka **records**) that represent a single member of the entity
(e.g., a movie, a customer, an invoice). Each attribute has a particular data type such as a string of text, an integer, a date/time, etc. 
The **columns** are also known as **fields** or **attributes** because they further describe the entity. 

A **primary key** is an attribute that **uniquely identifies** each record in the table so you can make sure there are no duplicates.
Sometimes the best thing to use for a primary key is an arbitrary integer, such as your student-id. This is useful because in the student data table,
records for 'John Smith' with ID 2134 and 'John Smith' with ID 3412 are seen as two separate records, or in terms of the entity, as two separate students.

A **foreign key** is an attribute that points to or **references** the primary key of a different table. Foreign keys let us join together
multiple tables in a database. 

![Data Table](https://i.stack.imgur.com/IbPuu.png)

Can you identify the entity/entities, the attributes, and the number of records in the above data table? 

![Database Schema](https://i.stack.imgur.com/XZROF.png)

Can you identify the entities, their attributes, and the number of records in the above **database schema**?

**Query**: a single action taken on a database. Often, we use the  programming language **SQL** (Structured Query Language) to query/describe a request for information
from a database. "Hey Alexa, could you get me all the names of the movies are coming out in December 2018?" might look something like `SELECT movie.name FROM movies WHERE movie.month = 12;`
In addition to selecting information, we could `INSERT`, `UPDATE`, and `DELETE`. 

**Transaction**: a transaction is a sequence of queries that make up a unit of work performed against a database. For example, Alice is paying Bob $20 for movie tickets. This
is a transaction that consists of two `UPDATE` operations: reducing Alice's balance by $20 and increasing Bob's.

**ACID** is an acronym that says a transaction only qualifies as a transaction if it follows these four "ACID" properties:
- **Atomicity**: each transaction is a unique, atomic unit of work. If one query fails, the data remains unchanged--all or nothing. Alice won't lose $20 if Bob isn't paid.
- **Consistency**: all data written to the database is subject to any of the queries defined. When a transaction is completed, all the data must be left in a consistent state.
- **Isolation**: data changed in a transaction are not visible to other transactions until the original transaction is complete.
- **Durability**: changes made and completed by a transaction are stored and available in the database, even if your system fails.

**Schema** is the skeleton/structure of the database--a logical blueprint of how the database is constructed and how its parts related to each other.

**DBMS**, the **database management system** is a software application that interacts with the user, other applications, and the database itself to access data. MySQL, PostgreSQL, Oracle are all database management systems because 
they allow the user or other computer applications to define, create, query, update, and administrate databases.

**Scalability** is the ability of a database to handle a growing amount of data. There are two main types of scalability:
- **Vertical scalability** is simply adding more capacity to a single machine. Practically every database is vertically scalable.
- **Horizontal scalability** means adding more capacity by adding more machines. The burden to partition, manage, and maintain data across the different machines falls on the DBMS. 

## Relational (SQL) Databases

The word "relational", when talking about relational databases, has nothing to do with *relationships*. In fact, the meaning of the word comes from [relational algebra](https://en.wikipedia.org/wiki/Relational_algebra). In a **relational database**, each relation is a set of **tuples**. A tuple can also be thought of as a row/record in a table. Each tuple ("row") in a **relation** ("table") shares the same **attributes** ("columns").
Nothing new, just different vocabulary when talking about different types of databases.
![Tuples & Attributes](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7c/Relational_database_terms.svg/1200px-Relational_database_terms.svg.png)

**SQL**: as we discussed before, SQL is a programming language based on relational algebra used to `SELECT`, `INSERT`, `UPDATE`, and `DELETE` data in a relational database.

**Normalization** is the process of organizing the relations and attributes of a relational database so as to reduce **redundancy** and improve **data integrity** (keeping data accurate, consistent, and up-to-date).

**Denormalization** is *not* normalization. But why would we want redundancy? Well, adding redundant data can speed up complex queries. We might include data from one table in another to eliminate the second table and reduce the number of foreign keys used to `JOIN` (another SQL operation) tables.

**ORM** or **object-relational mapping** is a technique for viewing a database as the interaction of objects/entities. 

## Non-Relational (NoSQL) Databases

The basic definition of a **non-relational** database is one that doesn't follow the relational model.

![Table-flip](https://cdn-images-1.medium.com/max/1200/1*Pq8DSf6o1z2N-Qc30yAoPA.jpeg)

Yes, no relations (tables) with tuples (rows) and attributes (columns). There are typically four group/models under the umbrella of NoSQL databases:
- **Key-value store**: one NoSQL model uses **key-value pairs** to define the link between some unique key (such as the primary key) and its value. The benefit is that key-value storage is generally faster and more scalable.
- **Graph store**: uses **nodes** and **edges** to represent relationships between items in a database. Instead of attributes, **properties** describe nodes or edges. Like this:
![Graph store](https://upload.wikimedia.org/wikipedia/commons/3/3a/GraphDatabase_PropertyGraph.png)
- **Column-oriented store** versus **Row-oriented store**. The difference is perhaps better illustrated (by [mariadb.com](https://mariadb.com/resources/blog/why-is-columnstore-important/)) then described:
![Row v. Column](https://mariadb.com/files/inline-images/columnstore-row-vs-column-orientated_0.png)
- **Document store** treats all information for a given item as a **document** which each document has its own structure and attributes.

## Additional Resources
- [Try SQL - w3schools](https://www.w3schools.com/sql/trysql.asp?filename=trysql_asc)
- [Prof. League's Database Worksheet](https://liucs.net/cs101f18/sample-db.pdf) and [solutions](https://liucs.net/cs101f18/n10-artists.html)
- [Khan Academy SQL Basics](https://www.khanacademy.org/computing/computer-programming/sql/sql-basics/v/welcome-to-sql)