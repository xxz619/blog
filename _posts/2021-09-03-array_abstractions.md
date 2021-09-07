---
layout: post
title: "Array Processing Abstractions"
excerpt_separator: <!--more-->
permalink: "array-abstractions"
categories:
- Learn
tags:
- Launch School
- Arrays
- Javascript
- abstractions
---

An array in Javascript is simply a list of values. In order to do something with that list, usually we would need to 'step through' or 'iterate' over that list to perform a specific action on each value. Javascript provides us with a few different types of iteration methods; each one of them processing each element or value and determining in the end the result return value. These high-level abstractions help us to write code that is closer to our intentions as a programmer and helps us to focus on *what* to do with an array as opposed to *how* to iterate over it. All of these methods accept functions as arguments, or callback functions, and executing that callback function for each element. The callback function itself is passed 3 arguments on each call: the current element in the array, the index of that element and optionally, the array itself. When searching for the right processing abstraction to use in your program, there are several things you need to consider: what action you need to perform for each value, what the return value is and the type of abstraction that is needed. 

In this article, we'll discuss 3 of the 6 main list processing abstractions: `Iteration`, `Filtering/Selection`, `Transformation`. We'll start with `Iteration`. 

<!--more-->

There are many ways to iterate over an array, such as using `for`, `do...while`, `while`, etc. These are great for getting the job done, however Javascript readily provides us with a method that is built specifically to iterate over arrays and perform an operation for each element: `forEach`. `forEach` is a simple iteration method that executes its callback function for each element. Since it does not have a meaningful return value to return once iteration is completed, it simply returns `undefined`. `forEach` is used if you only need to perform side effects and is not appropriate if you need to return a meaningful value. One thing to know about `forEach`: iteration will not stop with a `return` statement or any other way of breaking out of the loop. The only way to break out of a `forEach` iteration is by raising an exception. If you need to return early from an array or break iteration for any reason, a `for`, `do...while` or `while` loop will be the best choices. 

Here's an example with `forEach`. Say we have a small array that contains 4 strings, each string representing a season of the year. We simply want to log each string to the console as part of a sentence. `forEach` is perfect for this. We are performing a side effect, logging something to the console, and we don't necessarily care, or need to, return something meaningful to the program. We can use the handy `=>` array syntax to make a clean one-liner solution to this problem. Of course, it's not necessary or required, but it's common to see `forEach` used this way, since it is shorthand and faster to type. As we can see, there isn't anything crazy happening in this code; we simply iterate over the `seasons` array, logging the season to the console as part of a sentence. 

```javascript
let seasons = ['spring', 'summer', 'fall', 'winter'];

seasons.forEach(season => console.log(`Yay, it's ${season}!`));

// Logged to the console: 

"Yay, it's spring!"
"Yay, it's summer!"
"Yay, it's fall!"
"Yay, it's winter!"

// Returns

// undefined
```

The second array processing abstraction deals with selecting or filtering. This is one of my favorite list-processing abstractions. Selecting or filtering an array means that as we iterate through an array, we are checking each value to see if it passes some criteria established by our callback function. If it does, we *select* that element and put it into a new array object. `filter` is the array method that does this, and it's intention seems clear by it's name. We want to `filter` out elements that we don't want, and will only be left with elements that we do want. `filter` always returns a *new array* with the selected elements within it. 

An example is needed to show how it works. Say we have an array of random numbers, and we want to return an array that only contains odd numbers. Naturally `filter` is the perfect method for this type of work. Our mental model could be: "I want to filter through this array, selecting only the odd numbers, putting them into a new array, and finally return that array once iteration is complete". Based off of our mental model, we can safely assume that we will be iterating with `filter`. What's great about a high-level abstraction such as `filter`, is that we don't need to worry about how to iterate and select those elements that are true for our callback function. `filter` simply takes care of the implementation details. All we need to do is pass a callback function that itself holds the expression that checks if a number is odd. 

In this example, `numbers` is an array that contains 7 random out of order numbers. We pass a callback function `number => number % 2 !== 0` to `filter` as an argument. During iteration, each number is assigned to the variable `number` and processed in the expression `number % 2 !== 0`. This expression checks to see if the current number is not evenly divisible by 2. If it isn't, that means it's odd and it will thus be selected. The odd numbers array is saved to variable `oddNumbers` and is then logged to the console. As we can see from the output, only odd numbers are contained in the `oddNumbers` array.

```javascript
let numbers = [3, 5, 2, 9, 1, 7, 8];

let oddNumbers = numbers.filter(number => number % 2 !== 0);

console.log(oddNumbers); // [ 3, 5, 9, 1, 7 ]
```

The final list processing abstraction we'll talk about today is called *transformation*. This is my second favorite type of abstraction! I love to see values being transformed in an array. The method used for this type of abstraction is called `map`. It works in the same way as `forEach` and `filter` in that it iterates over a list of values, but the difference is `map` executes the callback function for each element, *transforming* that element in place and putting into a new array, to be returned at the end of iteration. While the element *itself* isn't changing, a new value is computed and will replace the old value in the returned array. Like `forEach` and `filter`, `map` takes a callback function as its single argument and executes this callback function for each element in the array. 

Let's look at an example. A common use case for `map` would be calculating some sort of mathematical operation with numbers. Say we had an array of numbers from `1-5`. We want to return an array of numbers that are the squares of the original numbers in the array. `map` would 'transform' the elements by computing their squares and putting the new values into the new array. In this example, we will only pass each individual number to the callback function. The returned array is `[1, 4, 9, 16, 25]`. Each number in this array is the square of that corresponding number in the `numbers` array. Neat!

```javascript
let numbers = [1, 2, 3, 4, 5];

let squares = numbers.map(number => number * number);

console.log(squares); // [1, 4, 9, 16, 25]
```

This article discussed 3 list processing abstractions and the Javascript methods that carry out the abstractions. They are designed to make life easier by helping us to write code that make our intentions clear as programmers in terms of what we want our program to do. We don't need to focus on the implentation details of 'how to do something'. Each method 'knows' how to iterate and do it's job, such as simple iteration, selection, or transformation. All we need to do is supply the 'whats' of the program: "What are we trying to do in this code?", or "What is my intention for this program?". In the next article, we'll talk about the last 3 list processing abstractions, `ordering`, `reducing/folding` and `interrogation`. Thanks for reading!