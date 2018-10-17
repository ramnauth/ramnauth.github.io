---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: C++ Review Sheet

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   C++ review sheet, updated as of **10/08/2018**

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

1. [Basics](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#basics) - Mon, Sept. 10; Quiz Mon, Sept. 17
2. [Data Types](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#data-types) - Mon, Sept. 10; Quiz Mon, Sept. 17
3. [Arithmetic](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#arithmetic) - Wed, Sept. 12; Quiz Mon, Sept. 17
4. [Conditionals](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#conditionals) - Mon, Sept. 17
5. [Loops](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#loops) - Wed, Sept. 19
6. [Strings](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#strings) - Wed, Sept. 19
7. [Functions](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#functions) - Mon, Sept. 24 ([L1](https://ramnauth.github.io/cs%20102/2018/09/24/functions/)); Wed, Sept. 26 ([L2](https://ramnauth.github.io/cs%20102/2018/09/26/functions-2/))
8. [Scope](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#scope) -  Wed, Sept. 26
9. [Recursion](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#recursion) - Wed, Oct. 3; TB-Continued
10. [Arrays](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#arrays) - Wed, Oct. 10
11. [Vectors](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-review/#vector) - Wed, Oct. 10

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

## Functions

```cpp
#include <iostream>
#include <cmath>
#include <string>

using namespace std;

int addNumbers(int a, int b) {
    int sum = a + b;
    return sum;
}

int addNumbers(int c, int d, int f) { // overloading addNumbers() -- two functions have the same name, but different parameters
    int sum = c + d + f;
    return sum;
}

int multiplyNumbers(int a, int b) {
    int product = a * b;
    return product;
}

int subtractNumbers(int a, int b) {
    int result = a - b;
    return result;
}

int divideNumbers(int a, int b) {
    if (b != 0) { //cannot divide by 0
        cout << "Divide by 0 error." << endl;
        return -21312; //you have to return an integer.
    } else {
        int quotient = a / b;
        return quotient;
    }
}

int showMenu(){
    cout << "Choose which option you'd like to perform: " << endl;
    cout << "1. Add 2 integers" << endl;
    cout << "2. Add 3 integers" << endl;
    cout << "3. Subtract 2 integers" << endl;
    cout << "4. Multiply 2 integers" << endl;
    cout << "5. Divide 2 integers" << endl;

    int choice;
    cin >> choice;
    return choice;
}

int enterNumber(){
    cout << "Enter a number: ";
    int num;
    cin >> num;
    return num;
}

int main(){
    cout << "----------------------------" << endl;
    cout << "         CALCULATOR         " << endl;
    cout << "----------------------------" << endl;

    int x, y, z; //declare 3 variables

    int operation = showMenu();
    
    switch(operation){
        case 1: // add 2 numbers (x and y)
            x = enterNumber();
            y = enterNumber();
            cout << x << " + " << y << " = " << addNumbers(x, y) << endl;
            break;
        case 2: // add 3 numbers (x, y, and z)
            x = enterNumber();
            y = enterNumber();
            z = enterNumber();
            cout << x << " + " << y << " + " << z << " = " << addNumbers(x, y, z) << endl;
            break;
        case 3: // subtract 2 numbers
            x = enterNumber();
            y = enterNumber();
            cout << x << " - " << y << " = " << subtractNumbers(x, y) << endl;
            break;
        case 4: // multiply 2 numbers
            x = enterNumber();
            y = enterNumber();
            cout << x << " * " << y << " = " << multiplyNumbers(x, y) << endl;
            break;
        case 5: // divide 2 numbers
            x = enterNumber();
            y = enterNumber();
            cout << x << " / " << y << " = " << divideNumbers(x, y) << endl;
            break;
        default:
            cout << "You did not enter a valid menu choice. Try again." << endl;
            showMenu();
    }

    return 0;

    /* Example output:
        Choose which option you'd like to perform:
        1. Add 2 integers
        2. Add 3 integers
        3. Subtract 2 integers
        4. Multiply 2 integers
        5. Divide 2 integers
        2
        Enter a number: 4
        Enter a number: 5
        Enter a number: 4
        4 + 5 + 4 = 13
    */
}
```

## Scope
```cpp
#include <iostream>

using namespace std;

int x = 10;

int main() {
    int x = 4; 
    
    cout << "Global x = " << ::x << endl;
    cout << "Local x = " << x << endl;
    
	return 0;
}
```

```cpp
#include <iostream>

using namespace std;

int x = 10; // global

int addNumbers(int x, int y) {
    return x + y; // local
}

int incrementNumber(int num) {
    return num + 1; // local
}

int main() {
    int y = 5; // local
    y = incrementNumber(y);
    cout << addNumbers(x, y);
    return 0;
}
```

## Recursion
```cpp
#include <iostream>

using namespace std;

int getFactorial(int number); // does not recurse to get factorial of a number
int getFactorialRecursively(int number); // recurses to get factorial of a number

int main() {
    cout << "8! = " << getFactorial(8) << endl;
    cout << "5! = " << getFactorial(5) << endl;
    cout << "0! = " << getFactorial(0) << endl;

    cout << "8! = " << getFactorialRecursively(8) << endl;
    cout << "5! = " << getFactorialRecursively(5) << endl;
    cout << "0! = " << getFactorialRecursively(0) << endl;
	
	return 0;
}

int getFactorial(int number){
    int num = number; //just storing param for safekeeping
    int factorial = 1;
    while(num > 0){
        factorial = factorial * num; 
        num--;
    }
    return factorial;
}

int getFactorialRecursively(int number){
    int factorial;
    if (number == 1) // this base case tells the recursive function when to stop
        factorial = 1;
    else 
        factorial = getFactorial(number - 1) * number; // recursive because it calls itself
    return factorial;

    /* behind the scenes of getFactorialRecursively(5):
            getFactorialRecursively(5) --> else statement --> getFactorialRecursively(4) * 5
            getFactorialRecursively(4) --> else statement --> getFactorialRecursively(3) * 4
            getFactorialRecursively(3) --> else statement --> getFactorialRecursively(2) * 3
            getFactorialRecursively(2) --> else statement --> getFactorialRecursively(1) * 2
            getFactorialRecursively(1) --> if statement --> 1 

        Now we know: 
            getFactorialRecursively(2) = getFactorialRecursively(1) * 2 = 1 * 2
            getFactorialRecursively(3) = getFactorialRecursively(2) * 3 = 1 * 2 * 3
            getFactorialRecursively(4) = getFactorialRecursively(3) * 4 = 1 * 2 * 3 * 4
            getFactorialRecursively(5) = getFactorialRecursively(4) * 5 = 1 * 2 * 3 * 4 * 5

        Therefore:
            getFactorialRecursively(5) = 1 * 2 * 3 * 4 * 5 = 120
    */
}
```

## Arrays
```cpp
#include <iostream>

using namespace std;

int main() {
	cout << "-----------------------------------" << endl;
    cout << "              ARRAYS               " << endl;
    cout << "-----------------------------------" << endl;
    // arrays store multiple values of the same data type, like baskets
    
    int luckyNums[5]; // says that this "basket" called luckyNums can hold only 5 integers
    
    int unluckyNums[5] = {4, 6, 1, 9, 78}; // these are the integers in my "basket" called unluckyNums
    
    cout << "First unlucky number = " << unluckyNums[0] << endl;
    cout << "Second unlucky number = " << unluckyNums[1] << endl;
    cout << "Last unlucky number = " << unluckyNums[4] << endl;

    // MULTIDIMENSIONAL ARRAYS means baskets of baskets
    char name[2][5] = {
		{'B', 'e', 'c', 'k', 'y'}, 
		{'R', 'a', 'm', 'e', 'n'}
	};
    
    // name[index of which row?][index of which column?]
    cout << "2nd letter in the 2nd array: " << name[1][1] << endl;
    cout << "1st letter in the 1st array: " << name[0][0] << endl;
    cout << "Last letter in the last array: " << name[1][4] << endl;

    name[0][4] = 'i'; // changing last letter of first array to 'i'
    cout << "Last letter in the 1st array: " << name[0][4] << endl;

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 5; j++) {
            cout << name[i][j];
        }
        cout << " ";
    }
	
return 0;
}
```

## Vectors
```cpp
#include <iostream>

using namespace std;

int main() {
	cout << "-----------------------------------" << endl;
    cout << "             VECTORS               " << endl;
    cout << "-----------------------------------" << endl;
    // just like arrays, except their size could change

    vector <int> lotteryNumVect(10); // initializes vector with 10 zeros
    int lotteryNumArray[5] = {4, 13, 14, 24, 34};
	
    // at the beginning of vector, insert elements 0, 1, and 2 of array
    lotteryNumVect.insert(lotteryNumVect.begin(), lotteryNumArray, lotteryNumArray+3);
	
    for (int i = 0; i < lotteryNumVect.size(); i++){
        cout << "Value at index " << i << " = " << lotteryNumVect.at(i) << endl;
    }

    lotteryNumVect.insert(lotteryNumVect.begin()+5, 44); //add number 44 to vector at index 5
    cout << "Item at index 5 = " << lotteryNumVect.at(5) << endl;
    
    lotteryNumVect.push_back(64); // insert number 64 to the end of the vector
    
    cout << "Last value = " << lotteryNumVect.back() << endl; // get last/back element
    cout << "First value = " << lotteryNumVect.front() << endl; // get first/front element
    cout << "Is the vector empty? " << lotteryNumVect.empty() << endl; // returns an int (0 = false, 1 = true)
    cout << "Size of vector = " << lotteryNumVect.size() << endl; // how many elements?
    
    lotteryNumVect.pop_back(); // removes last element
    cout << "New size of vector = " << lotteryNumVect.size() << endl; // size has decreased by 1

return 0;
}
```