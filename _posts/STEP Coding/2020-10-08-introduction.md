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
categories: [Fall 2020]
tags: [C++]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
In order to begin programming, we need a programming (or development) environment. **Text editors**, such as Microsoft Word, allows us to write/edit text. The text editor that we will be using in class to write/edit code is [Visual Studio Code](https://code.visualstudio.com/), or "VS Code" for short.
1. [Install Visual Studio Code](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#install-vs-code)
2. [Enable C++](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#install-vs-code)
3. [Install C++ Compiler](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#install--configure-a-c-compiler)
    - [For Windows](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#install--configure-a-c-compiler)
	- [For Mac](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#mac-osx)
4. [The `Hello World` Program](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#mac-osx)
5. [Additional Resources](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#additional-resources)

**Alternative:** If for some reason you are not comfortable with any of these tools, create an account on REPL.it [https://repl.it/](https://repl.it/).

## Install VS Code 

**Note:** if you're a Mac OSX user, jump to [Installing XCode](https://ramnauth.github.io/fall%202020/2020/10/08/introduction/#mac-osx).

The following video tutorial will walk you through setting up Visual Studio Code ([https://code.visualstudio.com/](https://code.visualstudio.com/)) and gives a general overview of its features.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Sdg0ef2PpBw?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### Highlights
- [0:05 - 0:30](https://youtu.be/Sdg0ef2PpBw?t=5s) Download and install VS Code with the default settings
- [0:35 - 1:17](https://youtu.be/Sdg0ef2PpBw?t=35s) See an overview of the user interface.
- [1:22 - 1:31](https://youtu.be/Sdg0ef2PpBw?t=1m22s) Install support for your programming language(s).
- [1:47 - 2:05](https://youtu.be/Sdg0ef2PpBw?t=1m47s) Customize your editor with themes.

## Install the C++ Extension

If this is your first time using VS Code, your editor can only understand JavaScript code. To enable C++ in VS Code, click on **Extensions**, the last icon on the sidebar.

<iframe src="https://drive.google.com/file/d/1-h-CXjWe5DuhZ8PH7pBJA9X_qygIOzBW/preview" width="640" height="480"></iframe>

In the search bar, type `C++` to find the official [Microsoft C/C++ extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools). Press **Install**, then **Reload** <br>

<iframe src="https://drive.google.com/file/d/1jN_XalRpQEsd22bTMNl8nUur2Z-DjfeH/preview" width="640" height="480"></iframe>

With the C/C++ extension installed, create a folder (I chose to create one on my Desktop) named `VSCode`. Then, create a subfolder to house only your C++ code (`~/Desktop/VSCode/cpp/`). Visual Studio Code will automatically place various settings files into a `.vscode` subfolder.

Now, we want this folder (`~/Desktop/VSCode/cpp/`) to be our designated *workspace* for our C++ code. To configure this in VS Code, click on **Explorer**, the first icon on the sidebar. 

<iframe src="https://drive.google.com/file/d/11NV8-swMhsmG7HgNPNqJU2sP0Wadeqiz/preview" width="640" height="480"></iframe>

Click **Open Folder** and navigate to the folder you've just created (`~/Desktop/VSCode/cpp/`). Click **Select Folder** to confirm. 

<iframe src="https://drive.google.com/file/d/1AsuXe_7NNcbLU-1w5qr4m8PXTtJLg_x1/preview" width="640" height="480"></iframe>

## Install & Configure a C++ Compiler

You may already have a C++ compiler installed. You can test this by opening Terminal (Mac) or cmd.exe (Windows) and entering `g++`. If you get a warning along the lines of `... error: no input files`, then your system already has a C++ compiler. Otherwise, if you get an error about the command not being found, then the C++ compiler may not be installed.

At this moment, if you've been following this tutorial, we only have a text editor for writing C++ code. This means that much of what we can now do in VS Code is write/edit text as we do in MS Word. A *compiler* is useful because it translates our human-readable code into machine code or a lower-level language so that now the computer can understand and execute our program. 

### Windows

The following video tutorial shows how to install the [MinGW](https://sourceforge.net/projects/mingw/) compiler for Windows 10.

<iframe width="560" height="315" src="https://www.youtube.com/embed/sXW2VLrQ3Bs?rel=0&amp;start=17" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### Mac OSX

Instead of Microsoft's Visual Studio Code and MinGW (for which the "W" stands for "Windows"), download [XCode](https://developer.apple.com/xcode/) from the app store to compile C++ programs. You can still download VS Code (which is compatible with Mac OSX) because this is what we'll be using in class. Unlike VS Code, XCode already comes with a C++ compiler that is compatible with Mac OS. If you wish to avoid the overlap, check out the options provided here: [https://github.com/kennethreitz/osx-gcc-installer#option-1-downloading-pre-built-binaries](https://github.com/kennethreitz/osx-gcc-installer#option-1-downloading-pre-built-binaries)

In the menu, open **File**, hover over **New**, and select **Project**.

<iframe src="https://drive.google.com/file/d/1z2qWY7UE1gT13ChQf3_r8133yPPmrFpa/preview" width="640" height="480"></iframe>

Choose the Command Line Tool template

<iframe src="https://drive.google.com/file/d/1lQeNKCgW5m539di2pfFGhn32YT_dyUs6/preview" width="640" height="480"></iframe>

Choose project type as C++

<iframe src="https://drive.google.com/file/d/1G-6tSGkGITz9pVv-QAIxgHxcgDIV_JGi/preview" width="640" height="480"></iframe>

Create project and click on `main.cpp` to make/edit your project. You can run the program under the **Product** tab > **Run**.

<iframe src="https://drive.google.com/file/d/1fXQKZ8DCoIaO4VTLwalpSbWUDTSksf7e/preview" width="640" height="480"></iframe>

## `hello.cpp`

To create our first C++ program, navigate to the **Explorer** icon on the sidebar, under our workspace **CPP**, click **New File**:

<iframe src="https://drive.google.com/file/d/1zwJHAt-IlG5ng88dHBX523w-6N951xB5/preview" width="640" height="480"></iframe>

Type `hello.cpp` and press enter. In the created file, paste and save the following code. This is a basic "Hello World" program that does only one thing: print `Hello World`.

```cpp
// Preprocessor directive that includes header iostream
#include <iostream>

// Start of your program: function block main()
int main() {
	/* Write to the screen */
	std::cout << "Hello World" << std::endl;

	// Return a value to the OS
	return 0;
}
```

**Note:** The purpose of this guide is to help you configure a text editor and compiler for executing C++ programs. The anatomy of this C++ program and what the `g++` command means will be discussed in later notes.

In the Terminal (Mac) or the cmd.exe (Windows), navigate to the workspace previously created (`~/Desktop/VSCode/cpp/`) using the command `cd` (which means *change directory*). 

Type the command `g++ -o hello hello.cpp` to compile your program. This creates an *executable file* (`~/Desktop/VSCode/cpp/hello.exe`). Clicking on the file will prompt its execution, which may look like a single flash of a black box on the screen. This is because the program has executed and was closed immediately upon completion. 

To view the results of your program, return to the command line and enter `hello.exe`. You should see the words "Hello World". If not, you should see an error which may result in a typo (formally called a *syntax error*) in the source code.

<iframe src="https://drive.google.com/file/d/1SPqFwo1P7kmjaIEbs-eKLivWlGZTuttE/preview" width="640" height="480"></iframe>

## Additional Resources 

- **VS Code Documentation:** [https://code.visualstudio.com/docs](https://code.visualstudio.com/docs)
- **The C++ Extension for VS Code:** [https://blogs.msdn.microsoft.com/vcblog/2016/03/31/cc-extension-for-visual-studio-code/](https://blogs.msdn.microsoft.com/vcblog/2016/03/31/cc-extension-for-visual-studio-code/)
- **Building C++ Programs (alt. method):** [https://blogs.msdn.microsoft.com/vcblog/2016/10/24/building-your-c-application-with-visual-studio-code/](https://blogs.msdn.microsoft.com/vcblog/2016/10/24/building-your-c-application-with-visual-studio-code/)


