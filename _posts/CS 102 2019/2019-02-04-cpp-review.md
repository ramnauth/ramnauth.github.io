---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: C++ Review Sheet

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   C++ review sheet, updated as of **02/20/2019**

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
This review sheet will cover the following topics:

1. [Basics](https://ramnauth.github.io/cs%20102/2019/02/04/cpp-review/#basics) - Mon, Jan. 28; Q1 Wed, Feb. 06
2. [Data Types](https://ramnauth.github.io/cs%20102/2019/02/04/cpp-review/#data-types) - Wed, Jan. 30; Q1 Wed, Feb. 06
3. [Arithmetic](https://ramnauth.github.io/cs%20102/2019/02/04/cpp-review/#arithmetic) - Mon, Feb. 04; Q1 Wed, Feb. 06
4. [Conditionals](https://ramnauth.github.io/cs%20102/2019/02/04/cpp-review/#conditionals) - Mon, Feb. 11; CA1
5. [Loops](https://ramnauth.github.io/cs%20102/2019/02/04/cpp-review/#loops) - Wed, Feb. 20, Mon, Feb. 25; A1
6. [Strings](https://ramnauth.github.io/cs%20102/2019/02/04/cpp-review/#strings) - Wed, Feb. 20, Mon, Feb. 25; A1

## Basics

```cpp
//This is a comment

/*
    This is a multiline comment
*/

#include <iostream>

using namespace std;
int main() {
    cout << "Hello World!" << endl;
    return 0;
}
```

## Data Types

```cpp
#include <iostream>

using namespace std;
int main() {

    // int is an integer value: 0, 1, 2, 3, ...
    int myAge = 35;
    // const values cannot be changed
    const double PI = 3.14;
    // char is a letter denoted in single quotes: 'a', 'b', 'c', ...
    char myGrade = 'A';
    // bool is either true (1) or false (0)
    bool isHappy = true;
    // float are numbers with max 7 sig figs
    float favFloat = 3.141592;
    // double has 2x precision of a float, max 16 sig figs
    double favDouble = 3.312141592341213;
    
    cout << "Printing the number " << PI << endl;

    /* Other types include:
         short int: >= 16 bits
         long int: >= 32 bits
         long long int: >= 64 bits;
         unsigned int: same size as signed int
         long double >= double
    */

    cout << "Size of int: " << sizeof(myAge) << " bytes." << endl;
    cout << "Size of double: " << sizeof(favDouble) << " bytes." << endl;
    cout << "Size of float: " << sizeof(favFloat) << " bytes." << endl;
    cout << "Size of bool: " << sizeof(isHappy) << " bytes." << endl;
    cout << "Size of char: " << sizeof(myGrade) << " bytes." << endl;
    
    int largestInt = 2147483647; // also written as INT_MAX
    cout << "Largest int possible: " << largestInt << endl;
    
    int smallestInt = -2147483648; // also written as INT_MIN
    cout << "Smallest int possible: " << smallestInt << endl;
	
    /*  Why is the smallest integer value just the negation of the largest integer? 
    	In two's complement (a representation for positive and negative binary numbers), the leftmost
    	bit is reserved for the sign (+ or -). If a number is negative, the leftmost bit will be 1. 
    	If positive, the leftmost bit is 0. 
    	
    	In a fixed-size representation of 3 bits (with signed numbers, aka Two's Complement), 
    	the most negative value is the binary number 100 ( = 4). The largest number is 011 ( = 3). 
    	For the fixed-size representation of any number of bits (which I name 'x'),
    	the largest number is 2^(x-1) -1. The smallest value (or the most negative value) is -1 * 2^(x-1)
    	or just one less than the largest number. 
    */
	
    return 0;
}
```

To read more about number systems and binary representations, see: [CS 101 Notes on Binary](https://ramnauth.github.io/cs%20101/2018/09/10/numbers/)

## Arithmetic

```cpp
#include <iostream>

using namespace std;
int main() {

    /* MATH OPERATIONS include:
         +      addition 
         -      subtraction
         *      multiplication
         /      division
         %      modulus 
         ++     increment by 1 aka add 1
         --     decrement by 1 aka subtract 1
    */
	
    cout << "5 + 2 = " << 5 + 2 << endl;
    cout << "5 - 2 = " << 5 - 2 << endl;
    cout << "5 * 2 = " << 5 * 2 << endl;
    cout << "5 / 2 = " << 5 / 2 << endl;
    cout << "5 % 2 = " << 5 % 2 << endl;

    int num = 5;
    cout << "5++ = " << num++ << endl; // shows '5', then increments by 1;  num = 6
    cout << "++5 = " << ++num << endl; // increments by 1, then shows 7;    num = 7
    cout << "5-- = " << num-- << endl; // shows '7', then decrements by 1;  num = 6
    cout << "--5 = " << --num << endl; // decrements by 1, then shows '5';  num = 5
    
    num += 10; // num = num + 10;

    // consider the ORDER OF OPERATIONS: * and / execute first, then + and -
    cout << "1 + 2 - 3 * 2 = " << 1 + 2 - 3 * 2 << endl; // = -3
    cout << "(1 + 2 - 3) * 2 = " << (1 + 2 - 3) * 2 << endl; // = 0

    // CASTING changes the data type
    cout << "4 / 5 = " << 4 / 5 << endl; // returns 0 because an int / int = int
    cout << "4 / 5 = " << (double) 4 / 5 << endl; // returns 0.8 because double / int = double
    cout << "4 / 5 = " << (double) 4 / (double) 5 << endl; // returns 0.8 because double / double = double

    // generating RANDOM numbers
    int randNum0To99 = (rand() % 100); //random number between 0 and 99
    int randNum1To100 = (rand() % 100) + 1; //random number between 1 and 100
    cout << "Random # between 1 and 100: " << randNum1To100 << endl;

    return 0;
}
```

## Conditionals

```cpp
#include <iostream>

using namespace std;
int main() {
    // CONDITIONALS (aka BRANCHES) execute different code depending on the conditions
    
    /* COMPARISON OPERATORS
         ==     is it equal?
         !=     is it not equal?
         >      is it greater than?
         <      is it less than?
         >=     is it greater than or equal to?
         <=     is it less than or equal to?
    */
   
    bool canBeWalked = false;
    bool isLazy = true;

    if (canBeWalked){ // is false, doesn't print anything, goes to next statement
        cout << "The animal is a dog." << endl;
    } else if (isLazy) { // this statement is true, prints '... is a cat'
        cout << "The animal is a cat." << endl;
    } else { // this statement is not checked because the prev. is already true.
        cout << "The animal is a fish." << endl;
    }

    canBeWalked = true;

    if (isLazy){ // is true. Check next statement because it is not an 'else'
        cout << "The animal is a cat." << endl;
    }
    if (canBeWalked){ // is also true.
        cout << "The animal is a dog." << endl;
    }

    /* LOGICAL OPERATORS
         &&     AND     are both true?
         ||     OR      is either true?
         !      NOT     is it not true?
    */

   int age = 70;
   int ageAtLastExam = 16;
   bool isIntoxicated = false;

   if ((age >= 1) && (age < 16)){ // if age is between 1 (inclusive) AND 16 (exclusive)
        cout << "You cannot drive." << endl;
   } else if (isIntoxicated) { // if you are intoxicated
        cout << "You cannot drive." << endl;
   } else if (age >= 80 && ((age > 100) || (age - ageAtLastExam) > 5)){
        // if you are older than 100 OR
        // if you haven't take the exam in the last 5 years
        // if either of the above conditions are true AND you are 80 or older, you can't drive
        cout << "You cannot drive." << endl;
   } else { // when none of the previous conditions are not met, you can drive
        cout << "You can drive." << endl;
   }

   int bookOption = 2;

   switch(bookOption){ // evaluates an INT EXPRESSION, not a BOOLEAN EXPRESSION
        case 1:
            cout << "Harry Potter" << endl;
            break; // if bookOption == 1, don't check the other cases.
        case 2:
            cout << "The Hunger Games" << endl;
            break; // bookOption equals 2, exit switch statement.
        case 3: 
            cout << "Frankenstein" << endl;
            break;
        default: // if no cases are true
            cout << "Computer Science textbook" << endl;
   }
   
	switch(1) {
		case 1 : 
			cout << '1'; // prints "1",
		case 2 : 
			cout << '2'; // then prints "2"
	}	
	
	switch(1) {
		case 1 : 
			cout << '1'; // prints "1"
			break;       // and exits the switch
		case 2 : 
			cout << '2';
			break;
	}
	

   /* TERNARY OPERATOR
        variable = (condition) ? true : false
   */
    int largestNum = (5 > 2) ? 5 : 2;
	
	/* ORDER OF EVALUATION
		1. ( )			parentheses
		2. !			NOT
		3. */%			division, multiplication, modulus
		4. +-			addition, subtraction
		5. < <= > > =	comparison operators
		6. == != 		equality operators
		7. &&			AND
		8. ||			OR
	*/

	return 0;
}
```

## Loops

```cpp
#include <iostream>

using namespace std;
int main() {

	// a FOR LOOP that counts from 0 to 25
	for (int i = 0; i <= 25; i++){
		cout << i << " ";
	} cout << endl;

	// The WHILE LOOP that generates random numbers until a random number equals 10
	while (randNum != 10){
		cout << randNum << " is not equal to 10." << endl;
		randNum = (rand() % 10) + 1; //regenerate a random number
	} cout << "Random number equals 10. Exiting loop." << endl;

	int index = 0;
	while (index <= 25){ // will simulate a FOR loop counting to 25
		cout << index << " ";
		index++;
	} cout << endl;

	// a DO WHILE LOOP that plays a guessing game with the user until the user guess the correct number
	string numberGuessed; // a STRING is a series of chars
	int intNumberGuessed = 0; 

	do {
		cout << "Guess a number between 1 and 10: ";
		getline(cin, numberGuessed); // get USER INPUT and store it into variable numberGuessed
		intNumberGuessed = stoi(numberGuessed); // convert string to int with stoi
	} while (intNumberGuessed != 4);
	cout << "You guessed the correct number!" << endl;

	return 0;
}
```

## Strings

```cpp
#include <iostream>
#include <string> // this include statements tells the preprocessor to get the file containing the relevant string functions

using namespace std;
int main() {
    string myDogFirstName = "Fluffy";
    string myDogLastName = "Marie Alfonso James";
    string myDogSuffix = "Jr. III";
    
	// combine or CONCATENATE strings with +
    cout << "My dog's name is " << myDogFirstName + " " + myDogLastName + " " + myDogSuffix << endl;

    // getting and storing USER INPUT
    string yourName;
    cout << "What is your name? ";
    getline(cin, yourName);
    cout << "Hello " + yourName + "!" << endl;

    // converting string to other data types
    double fivePIdigits = 3.1415;
    string piGuess;
    double piGuessDouble; 
    
    cout << "What are the digits of pi? ";
    getline(cin, piGuess);
    piGuessDouble = stod(piGuess); //convert string to double with stod
    
    if (piGuessDouble == fivePIdigits){
        cout << "You are right." << endl;
    } else {
        cout << "You are wrong." << endl;
    }

    // other functions of the string class
    cout << "Size of string " << piGuess.size() << endl; //returns # of chars
    cout << "Is the string empty? " << piGuess.empty() << endl; //returns 0 if empty, 1 if not.
    cout << piGuess.append( " was your guess.") << endl; // appends to end of string

    string alpha = "alpha";
    string beta = "beta";

    cout << "Alpha < Beta denoted as " << alpha.compare(beta) << endl; // returns -1; in alphabetic order, 'alpha' comes before 'beta'
    cout << "Alpha == Alpha denotes as: " << alpha.compare(alpha) << endl; // returns 0; 'alpha' is equal to 'alpha'
    cout << "Beta > Alpha denoted as: " << beta.compare(alpha) << endl; // returns 1; in alphabetic order, 'alpha' comes after 'beta'

    string wholeName = yourName.assign(yourName);
    cout << "Your whole name is: " + wholeName << endl;

    string firstName = wholeName.assign(wholeName, 2, 5); // grabs 5 characters from index 2; 'becca' from 'Rebecca'
    cout << "Your first name is: " + firstName << endl;

    int lastNameIndex = yourName.find("Ramnauth", 0); // search for 'Ramnauth' in yourName starting at index 0
    cout << "Index of last name: " << lastNameIndex << endl; 

    yourName.insert(7, " Ann Marie");
    cout << "Your new name is " + yourName << endl;

    yourName.erase(8, 4); // delete 4 characters starting at 8th char
    cout << "Your new name is " + yourName << endl;

    yourName.replace(14, 8, "Robins"); // replace 8 characters starting at 14th char with 'Robins'
    cout << "Your new name is " + yourName << endl;
    
    return 0;
}
```

In the case you want to ignore all escape characters, use the following methods for getting **raw-input**.
```cpp
#include <iostream>
#include <string>

using namespace std;

int main(){
  // Method 1: using '\\' instead of '\'
  cout << " ============================================== "      << endl;
  cout << "  ___   ___   _  __  ___  __  __   ___   _  _   "      << endl;  
  cout << " | _ \\ / _ \\ | |/ / | __||  \\/  | / _ \\ | \\| |  " << endl;
  cout << " |  _/| (_) || ' <  | _| | |\\/| || (_) || .` |  "     << endl;
  cout << " |_|   \\___/ |_|\\_\\ |___||_|__|_| \\___/ |_|\\_|  " << endl;
  cout << " ============================================== "      << endl;

  // Method 2: using raw string literals
  cout << R"( ============================================== )" << endl;
  cout << R"(  ___   ___   _  __  ___  __  __   ___   _  _   )" << endl;  
  cout << R"( | _ \ / _ \ | |/ / | __||  \/  | / _ \ | \| |  )" << endl;
  cout << R"( |  _/| (_) || ' <  | _| | |\/| || (_) || .` |  )" << endl;
  cout << R"( |_|   \___/ |_|\_\ |___||_|__|_| \___/ |_|\_|  )" << endl;
  cout << R"( ============================================== )" << endl;        

  return 0;
}
```