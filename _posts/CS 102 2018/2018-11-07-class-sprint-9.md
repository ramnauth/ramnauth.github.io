---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Pair Programming - Simulated "Database"

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   This is a group project **due** Wed. Nov. 21 at 11:59 PM.

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
For this pair-programming project, you will write a C++ program to simulate database CRUD functionality (i.e., creating, reading, updating, and deleting records). As proposed by Derron T., the topic is a database for all kinds of *food*.

**Note**: repl.it doesn't allow initializer lists. A great alternative is [Coding Ground](https://www.tutorialspoint.com/codingground.htm) which does allow for more C++ functionality.

## Requirements
1. Use a `struct` to define a `Food`. Have at least 3 attributes/members.
2. Show and allow the user to select from the following menu:
	1. Create and add a new food.
	2. Read information about a food.
	3. Update an existing food.
	4. Delete an existing food from history.
	5. Show all foods.
	6. Exit database.
3. See the following program transcripts for more information on the implementation.

## Class Progress 11-14-2018
```cpp
#include <iostream>
#include <string>
#include <vector>

using namespace std;

struct Food {
    string name;
    double price;
    double rating;
    string origin;
    string description;
};

vector<Food> foods = {
    {"Pasta salad", 6.99, 4.3, "Italy", "Organic wheat pasta with creamy alfredo sauce"},
    {"Pizza pie", 4.99, 4.6, "Italy", "Non-GMO cheese sprinkled around toasted pita bread"},
    {"Cheeseburger", 4.75, 3.5, "USA", "The classic American chicken burger with Smashburger's secret sauce"},
    {"Butter popcorn", 1.99, 3.5, "USA", "The classic American movie-time snack"},
    {"Masala dosa", 2.99, 4.5, "India", "A crispy, rice-batter crepe encases a spicy mix of mashed potato"},
    {"Potato chips", 0.99, 3.5, "UK", "One of the world's most child-friendly and best foods"},
    {"Seafood paella", 6.99, 4.8, "Spain", "Shrimp, lobster, mussels and cuttlefish combine with white rice and various herbs, oil and salt in this Valencian dish"},
    {"Chicken rice", 3.99, 3.75, "Singapore", "Steamed or boiled chicken is served atop fragrant oily rice, with sliced cucumber as the token vegetable"},
    {"Marzipan", 2.55, 3.75, "Germany", "Ground almonds coated with sugar"},
    {"Chicken parm", 6.75, 4.75, "Australia", "Melted Parmesan and mozzarella cheese, and a peppery, garlicky tomato sauce drizzled over the top of a chicken fillet"},
    {"Ankimo fish", 7.75, 4.95, "Japan", "Chunk of monkfish liver with a little grated daikon on the side"},
    {"Goi cuon", 0.75, 4.95, "Vietnam", "This snack made from pork, shrimp, herbs, rice vermicelli and other ingredients wrapped in rice paper is served at room temperature"},
};

void deleteFood();
void readFood();
void createFood();

void printAllFoods();

int main() {
    return 0;
}

void deleteFood() {
    printAllFoods();

    int choice;
    cout << "Which food would you like to delete (Enter #): ";
    cin >> choice;

    char confirmation;
    cout << "Are you sure you want to delete " << foods.at(choice).name << "? (Y/N): ";
    cin >> confirmation;

    if (confirmation == 'Y') {
        foods.erase(foods.begin() + choice);
    }

    printAllFoods();
}

void createFood() {
    string fname;
    cout << "Enter a food name: ";
    getline(cin, fname);

    double fprice;
    cout << "Enter the price: ";
    cin >> fprice;

    double frating;
    cout << "Enter the rating (out of 5): ";
    cin >> frating;

    cin.ignore();

    string forigin;
    cout << "Enter the origin: ";
    getline(cin, forigin);

    Food newFood = {fname, fprice, frating, forigin}; // init list
    /*newFood.name = fname;
    newFood.price = fprice;
    ...*/

    foods.push_back(newFood);
    printAllFoods();
}

void readFood() {
    string fname;
    cout << "Enter a food: ";
    getline(cin, fname);
    bool exists = false;

    // loops through all existing food
    for (int i = 0; i < foods.size(); i++){
        if (fname == foods.at(i).name) {
            exists = true;
            Food f = foods.at(i);
            cout << f.name << "\t";
            cout << f.price << "\t";
            cout << f.rating << "\t";
            cout << f.origin << endl;
            cout << f.description << endl;
        }
    } 
    if (exists == false) {
        cout << fname << " does not exist. " << endl;
    }
    
}

void printAllFoods(){
  for (int i = 0; i < foods.size(); i++){
    cout << i << ". \t" << foods.at(i).name << "\t";
    cout << foods.at(i).price << "\t";
    cout << foods.at(i).rating << "\t";
    cout << foods.at(i).origin << "\t"; 
    cout << endl;
  }
}
```

## Outline
Your program is not required to follow this outline.

```cpp
#include <iostream>
#include <string>
#include <vector>

using namespace std;

struct Food {
    string name;
    double price;
    double rating;
    string origin;
    string description;
};

vector<Food> foods = {
    {"Pasta salad", 6.99, 4.3, "Italy", "Organic wheat pasta with creamy alfredo sauce"},
    {"Pizza pie", 4.99, 4.6, "Italy", "Non-GMO cheese sprinkled around toasted pita bread"},
    {"Cheeseburger", 4.75, 3.5, "USA", "The classic American chicken burger with Smashburger's secret sauce"},
    {"Butter popcorn", 1.99, 3.5, "USA", "The classic American movie-time snack"},
    {"Masala dosa", 2.99, 4.5, "India", "A crispy, rice-batter crepe encases a spicy mix of mashed potato"},
    {"Potato chips", 0.99, 3.5, "UK", "One of the world's most child-friendly and best foods"},
    {"Seafood paella", 6.99, 4.8, "Spain", "Shrimp, lobster, mussels and cuttlefish combine with white rice and various herbs, oil and salt in this Valencian dish"},
    {"Chicken rice", 3.99, 3.75, "Singapore", "Steamed or boiled chicken is served atop fragrant oily rice, with sliced cucumber as the token vegetable"},
    {"Marzipan", 2.55, 3.75, "Germany", "Ground almonds coated with sugar"},
    {"Chicken parm", 6.75, 4.75, "Australia", "Melted Parmesan and mozzarella cheese, and a peppery, garlicky tomato sauce drizzled over the top of a chicken fillet"},
    {"Ankimo fish", 7.75, 4.95, "Japan", "Chunk of monkfish liver with a little grated daikon on the side"},
    {"Goi cuon", 0.75, 4.95, "Vietnam", "This snack made from pork, shrimp, herbs, rice vermicelli and other ingredients wrapped in rice paper is served at room temperature"},
};

void printStars(int num); // prints the rating as a star * or half star '
void printFood(Food f);
void printAllFood();
void showMenu();

void createFood();
void readFood();
void updateFood();
void deleteFood();

int main() {
    showMenu();
    return 0;
}
```

## Partial Transcripts

### Creating a Food
```cpp
-----------------------------------------------
           GLOBAL FOODS DATABASE
-----------------------------------------------
1. Create and add a new food.
2. Read information about a food.
3. Update an existing food.
4. Delete an existing food from history.
5. Show all foods.
6. Exit database.
«1»

Enter the name: «Cheesecake»
Enter the origin: «Greece»
Enter the price (US $): «4.99»
Enter the rating (out of 5): «4.5»
Enter a description: «Some people think destiny is something you cannot escape, such as 
death or a curdled cheesecake, both of which always turn up sooner 
or later. - Lemony Snicket, The Penultimate Peril.»

Cheesecake was added to the Global Foods Database.
Returning to database menu.
```

### Reading information about a Food
```cpp
-----------------------------------------------
           GLOBAL FOODS DATABASE
-----------------------------------------------
1. Create and add a new food.
2. Read information about a food.
3. Update an existing food.
4. Delete an existing food from history.
5. Show all foods.
6. Exit database.
«2»
Enter the name of a food: «Cheesecake»
Cheesecake      $: 4.99         Rating: ****'   Origin: Greece

Some people think destiny is something you cannot escape, such as 
death or a curdled cheesecake, both of which always turn up sooner 
or later. - Lemony Snicket, The Penultimate Peril.

Returning to database menu.
```

### Update an existing Food
```cpp
-----------------------------------------------
           GLOBAL FOODS DATABASE
-----------------------------------------------
1. Create and add a new food.
2. Read information about a food.
3. Update an existing food.
4. Delete an existing food from history.
5. Show all foods.
6. Exit database.
«3»

0.      Pasta salad     $: 6.99         Rating: ****'   Origin: Italy
1.      Pizza pie       $: 4.99         Rating: ****'   Origin: Italy
2.      Cheeseburger    $: 4.75         Rating: ***'    Origin: USA
3.      Butter popcorn  $: 1.99         Rating: ***'    Origin: USA
4.      Masala dosa     $: 2.99         Rating: ****'   Origin: India
5.      Potato chips    $: 0.99         Rating: ***'    Origin: UK
6.      Seafood paella  $: 6.99         Rating: ****'   Origin: Spain
7.      Chicken rice    $: 3.99         Rating: ***'    Origin: Singapore
8.      Marzipan        $: 2.55         Rating: ***'    Origin: Germany
9.      Chicken parm    $: 6.75         Rating: ****'   Origin: Australia
10.     Ankimo fish     $: 7.75         Rating: ****'   Origin: Japan
11.     Goi cuon        $: 0.75         Rating: ****'   Origin: Vietnam
12.     Cheesecake      $: 4.99         Rating: ****'   Origin: Greece

Which food would you like to update? (Enter #): «1»

1. Name
2. Price
3. Rating
4. Origin
5. Description
Which attribute would you like to update? (Enter #): «1»

What is the value of the new attribute?
«Cheese pizza»

Cheese pizza has been successfully updated in the Global Foods Database.
Returning to database menu.
```

### Delete an existing Food from history
```cpp
-----------------------------------------------
           GLOBAL FOODS DATABASE
-----------------------------------------------
1. Create and add a new food.
2. Read information about a food.
3. Update an existing food.
4. Delete an existing food from history.
5. Show all foods.
6. Exit database.
«4»

0.      Pasta salad     $: 6.99         Rating: ****'   Origin: Italy
1.      Cheese pizza    $: 4.99         Rating: ****'   Origin: Italy
2.      Cheeseburger    $: 4.75         Rating: ***'    Origin: USA
3.      Butter popcorn  $: 1.99         Rating: ***'    Origin: USA
4.      Masala dosa     $: 2.99         Rating: ****'   Origin: India
5.      Potato chips    $: 0.99         Rating: ***'    Origin: UK
6.      Seafood paella  $: 6.99         Rating: ****'   Origin: Spain
7.      Chicken rice    $: 3.99         Rating: ***'    Origin: Singapore
8.      Marzipan        $: 2.55         Rating: ***'    Origin: Germany
9.      Chicken parm    $: 6.75         Rating: ****'   Origin: Australia
10.     Ankimo fish     $: 7.75         Rating: ****'   Origin: Japan
11.     Goi cuon        $: 0.75         Rating: ****'   Origin: Vietnam
12.     Cheesecake      $: 4.99         Rating: ****'   Origin: Greece

Which food would you like to delete? (Enter #): «5»
Are you sure you want to delete Potato chips? (Y/N): «Y»
Returning to database menu.
```

### Show all Food
```cpp
-----------------------------------------------
           GLOBAL FOODS DATABASE
-----------------------------------------------
1. Create and add a new food.
2. Read information about a food.
3. Update an existing food.
4. Delete an existing food from history.
5. Show all foods.
6. Exit database.
«5»

0.      Pasta salad     $: 6.99         Rating: ****'   Origin: Italy
1.      Cheese pizza    $: 4.99         Rating: ****'   Origin: Italy
2.      Cheeseburger    $: 4.75         Rating: ***'    Origin: USA
3.      Butter popcorn  $: 1.99         Rating: ***'    Origin: USA
4.      Masala dosa     $: 2.99         Rating: ****'   Origin: India
5.      Seafood paella  $: 6.99         Rating: ****'   Origin: Spain
6.      Chicken rice    $: 3.99         Rating: ***'    Origin: Singapore
7.      Marzipan        $: 2.55         Rating: ***'    Origin: Germany
8.      Chicken parm    $: 6.75         Rating: ****'   Origin: Australia
9.      Ankimo fish     $: 7.75         Rating: ****'   Origin: Japan
10.     Goi cuon        $: 0.75         Rating: ****'   Origin: Vietnam
11.     Cheesecake      $: 4.99         Rating: ****'   Origin: Greece

Returning to database menu.
```

### Exiting database
```cpp
-----------------------------------------------
           GLOBAL FOODS DATABASE
-----------------------------------------------
1. Create and add a new food.
2. Read information about a food.
3. Update an existing food.
4. Delete an existing food from history.
5. Show all foods.
6. Exit database.
«6»

Goodbye.
```

## Submission Portal

Submit your program here: [https://goo.gl/forms/smEG0WmpRgBGliiE2](https://goo.gl/forms/smEG0WmpRgBGliiE2).

## Permission Release

Please give your responses to this form: [https://goo.gl/forms/aQhNv40cchmiXsyz2](https://goo.gl/forms/aQhNv40cchmiXsyz2)
