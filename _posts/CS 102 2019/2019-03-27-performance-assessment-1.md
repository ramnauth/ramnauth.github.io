---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: PA 1 - Programming Sprints

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Submit your programs here: [https://forms.gle/PQGNEkAghFwdANGT9](https://forms.gle/PQGNEkAghFwdANGT9)

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

You may submit more than one program using the provided [submission portal](https://forms.gle/PQGNEkAghFwdANGT9). Be careful not to overwrite your previous programs by using the same repl. Each submission should have:
1. Multiple submissions allowed
2. Title each program
3. Use comments to explain what's happening in your program
4. Use style guidelines to keep organized

If you don't complete your program within the time limit of the sprint, it is better to submit what you have than to submit nothing at all. This is not an assessment of completeness.

## Solutions

This is **not** a comprehensive list of *all* possible solutions. Remember, there isn't always one way to solve a single problem. Therefore, these solutions are only example solutions. 

- [Program 1](): get an inputted sentence
- [Program 2](): counts from 1 to 10 inclusive
- [Program 3](): counts from 10 to 1 inclusive
- [Program 4](): prints *n* even numbers from 0
    - [Variation 1](): multiplies index by 2 to get even
	- [Variation 2](): for loop that counts by 2
- [Program 5](): prints *n* odd numbers from 0
- [Program 6](): generates a random number between 1 and 10 inclusive
- [Program 7](): counts how many vowels in a given string
- [Program 8](): computes factorial of given number
    - [Variation 1](): computes using a for loop
	- [Variation 2](): computes using recursion
- [Program 9](): determines if a number or string is a palindrome
	- [Variation 1](): folds string in half for mirror image
	- [Variation 2](): completely reverses given string
	- [Variation 3](): folds string in half, terminates immediately if not mirror

## Program 1
```cpp
#include <iostream>
#include <string>

using namespace std;

int main() {
  string sentence;
  cout << "Enter a sentence: ";
  getline(cin, sentence);
  cout << "You have entered the sentence: " << sentence;
  return 0; 
}
```

## Program 2
```cpp
#include <iostream>
using namespace std;

int main() {
  for (int i = 1; i <= 10; i++){
    cout << i << endl;
  }
  return 0; 
}
```

## Program 3
```cpp
#include <iostream>
using namespace std;

int main() {
  for (int i = 10; i >= 1; i--){
    cout << i << endl;
  }
  return 0; 
}
```

## Program 4

### Variation 1
```cpp
#include <iostream>
using namespace std;

int main() {
  int index;
  cout << "Enter a number: ";
  cin >> index;
  for (int i = 0; i < index; i++){
    cout << (i * 2) << endl;
  }
  return 0; 
}
```

### Variation 2
```cpp
#include <iostream>
using namespace std;

int main() {
  int index;
  cout << "Enter a number: ";
  cin >> index;
  for (int i = 0; i < (index * 2); i+=2){
    cout << i << endl;
  }
  return 0; 
}
```

## Program 5
```cpp
#include <iostream>
using namespace std;

int main() {
  int index;
  cout << "Enter a number: ";
  cin >> index;
  for (int i = 0; i < index; i++){
    cout << i * 2 + 1 << endl;
  }
  return 0; 
}
```

## Program 6
```cpp
#include <iostream>
using namespace std;

int main() {
  cout << rand() % 11 + 1 << endl;
  return 0; 
}
```

## Program 7
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
  string sentence;
  cout << "Enter a sentence: ";
  getline(cin, sentence);

  int counter = 0;

  for (int i = 0; i < sentence.size(); i++){
    if (sentence.at(i) == 'A' || sentence.at(i) == 'a' ||
    sentence.at(i) == 'E' || sentence.at(i) == 'e' ||
    sentence.at(i) == 'I' || sentence.at(i) == 'i' ||
    sentence.at(i) == 'O' || sentence.at(i) == 'o' ||
    sentence.at(i) == 'U' || sentence.at(i) == 'u'){
      counter++;
    }
  }
  cout << "There are " << counter << " vowels in '" << sentence << "'" << endl;
  return 0; 
}
```

## Program 8

### Variation 1
```cpp

#include <iostream>
using namespace std;

int getFactorial(int number){
    int num = number;
    int factorial = 1;
    while(num > 0){
        factorial = factorial * num; 
        num--;
    }
    return factorial;
}

int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;
    cout << num << "! = " << getFactorial(num) << endl;
    return 0;
}
```

### Variation 2
```cpp
#include <iostream>
using namespace std;

int getFactorialRecursively(int number){
    int factorial;
    if (number == 1) // base case
        factorial = 1;
    else 
        factorial = getFactorial(number - 1) * number;
    return factorial;
}

int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;
    cout << num << "! = " << getFactorialRecursively(num) << endl;
    return 0;
}
```

## Program 9

### Variation 1
```cpp
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

### Variation 2
```cpp
#include <iostream>
using namespace std;

int main() {
  cout << "Enter a string or number: "<< endl;
  string s;
  getline(cin,s);
 
  string backwards = "";
  for(int i = s.size()-1; i > -1; i--){
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

### Variation 3
```cpp
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