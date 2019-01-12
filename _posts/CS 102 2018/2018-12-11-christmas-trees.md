---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Christmas Trees

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
categories: [CS 102]
tags: [C++]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

Write a program that generates a Christmas tree.

## Triangular Trees
Generate a triangular tree given user-inputted number of levels.
```cpp
Enter a number (levels): 6
     ^
    ^^^
   ^^^^^
  ^^^^^^^
 ^^^^^^^^^
^^^^^^^^^^^
```

```cpp
#include <iostream>
#include <vector>

using namespace std;

int enterNumber(string qualifier);
void drawTriangle();

int main(){
    drawTriangle();
    return 0;
}

void drawTriangle(){
    int levels = enterNumber("levels") * 2;
    for (int i = 1; i <= levels; i+=2){
        for (int k = (levels - i)/2; k > 0; k--){
            cout << " ";
        }
        for (int j = 1; j <= i; j++){
            cout << "^";
        }
        cout << endl;
    }
}

int enterNumber(string qualifier){
    int num;
    cout << "Enter a number (" << qualifier << "): ";
    cin >> num;
    return num;
}
```
## Layered Trees
Generate a layered tree given user-inputted number of layers and layer's depth.
```cpp
Enter a number (layers): 5
Enter a number (depth of each layer): 3
              ^
             ^^^
            ^^^^^
             ^^^
            ^^^^^
           ^^^^^^^
            ^^^^^
           ^^^^^^^
          ^^^^^^^^^
           ^^^^^^^
          ^^^^^^^^^
         ^^^^^^^^^^^
          ^^^^^^^^^
         ^^^^^^^^^^^
        ^^^^^^^^^^^^^
```
```cpp
#include <iostream>
#include <vector>

using namespace std;

int enterNumber(string qualifier);
void drawLayered();

int main(){
    drawLayered();
    return 0;
}

void drawLayered(){
    int layers = enterNumber("layers") * 2;
    int depth = enterNumber("depth of each layer") * 2;

    for (int m = 0; m < layers; m+=2){
        for (int i = 1; i <= depth; i+=2){
            for (int k = (depth * layers/2 - i)/2 - m/2; k > 0; k--){
                cout << " ";
            }
            int j;
            for (j = 1; j <= (i + m); j++){
                cout << "^";
            }
            cout << endl;
        }
    }
}

int enterNumber(string qualifier){
    int num;
    cout << "Enter a number (" << qualifier << "): ";
    cin >> num;
    return num;
}
```

## Decorated Trees
Simulate a tree with twinkling lights and/or ornaments using thread sleeping.
```cpp
#include <iostream>
#include <vector>
//#include <unistd.h> // for Mac OS for system(...)
#include <chrono> // for Windows - sleep/delay thread
#include <thread> // for Windows - sleep/delay thread
#include <windows.h> // for Windows - hide cursor

using namespace std;

int enterNumber(string qualifier);
void drawLights();
void printTree();

void ShowConsoleCursor(bool showFlag); // for Windows - hide cursor

vector< vector<char> > tree;

int main(){
    drawLights();
    return 0;
}

void drawLights(){
    ShowConsoleCursor(false); // hide cursor
    int levels = enterNumber("levels") * 2;

    // build Christmas tree
    for (int i = 1; i <= levels; i+=2){
        vector<char> level;
        for (int k = (levels - i)/2; k > 0; k--){
            level.push_back(' ');
        }
        for (int j = 1; j <= i; j++){
            level.push_back('.');
        }
        tree.push_back(level);
    }
    
    while (1){
        //system("clear"); // on Mac OS
        system("CLS"); // on Windows

        int r = rand() % tree.size();
        int c = rand() % tree.at(r).size();

        if (tree[r][c] == '.'){ // toggle lights
            tree[r][c] = '*'; 
        } else if (tree[r][c] == '*'){ 
            tree[r][c] = '.'; 
        }

        printTree();

        //usleep(50000); // on Mac OS
        Sleep(20); // on Windows
    }
}

// hiding blinking cursor for Windows
// (https://stackoverflow.com/questions/18028808/blinking-underscore-with-console)
void ShowConsoleCursor(bool showFlag) {
    HANDLE out = GetStdHandle(STD_OUTPUT_HANDLE);

    CONSOLE_CURSOR_INFO cursorInfo;

    GetConsoleCursorInfo(out, &cursorInfo);
    cursorInfo.bVisible = showFlag;
    SetConsoleCursorInfo(out, &cursorInfo);
}

void printTree(){
    for (int layer = 0; layer < tree.size(); layer++){
        for (int light = 0; light < tree.at(layer).size(); light++){
            cout << tree[layer][light];
        }
        cout << endl;
    }
}

int enterNumber(string qualifier){
    int num;
    cout << "Enter a number (" << qualifier << "): ";
    cin >> num;
    return num;
}
```