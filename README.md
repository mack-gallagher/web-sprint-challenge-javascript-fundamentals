# Sprint Challenge - JavaScript Fundamentals

**Read these instructions carefully. Understand exactly what is expected _before_ starting this Sprint Challenge.**

This challenge allows you to practice the concepts and techniques learned over the past week and apply them in project. This Sprint explored JavaScript Fundamentals. During this Sprint, you studied array methods, this keyword, prototypes, and class syntax. In your challenge this week, you will demonstrate proficiency by completing a range of JavaScript problems.

This is an individual assessment. All work must be your own. Your challenge score is a measure of your ability to work independently using the material covered through this sprint. You need to demonstrate proficiency in the concepts and objectives introduced and practiced in preceding days.

You are not allowed to collaborate during the sprint challenge. 

## Introduction

The index.js file contains all of your challenges. Please review it in full before answering the questions. If you complete the stretch goals please leave them in your file but commented out so that they do not affect the MVP tasks. 

In meeting the minimum viable product (MVP) specifications listed below, you should have all tests passing. You can console.log to check your work and ensure you are submitting the correct results. 

### Commits

Set up codegrade early and commit your code regularly and meaningfully. 

## Interview Questions
### (please edit this file and write your answer below each question.)
Demonstrate your understanding of this week's concepts by answering the following free-form questions.

Edit this document to include your answers after each question. Make sure to leave a blank line above and below your answer so it is clear and easy to read.

1. Explain the differences between `.map`, `.reduce` and `.filter` and describe a use case for each. 


.map(), .reduce(), and .filter() are all methods of JavaScript arrays. .map and .filter are both used to return a new array that is a modified version of the array to the left of the dot, while .reduce can be used to "reduce" the array to the left of the dot into an arbitrary "accumulator" value, which can be a number, an object, or an array. 

.map takes a callback function between its parentheses and does that callback function to *every* member of the array it is called on, then returns that modified array. This might be useful if, for example, you had an array of Customer objects and in order to keep track of your target demographic you incremented each customer's .age value on January 1st; you could |const 2022Customers = 2021Customers.map(x => x.age++)|. 

.filter takes a callback function and returns an array containing only the elements of the original array for whom that callback function returns true - for example, you could filter your Customer objects by 2022Customers.filter(x => x.age > 21). 

.reduce's syntax is more complicated. Its callback function takes both the current value of your accumulator and the value of the array you are currently on, and updates the value of the accumulator after each array element according to what was returned from the callback function. In addition to the callback function, .reduce takes the starting value of your accumulator, which is usually 0 or an empty object or array. For example, to get the total age of all your customers [perhaps to find the average] you could |const totalAge = 2022Customers.reduce((acc,curr) => acc+curr.age,0)|.
  

2. Explain the difference between a callback and a higher order function.

A callback is a function that is passed to another function as an argument. A higher order function is a function that returns another function and/or takes a callback function as an argument.

3. Explain what a closure is.

A closure is the "closed" relationship between a function and the scope it was declared in, and it can be used to give a function declared from inside a higher-order function, access to the usually private variables that were also declared within that higher-order function. Even after the function exits its birthplace, when it is invoked it can access and mutate the private variables that live in its birthplace scope, because it has "closed over" them. This can be useful if we want some functions that work with private-ish variables that still maintain state.

4. Describe the four principles of the 'this' keyword.


Principle 1 [Global binding] says that in the absence of an enclosing object to refer to, 'this' refers to the global object - 'console' or 'window'. 

Principle 2 [Implicit binding] says that 'this', *inside* an object,refers to the object that it is inside. 

Principle 3 [New binding] says that Principle 2 also applies to objects returned implicitly from constructor functions invoked using the 'new' keyword - when we create a new object using eg 'const morrie = new Cat({name: 'Morrie', color: 'orange'})', the 'this'es inside Morrie's constructor function refer to the newly created morrie object. 

Principle 4 [Explicit binding] By calling .call() or .apply(), with any functions whose internals refer to 'this' *to the left of the dot*, and putting a substitute, fixed value of 'this' *inside the parentheses*, we can force the 'this' inside those functions to refer to the thing inside the parentheses for one individual call. By doing the same thing with .bind(), we can return a new, permanent function based on the function to the left of the dot, that will refer to that new, fixed 'this' *every* time it is called.
 

5. Why do we need super() in an extended class?

When emulating classes with the prototype system in JavaScript, if you want a constructor function to automatically inherit from another constructor function, it is necessary to invoke the ancestor constructor function with 'this' passed in as an argument, so that the member of the child 'class' will be instantiated with all the parent constructor's attributes. super(), combined with using the extends keyword to specify which parent class you want your class to inherit from, is just a simpler way of saying 'call the parent class's constructor on this so I get my parent constructor's attributes'.

You are expected to be able to answer questions in these areas. Your responses contribute to your Sprint Challenge grade. 

## Instructions

### Task 1: Set up Project

Using VSCode and Command Line:


1. Fork the repo
2. Go into canvas and connect your repo to codegrade
3. Clone your forked version of the repo
4. DO NOT CREATE A BRANCH. You will be pushing your changes to the main/master today
5. cd into your repo
6. open the terminal in your vs code and type `npm install`
7. next type `npm run test` in your terminal
8. Complete your work making regular commits to main/master; your codegrade score will update each time you make a push.


### Testing & Debugging

Open a second terminal inside of your project by clicking on the split terminal icon
![alt text](assets/split_terminal.png "Split Terminal")

Inside of your second terminal type `npm start` 
![alt text](assets/npm_start.png "type npm start")

You will be running your tests in one terminal and debugging in the other. As you work on your code you should make use of `console.log` to check your progress and debug.
![alt text](assets/tests_debug_terminal_final.png "your terminal should look like this")

### Task 2: Project Requirements (MVP)

You must complete all tasks inside of `index.js` and answer the questions above.

In your solutions, it is essential that you follow best practices and produce clean and professional results. Schedule time to review, refine, and assess your work and perform basic professional polishing including spell-checking and grammar-checking on your work. It is better to submit a challenge that meets MVP than one that attempts too much and does not.

## Resources
 
 [Sprint Challenge Study Guide](https://www.notion.so/bloomtech/Unit-1-Sprint-3-Study-Guide-033a9a00659a4ef98c12eb97e49a6110)

## Submission format

Please submit your project via codegrade by following [these instructions](https://bloomtech.notion.site/bloomtech/BloomTech-Git-Flow-Step-by-step-269f68ae3bf64eb689a8328715a179f9) (see part 2, submitting an assignment with codegrade).
