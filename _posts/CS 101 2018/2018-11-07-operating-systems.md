---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Operating System

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
	

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
An **operating system** (OS) is software that starts up a computer and keeps it running and following your commands. An operating system's main responsibilities are:
- to run **applications**, which are useful programs such as a calculator or word processor
- allows you to interact with applications
- creates and maintains the **user-interface** (the display on the screen, such as icons you click)
- controls and manages the **file system** so you can read, write, save, and delete files
- translates and communicates your request (e.g., saving a file or printing your homework) with your computer's hardware. 

**Note:** we don't look to the OS to do anything "fun". For example, you can't use it to send an email, draw a picture, or to create a video game. However, your operating system contributes to all of these activities because it allows the applications (that do those "fun" things) to run.

## User Interface
The operating system is a software, and a major part of software is the **user-interface** (else, why create software if your user can't interface/**interact** with it?). There are other **interfaces** that are not *user*-interfaces because they don't interact with human users. For example, a non-user-interface could interact with other programs, connect devices (such as your printer), and connect programs to devices. 

The earliest type of interface is the **command-driven** interface. This kind of interface allows the operating system to accept commands using specific keywords. In contrast, programs that allow you to choose from a list of options in a menu are said to have a **menu-driven** interface. 

Command-driven software usually wins in a battle against menu-driven software. This is because command-driven software is more flexible and allows you to do a lot more things. However, since it relies so much on keywords, you must first learn the **command language**. This language is a programming language because the user communicates with the operating system or the application to make your computer do some commanded actions. 
An example of a command-language is [Bash](). 

The part of an operating system that responds to operating system commands is called the **command processor**. Other popular names for the command processor are the **terminal**, **console**, **command line prompt**, **command line interpreter**, or the **shell**.

![Linux Terminal](https://i.stack.imgur.com/QQreA.png)

A **graphical user interface** (GUI, pronounced *gooey*) allows you to make commands by pointing and clicking at graphical objects on the screen. Below is a screenshot of the Windows 10 GUI.
![Win 10](https://www.google.com/url?sa=i&source=images&cd=&cad=rja&uact=8&ved=2ahUKEwjUtbew4cDeAhWSxVkKHT0TAT0QjRx6BAgBEAU&url=https%3A%2F%2Fwww.guitricks.com%2F2015%2F07%2Fhow-to-download-or-get-windows-10.html&psig=AOvVaw26fogdqvrT6GrayezAFCQ3&ust=1541627837038915)

GUIs such as Microsoft Windows and the one used by Apple Mac feature the following components:
- A **pointer**. The symbol (usually an small angled arrow) that appears on the display and is controlled by the mouse
- **Icons* are small pictures that represent commands, files, or windows. Moving the pointer over the icon and pressing down on the mouse button can execute a command. 
- The **desktop** contains a group of icons. It is called a desktop because the icons are intended to represent real objects on top of a real desk.
- A **window** is a portion of the screen which can display other information or can allow the user to run a different program. You can move windows around the display screen as well as change their shape and size.
- **Menus** allow you to execute commands by selecting a choice from a menu.
- **Folders** are graphical representations of a directory

In additional to these visual components, graphical user interfaces make it easy and intuitive to move data from one application to another. Two ways to do this:
1. **Copy & paste** (`ctrl + c` and `ctrl + v`), copies some data unto a **clipboard** (a special file or memory area (aka a **buffer**) where data is temporarily stored before being pasted into another location).
2. **Drag & drop** is an expression we use to describe applications that allow you to drag objects to specific locations on the screen to perform some action with them. For example, dragging-and-dropping a file into the trash icon will delete the file. When implemented well, drag-and-drop functionality that is more **intuitive** than selecting options from a menu or typing in commands. 