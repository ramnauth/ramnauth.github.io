---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Classroom Coding Sprint - Prof. League's Quiz 2

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
tags: [C++, Coding Challenges]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
You may download and complete the following quiz. The solutions are posted below.
<iframe src="https://drive.google.com/file/d/1hHGyVfnsw_9XKkHaySpc6K_bDmFiNsap/preview" width="720" height="240"></iframe>

## Solutions

1. Which of the following statements prints exactly this text, as shown:
```
We the
PEOPLE
```
Select all that apply.
	a. `cout << "We the PEOPLE" << endl;`
	b. `cout << "We the" << "endl" << "PEOPLE" << "endl";`
	c. `cout << "We" << " the" << endl << "PEOPLE" << endl;`
	d. `cout << "We the" << endl << "PEOPLE" << endl;`
	e. `cout << "WE the" << endl << "people";`
**Solution:**
```cpp
	cout << "We the PEOPLE" << endl; 					// prints "We the PEOPLE"
	cout << "We the" << "endl" << "PEOPLE" << "endl";	// prints "We the endl PEOPLE"
	cout << "We" << " the" << endl << "PEOPLE" << endl;	// prints correct output
	cout << "We the" << endl << "PEOPLE" << endl; 		// prints correct output
	cout << "WE the" << endl << "people";				// prints with capital "E" in "WE"
```
Only options **c** and **d** produce the required output.
2. Given a variable `maxDays = 14`, which statement prints `14`?
	a. `cout >> maxDays;`
	b. `cout << maxDays;`
	c. `cout << "maxDays";`
	d. `print maxDays;`
	
**Solution:**
```cpp
	cout >> maxDays;	// arrows are facing the wrong way for cout
	cout << maxDays;	// prints correct answer
	cout << "maxDays";	// prints the word "maxDays" not the value
	print maxDays;		// wrong command for printing, use cout
```
Only option **b** produces the required output.

3. Circle and describe any syntax errors in this program:
```cpp
#include <iostream>
using namespace;
INT main( )
{
	int score = 100;
	cout << 'Hello world.' << endl
	cout < score < '%';
	return 0;
}
```
**Solution:**
- Missing namespace `std`
- Should lowercase `INT`
- Need double quotes around `“Hello world”`
- Need semi-colon after `endl`
- Need double less-than `<<` on second `cout`

4. Below is a simple C++ program containing a calculation and some output. What would it output when you run it?
```cpp
#include <iostream>
using namespace std;
int main()
{
	int lisa = 8;
	int bart = lisa + 2;
	int maggie = bart - 7;
	cout << maggie << ", " << bart << lisa << endl;
	return 0;
}
```
**Solution:** will output `3, 108`
5. The following program uses a variety of arithmetic operators and mathematical functions. What does it output? You can write each line of output to the right of the corresponding `endl`.
```cpp
#include <iostream>
#include <cmath>
using namespace std;
int main()
{
	cout << 9 / 2            << endl; // _______
	cout << 7 / 2.0          << endl; // _______
	cout << 17 % 2           << endl; // _______
	cout << 31 % 7           << endl; // _______
	cout << pow(3,3)         << endl; // _______
	cout << sqrt(25)         << endl; // _______
	cout << floor(9.8)       << endl; // _______
	cout << sqrt(pow(2,4))+1 << endl; // _______
	return 0;
}
```
**Solution:**
```cpp
#include <iostream>
#include <cmath>
using namespace std;
int main()
{
    cout << 9 / 2            << endl; // 4
    cout << 7 / 2.0          << endl; // 3.5
    cout << 17 % 2           << endl; // 1
    cout << 31 % 7           << endl; // 3
    cout << pow(3,3)         << endl; // 27
    cout << sqrt(25)         << endl; // 5
    cout << floor(9.8)       << endl; // 9
    cout << sqrt(pow(2,4))+1 << endl; // 5
    return 0;
}
```
