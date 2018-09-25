---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: User-Defined Functions

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   What is a function? How can we create/call functions? Why are they important in programming?

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
A **function** is a reusable sequence of statements designed to do a specific job. 

A C++ program has many parallels to the real-world. For example, your program may need to interrupt 
what it's doing to do something else. In real-life, this is similar to when you are reading a book, but then remember 
that you need to make a phone call. So, you place a bookmark, close your book, make the phone call, and when you are done
with the phone call, you open your book to where you left off. 

C++ programs work the same way. A program will be sequentially executing statements inside of `main()`
when it encounters a function call. A **function call* tells the CPU to pause the current function, execute a **called** function, and when finished, 
return to the original function (the **callee**). In other words, the CPU "puts a bookmark" in the current function, and then calls the function named in the function call. 
When the called function terminates, the CPU goes back to the point it bookmarked, and resumes as usual. 

```cpp
#include <iostream>

using namespace std;

void doSomething(){ //STEP 4
    cout << "In doSomething function" << endl; //STEP 5
}
 
int main(){ //STEP 1
    cout << "Starting main function" << endl; //STEP 2
    doSomething(); // STEP 3: Interrupt main() by making a function call to doSomething()
	cout << "Finished main function" << endl; //STEP 6
	
    return 0; //STEP 7
}
```

In the above program:
1. the C++ compiler first looks for `main()`, which promises to return an `int`.
2. Executing each statement in the order it appears, "`Starting main function`" is printed to the console. 
3. The next line is a function call to `doSomething()`. Here, the CPU bookmarks it's position, and jumps up
to execute `doSomething()`. 
4. The compiler sees that `doSomething()` promises to return `void`, which means the function won't have a return statement. And, thus, returns nothing. 
5. The first (and only) thing it sees in `doSomething()` is a statement to print to the console "`In doSomething function`". 
6. When `doSomething()` is finished, we jump back down to our `main` function and continue where we left off. "`Finished main function`" is printed to the console.
7. We know our `main` function is complete when it fulfills its promise and returns an `int` (`0`). 

## Return Values

In the previous steps, we said that a function may "promise" to return a certain data type. 
When you write your own functions (aka **user-defined functions**), you get to decide whether a function will return a value to the caller or not.
Where and how can you do this? 

Every function has a **function header** (also called a function **signature**) that says:
- **Return value**: what data type does the function promise to return/output?
- **Function name**: by what name can we call the function?
- **Parameter(s)**: what are the expected inputs and their individual data types?

![Function Signature](https://drive.google.com/file/d/1F101DS9MHSZ9MiXr0HCDNdQWUs7vG8WW)

For example, when the `main()` function finishes executing, it returns an integer value (typically `0`) back to the caller function by using a return statement. 

```cpp
// int means the function returns an integer value to the caller
int return3() {
    // this function returns an integer, so a return statement is needed
    return 3; // we're going to return integer value 3 back to the caller of this function
}
 
int main() {
    cout << return3() << endl; // prints 3
    cout << return3() + 2 << endl; // prints 5
 
    return3(); // the value 3 is returned, but is ignored since main() doesn't do anything with it

    return 0;
}
```

In the first function call of `return3()`, the function returns the value of `3` back to the caller (`main()`), and passes that value to the `cout` statement that prints the value to the console.

In the second function call of `return3()`, the function returns the value `3` back to the caller. That line of code becomes: `cout << 3 + 2 << endl;` `3 + 2` is evaluated to `5`. The value of `5` is printed to the console.

In the third function call of `return3()`, the function returns the value of `3` back to the caller. However, `main()` does nothing with the returned value (it doesn't even `cout` it!). So, we can say the returned value is ignored.

## Return Value of Type `void`

Sometimes, you want to create a function that need to return a value. To tell the compiler that a function doesn't return a value, use the return type of `void`. 

We used `void` in our previous function `doSomething()`

```cpp
void doSomething() { // void is the return type
    cout << "In doSomething()" << endl;
    // This function does not return a value so no return statement is needed
}
```

Another example of a function with a `void` return type:

```cpp
void returnNothing() {
    cout << "Hello" << endl;
    // This function does not return a value so no return statement is needed
}
 
int main() {
    returnNothing(); // function returnNothing() is called, no value is returned
 
    cout << returnNothing(); // error: returnNothing() doesn't return anything, so what are you trying to print out?
 
    return 0;
}
```

In the second function call to `returnNothing()`, we get an error. Our function `returnNothing()` has a `void` return type, meaning it doesn't return a value. However, `main()` is trying to send this nothing value to `cout` to be printed. `cout` doesn't know what to do with these "nothing" values. As a result, the compiler flags this as an error.

## Importance of Functions

Functions are helpful for dividing up your work. The same function can also be called multiple times, which is useful if you need your program to do something more than once. 

```cpp
#include <iostream>
 
using namespace std;

// getValueFromUser will read a value in from the user, and return it to the caller
int getValueFromUser() {
    cout << "Enter an integer: "; // ask user for an integer
    int a; // a variable to hold the user input
    cin >> a; // get user input from console and store in variable a
    return a; // return this value to the function's caller (main)
}
 
int main() {
    int x = getValueFromUser(); // first call to getValueFromUser
    int y = getValueFromUser(); // second call to getValueFromUser
 
    cout << x << " + " << y << " = " << x + y << endl;
 
    return 0;
}

/* The program produces the following output:

	Enter an integer: 3
	Enter an integer: 2
	3 + 2 = 5
*/
```

In the above program, `main()` is interrupted twice to make a call to `getValueFromUser()`. In both cases, the value read into variable `a` is passed back to `main()` via the function's return value, and then assigned to variable `x` or `y` in `main()`. This is to make sure that the returned values from our two calls to `getValueFromUser()` don't conflict. 

In addition, `main()` isn't the only function that can call other functions. Any function can make a call to any function:

```cpp
#include <iostream>

using namespace std;
 
void printA(){
    cout << "A" << endl;
}
 
void printB(){
    cout << "B" << endl;
}
 
// function printAB() calls both printA() and printB()
void printAB() {
    printA();
    printB();
}
 
int main() {
    cout << "Starting main()" << endl;
    printAB();
    cout << "Ending main()" << endl;
	
    return 0;
}

/* This program produces the following output:
	Starting main()
	A
	B
	Ending main()
*/
```

## Nested Functions

Unlike conditionals and loops, you cannot nest functions. In other words, you cannot define functions inside other functions. 

```cpp
#include <iostream>

using namespace std;
 
int main() {
    void doSomething(){ // this function is nested inside main(), which is illegal.
        cout << "In doSomething function" << endl;
    }
 
    doSomething();
    return 0;
}
```

The proper way to write the previous program is:

```cpp
#include <iostream>

using namespace std;
 
void doSomething() {
    cout << "In doSomething function" << endl;
}
 
int main() {
    doSomething();
    return 0;
}
```