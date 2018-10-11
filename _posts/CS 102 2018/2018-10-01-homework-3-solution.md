---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: A3 - Grid Generation - Solution

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Example solution(s) for [Assignment 3 - Grid Generation](https://ramnauth.github.io/cs%20102/2018/10/01/homework-3/)

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
tags: [C++, Assignments]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

```cpp
#include <iostream>
#include <string>
#include <ctime>

using namespace std;

// Menu
int formatMenu();
int designMenu();
bool checkMenu();

// Get/Use Dimensions
int getDimension();
void determineGrid();

// Draw Grids
void points(int x, int y);
void stars(int x, int y);
void lines(int x, int y);
void boxes(int x, int y);
void custom(int x, int y);

// Global Variables
int gridSizeOpt;
int gridDesignOpt;


int main(){
    checkMenu();
    determineGrid();
    return 0;
}

/*
    Shows this menu and allows the user to choose an option
    > Select the format of your grid:
    > 1. Create an n by n grid [square]
    > 2. Create a x by y grid [rectangle]
    > 3. Create a random grid size
*/
int formatMenu(){
    cout << "----------------------------------" << endl;
    cout << "    WELCOME TO GRID GENERATOR     " << endl;
    cout << "----------------------------------" << endl;
    cout << "Select the format of your grid: " << endl;
    cout << "1. Create an n by n grid [square]" << endl;
    cout << "2. Create a x by y grid [rectangle]" << endl;
    cout << "3. Create a random grid size" << endl;

    int opt;
    cin >> opt;
    if (opt > 3 || opt < 1) {
        return 0;
    }
    return opt;
}

/* Shows this menu and allows the user to choose an option */
int designMenu() {
    cout << "----------------------------------" << endl;
    cout << "    WELCOME TO GRID GENERATOR     " << endl;
    cout << "----------------------------------" << endl;
    cout << "Select the design of your grid: " << endl;
    cout << "1. Points  [.]" << endl;
    cout << "2. Stars   [*]" << endl;
    cout << "3. Lines   [|]" << endl;
    cout << "4. Boxes   [_]" << endl;
    cout << "5. Custom  [?]" << endl;

    int opt;
    cin >> opt;
    if (opt > 5 || opt < 1) {
        return 0;
    }
    return opt;
}

/*
    Check to see if valid menu options were entered
    If invalid option(s), reshow the menus
    Sets the values for global variables gridSizeOpt and gridDesignOpt
*/
bool checkMenu(){
    bool isValid = false;
    while (!isValid) {
        int f = formatMenu();
        int d = designMenu();
        if (f == 0 || d == 0) {
            cout << "Oops, that doesn't seem to be a grid option. Try again." << endl;
        } else {
            isValid = true;
            gridSizeOpt = f;
            gridDesignOpt = d;
        }
    }
    return true;
}

/* Asks the user to enter just 1 dimension */
int getDimension(){
    int d;
    cout << "Enter a dimension: ";
    cin >> d;
    return d;
}

/*
    Sets the length and width of grid by calling getDimension()
    Calls appropriate draw function to draw the grid
*/
void determineGrid(){
    int length = 0;
    int width = 0;
    switch(gridSizeOpt){
        case 1:
            length = getDimension();
            width = length;
            break;
        case 2:
            length = getDimension();
            width = getDimension();
            break;
        case 3: 
            srand(time(0)); // reset a seed
            length = rand() % 10 + 1;
            width = rand() % 10 + 1;
            //cout << "Random #s = " << length << " and " << width << endl;
            break;
    }
    switch(gridDesignOpt){
        case 1: // points
            points(length, width);
            break;
        case 2: // stars
            stars(length, width);
            break;
        case 3: // lines
            lines(length, width);
            break;
        case 4: // boxes
            boxes(length, width);
            break;
        case 5: // custom
            custom(length, width);
            break;
    }
}

/* Draws a grid with period symbol */
void points(int x, int y){
    cout << "----------------------------------" << endl;
    cout << "       POINTS GRID (" << x << " x " << y << ")" << endl;
    cout << "----------------------------------" << endl;
    for (int i = 0; i < x; i++) {
        for (int j = 0; j < y; j++) {
            cout << " . ";
        }
        cout << endl;
    }
}

/* Draws a grid with asterisk symbol */
void stars(int x, int y){
    cout << "----------------------------------" << endl;
    cout << "       STARS GRID (" << x << " x " << y << ")" << endl;
    cout << "----------------------------------" << endl;
    for (int i = 0; i < x; i++) {
        for (int j = 0; j < y; j++) {
            cout << " * ";
        }
        cout << endl;
    }
}

/* Draws a grid with pipe symbol */
void lines(int x, int y){
    cout << "----------------------------------" << endl;
    cout << "       POINTS GRID (" << x << " x " << y << ")" << endl;
    cout << "----------------------------------" << endl;
    for (int i = 0; i < x; i++) {
        for (int j = 0; j < y; j++) {
            cout << " | ";
        }
        cout << endl;
    }
}

/* Draws a grid with underscore and bracket symbols */
void boxes(int x, int y){
    cout << "----------------------------------" << endl;
    cout << "       BOXES GRID (" << x << " x " << y << ")" << endl;
    cout << "----------------------------------" << endl;
    for (int i = 0; i < x; i++) {
        
        for (int j = 0; j < y; j++) {
            cout << "[__]";
        }
        cout << endl;
    }
}

/* Draws a grid with user-inputted symbol */
void custom(int x, int y){
    cout << "----------------------------------" << endl;
    cout << "       CUSTOM GRID (" << x << " x " << y << ")" << endl;
    cout << "----------------------------------" << endl;
    string sym;
    cout << "Enter a symbol to denote a cell: ";
    cin >> sym;

    for (int i = 0; i < x; i++) {
        for (int j = 0; j < y; j++) {
            cout << " " + sym + " ";
        }
        cout << endl;
    }
}
```