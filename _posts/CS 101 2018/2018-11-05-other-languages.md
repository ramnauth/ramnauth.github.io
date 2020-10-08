---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Programming Languages

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
  What tools are needs for the computer to understand our programs/languages? 

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
tags: [Programming Basics]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
Let's look at the tools a computer needs to understand **high-level** (that means, a little like English) **programming languages**. Then, let's discuss **language paradigms**, how languages can be grouped by their features in various ways.

## How Computers "Understand"
We know that computers only speak [binary](https://ramnauth.github.io/cs%20101/2018/09/10/numbers/#binary-numbers). So, when we write and execute programs in high-level programming languages (such as Python), we need several tools to **translate**. This is the stages of 'life' for a computer program.

1. **Editors**: A program is 'born' or begins in a text editor where we write our code. This stage is like writing an essay in MS Word. Instead, we're writing *code* that means something (or, after it's translated in to binary, *will* mean something) to a computer. 
2. **Compilers**: When a program is **compiled**, it is converted into **machine-code**. A program written in a high-level language can run on any computer that has an appropriate compiler (aka the program that translates the language into machine code).
	- Machine-code is also a computer programming language (but a very **low-level** language because it doesn't resemble English very much) consisting of binary or hexadecimal instructions that your computer can respond to directly. 
	- In the early days of computer programming, the output of a compiler was an **assembly-language** version of the program, when then had to be passed through to an **assembler** to finally get to machine-language. Today, compilers are more sophisticated and the assembly-language phase is often eliminated. 
	- You can read more about compilers and other tools in my post on the[Life of a C++ Program](https://ramnauth.github.io/cs%20102/2018/09/12/life/)
3. **Interpreters**: is a program that translates and executes statements in sequence. In other words, it directs the computer to perform the actions specified in your program.

## Programming Language Paradigms
There are many programming languages. Therefore, grouping languages together by common characteristics can help us understand the larger picture. A **paradigm** is simply a **group**. There are two main language paradigms, imperative and declarative, and many subparadigms within each.

![Lang Paradigms](https://liucs.net/cs101f18/lang-taxonomy.png)

### Imperative Languages
The *von Neumann model* of sequential instructions operating on values in memory greatly influenced the most common model of programming language: the **imperative paradigm**. Imperative languages work by issuing a sequence of commands/instructions for the computer to understand. In Python, each statement we type is a new command, telling the computer to print some text, do some calculation, or update a variable.

```py
def fact(n):         # Factorial function, imperative style, Python
    k = 1
    while n > 1:
        k = k * n
        n = n - 1
    return k
```

**Procedural Languages**

The imperative language family is further divided into procedural and object-oriented languages. In procedural languages, the program is divided into **procedures** aka groups of steps to solve a particular problem. Procedures are also called *subprograms* or *functions*. Our pseudocode examples follow this model.

**Object-Oriented Languages**

Object-oriented languages see the world as a bunch of interacting objects. Each object is responsible for its own actions and can contain (aka **encapsulate**) procedures and data structures within themselves. Furthermore, various objects in a program can send messages and respond to each other's messages in order to solve problems.

### Declarative Languages
In the **declarative** paradigm, results are described (aka declared) and the steps to accomplish those results are not stated. There are two main declarative subparadigms, functional and logic languages.

**Functional Languages**

The functional model uses math to describe functions. This means that each piece of code throughout a program produces a value and can be replaced with its value without any side effects. 

```scheme
(define factorial	; Factorial function, functional style, Scheme
(lambda(n)
	(if
	(= n 0)
1
(* n (factorial (- n 1))))))
```

```haskell
fact n = product [1..n]      -- Factorial, functional style, Haskell
```

**Logic Languages**

Logic programming is based on predicate logics, a branch of math that deals with formal reasoning about `AND` and `OR` (the Boolean operators), as well as implication, relations, and inference. In other words, this model uses **facts** about objects and **rules** about the relationships among the objects. A program would consist of asking questions about these objects and their relationship, where answers are deduced from the facts and rules.

```prolog
/* Example clauses in Prolog*/
likes(mary,food).
likes(mary,apples).
likes(john,apples).
likes(john,mary).
```

The following questions (aka **queries**) give these answers:
```
 | ?- likes(mary,food). 
 yes.
 | ?- likes(john,apples). 
 yes.
 | ?- likes(john,food). 
 no.
```

**Query Languages**

Query languages characterize interaction with a database such as inserting, updating, deleting, selecting records. **SQL** (Structured Query Language) is a famous query language that we'll learn about later.

## Expression Notation

One way in which some languages differ is in how arithmetic expressions are written. The way we're familiar with is called **infix notation** because we put the operator **in between** the operands. For example, *a* + *b*. 

However, there are alternative ways of writing arithmetic expressions: prefix and postfix.

In the Lisp language family (which includes Scheme, Racket, and others), we use **prefix notation**. This means the operator goes **before** the operands. Instead of writing `1 + 2 * 3`, we write (+ 1 (* 2 3)).

You evaluate prefix expressions starting from the innermost parentheses, like this:
```
(+ 1 (* 2 3)) ⇒
(+ 1 6) ⇒
7
``` 

On the other hand, some languages use **postfix notation**. No parentheses need, just specify the numbers (separated by spaces) and the operators **after**. Instead of writing `1 + 2 * 3`, we write `1 2 3 * +`