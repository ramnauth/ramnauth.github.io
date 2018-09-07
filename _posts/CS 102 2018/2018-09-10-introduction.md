---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Getting Started

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Setting up Visual Studio Code, your coding environment, and becoming familiar with the tools for debugging and executing your first C++ program.

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
categories: [CS 102]
tags: [C++, Programming Basics]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
In order to begin programming, we need a programming (or development) environment. **Text editors**, such as Microsoft Word, allows us to write/edit text. The text editor that we will be using to write/edit code is [Visual Studio Code]((https://code.visualstudio.com/)), or "VS Code" for short.

## Install VS Code 

**Note:** if you're a Mac OSX user, jump to 

The following video tutorial will walk you through setting up Visual Studio Code ([https://code.visualstudio.com/](https://code.visualstudio.com/)) and give a general overview of its features.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Sdg0ef2PpBw?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### Highlights
- [0:05 - 0:30](https://youtu.be/Sdg0ef2PpBw?t=5s) Download and install VS Code with the default settings
- [0:35 - 1:17](https://youtu.be/Sdg0ef2PpBw?t=35s) See an overview of the user interface.
- [1:22 - 1:31](https://youtu.be/Sdg0ef2PpBw?t=1m22s) Install support for your programming language(s).
- [1:47 - 2:05](https://youtu.be/Sdg0ef2PpBw?t=1m47s) Customize your editor with themes.

## Install the C++ Extension

If this is your first time using VS Code, your editor can only understand JavaScript code. To enable C++ in VS Code, click on **Extensions**, the last icon on the sidebar.

<iframe src="https://drive.google.com/file/d/1-h-CXjWe5DuhZ8PH7pBJA9X_qygIOzBW/preview" width="640" height="480"></iframe>

In the search bar, type <code> C++ </code> to find the official [Microsoft C/C++ extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools). Press **Install**, then **Reload** 

<iframe src="https://drive.google.com/file/d/1jN_XalRpQEsd22bTMNl8nUur2Z-DjfeH/preview" width="640" height="480"></iframe>

With the C/C++ extension installed, create a folder (I chose to create one on my Desktop) named <code> VSCode </code>. Then, create a subfolder to house only your C++ code (<code> ~/Desktop/VSCode/cpp/ </code>). Visual Studio Code will automatically place various settings files into a <code> .vscode </code> subfolder.

Now, we want this folder (<code> ~/Desktop/VSCode/cpp/ </code>) to be our designated *workspace* for our C++ code. To configure this in VS Code, click on **Explorer**, the first icon on the sidebar. 

<iframe src="https://drive.google.com/file/d/11NV8-swMhsmG7HgNPNqJU2sP0Wadeqiz/preview" width="640" height="480"></iframe>

Click **Open Folder** and navigate to the folder you've just created (<code> ~/Desktop/VSCode/cpp/ </code>). Click **Select Folder** to confirm. 

<iframe src="https://drive.google.com/file/d/1AsuXe_7NNcbLU-1w5qr4m8PXTtJLg_x1/preview" width="640" height="480"></iframe>

## Install & Configure a C++ Compiler

You may already have a C++ compiler installed. You can test this by opening Terminal (Mac) or cmd.exe (Windows) and entering <code> g++ </code>. If you get a warning along the lines of <code> ... error: no input files </code>, then your system already has a C++ compiler. Otherwise, if you get an error about the command not being found, then the C++ compiler may not be installed.

At this moment, if you've been following this tutorial, we only have a text editor for writing C++ code. This means that much of what we can now do in VS Code is write/edit text as we do in MS Word. A *compiler* is useful because it translates our human-readable code into machine code or a lower-level language so that now the computer can understand and execute our program. 

### Windows

The following video tutorial shows how to install the [MinGW](https://sourceforge.net/projects/mingw/) compiler for Windows 10.

<iframe width="560" height="315" src="https://www.youtube.com/embed/sXW2VLrQ3Bs?rel=0&amp;start=17" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### Mac OSX

Instead of MinGW (for which the "W" stands for "Windows"), download [XCode](https://developer.apple.com/xcode/) from the app store to compile C++ programs. 

In the menu, open **File**, hover over **New**, and select **Project**.

![XCode New Project](https://qph.fs.quoracdn.net/main-qimg-494e5c7729829296bc6c5f874ea1e844.webp)

Choose the Command Line Tool template

![Command Line Tool template](https://qph.fs.quoracdn.net/main-qimg-e469e865e8be6bdacba120578e2ed516.webp)

Choose project type as C++

![Configure XCode for C++](https://qph.fs.quoracdn.net/main-qimg-127428e338bac20f83da77e593cfd1c8.webp)

Create project and click on <code> main.cpp </code> to make/edit your project. 




