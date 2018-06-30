---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Building Blocks of Scratch

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
# description: >
   

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
categories: [Summer Institute]
tags: [Scratch, Programming Basics]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
# Building Blocks of Scratch

## Statements

In programming, a **statement** is a command that tells the computer to do something. In Scratch, any block that reads like a command is a statement.

For example, the <img src="https://cs.harvard.edu/malan/scratch/say.gif"/> block instructs a sprite to say something. <img src="https://cs.harvard.edu/malan/scratch/goto.gif"/> block commands the sprite to go to the mouse's _x_ and _y_ location. 

You may want a statement to be executed only under specific conditions. Such conditions are defined in terms of boolean expressions.

## Boolean

A **boolean** expression is an expression that is either true or false. In Scratch, any diamond-shaped block is a boolean expression. For example, the ![mouse-down](https://cs.harvard.edu/malan/scratch/mousedown.gif) block evaluates to true if the mouse button is down or false if not. Another example is the comparator block( ![less-than](https://cs.harvard.edu/malan/scratch/lessthan.gif)) will evaluate to true is some number is less than another and false if not.

With boolean expressions we can make conditions.

## Conditions

A **condition** must be true in order for something to happen. In Scratch, any block whose label include the words “if,” “when,” or “until” is a conditional construct. For example:
![if-construct](https://cs.harvard.edu/malan/scratch/if.gif) 

This **if construct** can instruct a sprite to say hello **if** the user has clicked the mouse:
![if-example](https://cs.harvard.edu/malan/scratch/ifmousedown.gif)

The **if-else construct** is different in that we can instruct a sprite to, **if** the mouse is clicked, say hello. **Else** (the mouse is not clicked), say goodbye.
![if-else-construct](https://cs.harvard.edu/malan/scratch/ifelse.gif)

Furthermore, these constructs can be **nested** to allow for multiple different conditions:

![nested-condition](https://cs.harvard.edu/malan/scratch/ifelseifelse.gif)

Other conditional blocks include ![keypressed](https://cs.harvard.edu/malan/scratch/when.gif) and ![wait-until](https://cs.harvard.edu/malan/scratch/until.gif).

Sometimes, you may want statements to be executed many times in a row. Loops make this behavior possible. 

## Loops

A **loop** can make one or more statements execute multiple times. In Scratch, any block whose label begins with “forever” or “repeat” is a looping construct. 

An instance of a loop construct is the ![forever](https://cs.harvard.edu/malan/scratch/forever.gif) block which allows us to, for example, instruct a sprite to meow every other second:
![forever-example](https://cs.harvard.edu/malan/scratch/forevermeow.gif)

The ![repeat](https://cs.harvard.edu/malan/scratch/repeat.gif) block allows you to loop a specified number of times. And the ![repeat-until](https://cs.harvard.edu/malan/scratch/repeatuntil.gif) block allows you to loop until some boolean expression is

## Variables

In programming, variables allow a program to “remember” a value. In algebra, _x_ and _y_ are popular variables for storing the numerical value of coordinates such as (3, 4). In Scratch, variables are the oval blocks that must be uniquely labelled (no two variables can have the same name). 

Variables can be **local** or **global**. In Scratch, a local variable is used by only one sprite. A global variable can be used by all of your sprites. 

Variables allow, for example, a sprite to count up from 1:
![count-variable-example](https://cs.harvard.edu/malan/scratch/forevercount.gif)

Statements, boolean expressions, conditions, loops, and variables are the building blocks in programming. Now, we explore higher-level programming constructs such as threads and events.

## Threads

In general, a **thread** is mini-program running within a larger program. A program can have multiple threads and, therefore, can do multiple things at the same time. In Scratch any block with a wavy top and whose label begins with “when” demarks the start of a thread. For example, the ![flagclick](https://cs.harvard.edu/malan/scratch/whenclicked.gif) block and the blocks that fit unto it form a thread that executes when the user clicks the green flag. 

It is helpful to separate different tasks into different threads. For example, you might want to keep track of whether the user presses a key to turn off and on (toggle) the sound. 

![multithreading](https://cs.harvard.edu/malan/scratch/muted.gif)

In the above example, the left-hand thread is responsible for meowing and the right-hand thread is constantly checking and remembering whether the user has muted or unmuted sound by pressing the space bar. 

## Events 

Multiple threads can communicate with each other by signaling and then handling events. An event is like a message between threads. In Scratch, ![broadcast](https://cs.harvard.edu/malan/scratch/broadcast.gif) blocks signal events to blocks that begin with “when” (threads such as ![whenireceive](https://cs.harvard.edu/malan/scratch/whenireceive.gif). Clicking the Scratch green flag, for example, signals an event that is handled by ![flagclick](https://cs.harvard.edu/malan/scratch/whenclicked.gif).

In Scratch, events also allow different sprites to communicate with each other. For instance, two sprites playing Marco Polo require a message to be sent. Therefore, an event is broadcasted. 
![marcopolo](https://cs.harvard.edu/malan/scratch/marco.gif)

## Review

<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdoanTIBwy7SnRL9G8qyXm5xPnoRwu6b3Q0exfy2TJWaq5HyA/viewform?embedded=true" width="650" height="520" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>