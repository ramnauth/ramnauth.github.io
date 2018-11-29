---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Performance Assessment - Week 2 (Nov. 26 - 30)

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Upload link provided below. Prompts will be posted after assessment. 

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
categories: [CS 102, Coding Challenges]
tags: [C++]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

**Submission portal**
[https://goo.gl/forms/NWanEDatuCOiZ9Yq1](https://goo.gl/forms/NWanEDatuCOiZ9Yq1)

## Assessment Format
This is less of an assessment than it is a game of [musical chairs](https://en.wikipedia.org/wiki/Musical_chairs). 
You'll be presented a programming task to write/solve. Whoever finishes last is out of the game. The person/team that finishes first will be awarded the most points. 
However, those that are eliminated from the game can rejoin by critiquing (finding a way to break) someone else's code. The individual left or with the most points by the end of the week wins. 

## Submission Requirements
1. Multiple submissions allowed
2. Title/number each program
3. Use comments to explain what's happening in your program
4. Use style guidelines to keep organized

## Prompts
- [Factorial Finder]() - write a program that determines the factorial of a user-inputted number
- [Is Prime?]() - write a program that determines if a user-inputted number is prime
- [Is Palindrome?]() - write a program that determines if a user-inputted string/number is a [palindrome](https://en.wikipedia.org/wiki/Palindrome)
- [Fibonacci Sequence]() - write a program that get the nth number in the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number), where *n* is a user-inputted integer

## Solutions

### Factorial Finder
```cpp
/* WINNERS: Timothy J. Morales Lopez & L.X. 
   Title: 1 - Factorial Finder
*/

#include <iostream>

using namespace std; 

int main() 
{
  int num; // stores user inputted positive integer
  int factorial = 1; // stores the factorial so if num is 0, factorial is 1 

  do
  {
    cout << "Enter a positive integer" << endl;
    cin >> num; 
  } while (num < 0); 

// calculates factorial of num
  for (int i = 1; i <= num; i++)
  {
    factorial*= i; 
  }

  cout << "The factorial of " << num << " is = " << factorial << endl;

  return 0; 
}
```

```cpp


```cpp
/* Author: Rebecca Ramnauth
   Title: just another solution...
*/

#include <iostream>

using namespace std;

int getFactorial(int number);
int getFactorialRecursively(int number);

int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;

    cout << num << "! = " << getFactorial(num) << endl;
    cout << num << "! = " << getFactorialRecursively(num) << endl;

    return 0;
}

int getFactorial(int number){
    int num = number;
    int factorial = 1;
    while(num > 0){
        factorial = factorial * num; 
        num--;
    }
    return factorial;
}

int getFactorialRecursively(int number){
    int factorial;
    if (number == 1) // base case
        factorial = 1;
    else 
        factorial = getFactorial(number - 1) * number;
    return factorial;
}
```

### Is Prime?
``` cpp
/* WINNERS: Timothy J. Morales Lopez & L.X. 
   Title: 2 - Prime Finder
*/

#include <iostream>

using namespace std; 

int main() 
{
  int num; // user number
  int n; 
  bool p = true; // store if num is prime or not

  cout << "Enter a number" << endl;
  cin >> num; 
  n = num; 
  
  if (n <= 1)
  {
    p = false; 
  }
  else
  {
    for (int i = n - 1; i > 1; i--)
    {
      if (n % i == 0)
      {
        p = false; 
      }
    }
  }

  if (p)
  {
    cout << num << " is prime" << endl; 
  }
  else if (!p)
  {
    cout << num << " is not prime" << endl;
  }

  return 0; 
}
```

```cpp
/* RUNNER UP - 2nd Place: THITHI & Derron Thomas
   Title: Prime Number
*/

#include <iostream>

using namespace std;

bool isPrime(int n) // function to check if number is Prime
{ 
    if (n <= 1) 
        return false; 
  
    for (int i = 2; i < n; i++){
        if (n % i == 0) 
            return false; 
    }
    return true; 
} 
  
int main (){
    int enter;
    cout << " Please enter the Prime #: " << endl;
    cin >> enter; // variable to store number entered
    isPrime(enter);
    if (isPrime(enter) == true) {
        cout << "Your number is a Prime number" << endl; // prints if number is Prime
    }
    else {
        cout << "Your number is not a Prime number" << endl; // prints if number is not Prime
    }
    return 0;
}
```

```cpp
/* RUNNER UP - 3rd Place: J.R.
   Title: Prime Numbers
*/

#include <iostream>

using namespace std;

bool determinePrime() {
  int num;
  cout << "Enter a number: ";
  cin >> num;

  if (num <= 0){
    return false; // negatives and 0 are not prime
  }

  for (int i = 2; i < num; i++){
    if (num % i == 0){ // num is divisible by i
      return false; // isn't a prime
    }
  }
  return true;
}

int main() {
  cout << determinePrime();
  return 0;  
}
```

### Is Palindrome?
```cpp
/* WINNER: THITHI & Derron Thomas
   Title: Palindrome
*/

#include<iostream>
#include<string>
 
using namespace std;
 
int main()
{
    string str; // used to store what user entered
    int length; // length of the string entered
    bool isPalindrome = true; // check if is true or false
    
    cout << "Enter a word: " ;
    getline(cin, str);
 
    length = str.length(); // length of string entered
 
    for (int i = 0; i < (length / 2); i++)
    {
        if (str[i] != str[(length - 1) - i])
            isPalindrome = false;
    }
 
    if (isPalindrome == true) 
    {
        cout << str << " is a palindrome" << endl;
    }
    else 
    {
        cout << str << " is not a palindrome" << endl;
    }
    return 0;

}
```

```cpp
/* RUNNER UP - 2nd Place: J.R.
   Title: Palindrome Checker
*/

#include <iostream>

using namespace std;

int main() {
  cout << "Welcome To Our Palindrome Checker" << endl;
  cout << "Enter A String Or A Number"<< endl;
 
  string s;

  getline(cin,s);
 
  string backwards = "";
  for(int i = s.size()-1; i > -1; i--){ //Reverse String
    backwards += s.at(i);
  }
  if (backwards == s){
    cout << "It is A Palindrome";
  }
  else {
    cout << " It is Not A Palindrome";
  }
  return 0;
}
```

```cpp
/* RUNNER UP - 3rd Place: Timothy J. Morales Lopez & L.X. 
   Title: 3 - Palindromes
*/

#include <iostream>
#include <string> 

using namespace std; 

int main() 
{
  string answer; // stores user input
  bool p = true; // stores whether string is a palindrome or not

  cout << "Enter a string: " << endl;
  getline(cin, answer); 

  if (answer.length() != 1)
  {
    for (int i = 0; i < answer.length() / 2; i++)
    {
      int j = answer.length() - (1 + i); 
      if (answer.at(i) != answer.at(j)) // loops thru the word and checks if the first char of the string is the same as the last char of the string, and so on
      {
        p = false; // if at any point the chars are not the same, then the word is not a palindrome 
        break; 
      }
    }
  }

  if (p)
  {
    cout << "Your string is a palindrome" << endl;
  }
  else
  {
    cout << "Your string is not a palindrome" << endl;  
  }

  return 0; 
}
```

### Fibonacci Sequence
```cpp
/* TIE: Timothy J. Morales Lopez & L.X. 
   Title: 4 - Fibonacci Sequence
*/

#include <iostream>
#include <vector> 

using namespace std; 

vector<int> fnums; // stores numbers of the Fibonacci sequence
int num = 0; // stores user input, set to 0 so that while loop will activate 

int main() 
{
  while (num <= 0 || num >= 47) // gets the position of the sequence that the user wants to see 
  {
    cout << "What number digit of the Fibonacci Sequence would you like to be shown? (Please enter a number from 1 to 46)" << endl; 
    cin >> num;
  }
  // pushes back the first two elements of the sequence
  fnums.push_back(1);
  fnums.push_back(1);

  // loops through vector and adds numbers of the Fibonacci sequence as necessary, only up to the position the user requests 
  for (int i = 2; i <= num; i++) 
  {
    int c = fnums.at(i - 2) + fnums.at(i - 1); 
    // calculates next number in sequence  
    fnums.push_back(c); 
  }

  cout << "Digit #" << num << " of the Fibonacci sequence is " << fnums.at(num - 1) << endl; 

  return 0; 
}
```

```cpp
/* TIE: THITHI & Derron Thomas
   Title: Fibonacci
*/

#include <iostream>

using namespace std;

int main() {
int x;

int p1 = 1;
int p2 = 1;
int p3 = 0;

cout << "Which number placement do you want in the Fibonacci sequence? ";
cin >> x;

if (x == 1) {
    p3 = 1;
}
else if (x == 2) {
    p3 = 1;
}
else {
    for (int i = 1; i < x - 1; i++) {
    p3 = p1 + p2;
    p1 = p2;
    p2 = p3;
  }
}
cout << p3 << endl;
return 0;

}
```

```cpp
/* RUNNER UP - 2nd Place: G.J.
   Title: Get Nth Fibonacci
*/

#include <iostream>
#include <vector>

using namespace std;

int getNumber();
int getNthFib(int num);

int main() {
	cout << getNthFib(getNumber());
	return 0;
}

int getNumber() {
  int num;
  cout << "Enter a number: ";
  cin >> num;

  return num;
}

int getNthFib(int num){
  vector<int> sequence(0);
  sequence.push_back(1);
  sequence.push_back(1);
  if (num <= 2){
    return 1;
  } else {
    for (int i = 1; i < num - 1; i++){
      sequence.push_back(sequence.at(i) + sequence.at(i - 1));
      cout << sequence.at(i + 1) << " ";
    }
  }
  cout << endl;
  return sequence.at(sequence.size() - 1);
}
```

```cpp
/* Honorable Mention: Rebecca Ramnauth & Timothy J. Morales Lopez
   Purpose: Considering time/space...
*/

#include <iostream>

using namespace std;

int main() {
  int nums[46] = {1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368, 75025, 121393, 196418, 317811, 514229, 832040, 1346269, 2178309, 3524578, 5702887, 9227465, 14930352, 24157817, 39088169, 63245986, 102334155, 165580141, 267914296, 433494437, 701408733, 1134903170, 1836311903};
  
  int num;
  cout << "Enter a number: ";
  cin >> num;

  cout << nums[num - 1];
  return 0;
}
```