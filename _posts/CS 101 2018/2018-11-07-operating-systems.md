---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Operating Systems

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   What are operating systems? Why are they important?

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

The primary components/aspects of an operating system are:
- the [User Interface](https://ramnauth.github.io/cs%20101/2018/11/07/operating-systems/#user-interface)
- the [Kernel](https://ramnauth.github.io/cs%20101/2018/11/07/operating-systems/#kernel)
- [Networking](https://ramnauth.github.io/cs%20101/2018/11/07/operating-systems/#networking)
- [Security](https://ramnauth.github.io/cs%20101/2018/11/07/operating-systems/#security)

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

## Other Components to an OS
In addition to a command-driven interface, an operating system consists of the following components:

### Kernel
The **kernel** provides a basic level of control over all the computer's hardware devices. It manages memory access for programs in the RAM, it says which applications get access to which hardware resources, it sets/resets the CPU's operating state, and organizes data with file systems. In other words, the kernel connects the hardware and software of a computer:
![Kernel](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Kernel_Layout.svg/330px-Kernel_Layout.svg.png)
- **Program Execution**: opening/running/executing a program makes the kernel create a **process** for assigning memory space and other resources. The process is given a priority if the OS can multi-task. It also loads program binary code into memory, and begins executing that program.
- **Interrupts**: instead of watching all the sources of input for events that require action, the OS uses interrupts to be more efficient. When an interrupt is received (such a user clicking on an application icon), the OS's kernel stops whatever the computer's hardware was doing, saves its status, and run the code associated with the interrupt. This is like bookmarking your book to respond to a phone call. 
- **Modes**: there are usually two modes in a OS -- **user mode** and **root** (aka **supervisor**) **mode**. Supervisor mode allows unrestricted access to all the computer's resources. However, user mode sets limits on what the use can use or even access.
- **Managing Memory**: the kernel must manage all system memory so that a program won't interfere with memory already used by another program.
- **Virtual Memory**: when there's a shortage in physical memory, the kernel may temporarily transfer data from RAM to disk storage.
- **Multitasking**: the kernel has a **scheduling** program that determines how much time each process takes. You can see this scheduler in action by opening the `Task Manager` (on Windows) or `Activity Monitor` (on Mac)
- **Disk Access & File Systems**: computers store data on disks using files. The way in which files are stored on a disk is called a **file system**, and enables files to have names and attributes. It also allows them to be stored in a hierarchy or **directory tree**.
- **Device Drivers**: this is a computer program that operates/controls/manages a device connected to the computer.

### Networking
Many operating systems support a variety of networking protocols, hardware, and applications for using them. Networks can allow a computer to access the resources of another computer or a wired or wirelessly-connected device (e.g., a printer or your smart-phone). **Client and server** networking allows a program on a computer (the **client**) to connect over a network to another computer (the **server**). Servers provide the *services* requested by the client by first figuring out what the client's **Internet Protocol** (IP) **address** is and what **ports** (aka access points) exists beyond that IP address. We will investigate this further in the coming weeks.

### Security
An operating system must be aware of requests that are **privileged** (allowed) versus **non-privileged** (aka not allowed). To do this, your OS will request the **identity** of the user or application making the request. Then, to make sure the person/application isn't lying, the computer **authenticates**. Usually, a username and the password must be correctly given. 

Today, we have many sophisticated ways of authentication, such as magnetic cards (like our LIU ids) or biometric data (like a retina or fingerprint scanner).

In the next few classes, we'll look at these components in more detail.