---
author: "icarnaghan"
title: "JavaScript Arrays - Properties and Methods"
date: 2019-01-27
categories: 
  - "coding"
tags: 
  - "bitesize-javascript"
  - "cmst-388"
  - "javascript"
---

We are going to cover some of the most commonly used properties and methods in JavaScript, for working with arrays. There are a lot of other methods which are not covered here, including newer ES6 methods. The goal here is to get you started working with arrays and gaining an understanding of the fundamental ways we can access and manipulate data. The table below summarizes the various methods we will cover in this lesson:

| length property | Sets or returns the number of elements in an array |
| --- | --- |
| find methods | Returns the value (find) or index (findIndex, indexOf) of the first element in an array |
| sort, reverse, and compare | Sorts, reverses, and compares the elements of an array |
| push and pop | Adds (push) or removes (pop) new elements to the end of an array, and returns the new length |
| unshift and shift | Adds (unshift) or removes (shift) new elements to the beginning of an array, and returns the new length |
| splice and slice | Adds/Removes elements from an array (splice) or selects a part of an array, and returns the new array (slice) |
| concat | Joins two or more arrays, and returns a copy of the joined arrays |

For a more complete list, please be sure to check out the W3 Schools JavaScript Array Reference.

## The length property

The length property is extremely useful to determine the number of elements in a given array. In your console try entering **students.length**. You will be presented with the number of elements in our students array (in this case 4). Because length is a property, no arguments are needed here nor are empty brackets. The property simply returns the number of elements as expected and does not provide additional functionality.

## The find, findIndex, and indexOf methods

The find method can be used to locate an element within your array. It works by passing in a callback function to the find array method. If you recall in our earlier lesson on JavaScript Functions, we discussed that functions can be defined as variables. Callback functions (sometimes referred to as higher-order functions) are simply functions or variables defined as a function expression, that have been passed into another function as an argument. The array find method expects a function passed as an argument, which we can do. This is better illustrated through an example.

<script src="https://gist.github.com/icarnaghan/fd6d75786fb66ed4c54ebf6f764911e7.js?file=script-part-2.js"><span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span></script>

The find method expects a callback function with an element. In this case we are evaluating the element value and returning the first array element containing a value over 89 (assuming a grade of A would be 90 or above). We could also simplify this further by using an arrow function if we wish:

```
let aGrade = examResults.find(element => element > 89);
```

You might be thinking, "Why not just provide a means to send a value to the find method instead of a callback function?" The callback function allows us to evaluate more complex scenarios. Say for example, you wanted to locate the first odd number in an array. This could be done by writing a function to evaluate a number using the modulus arithmetic operator. More complex functions could be written to find values based on different criteria.In a similar manner to find, the findIndex method also lets us search an array. Remember earlier I mentioned an array is zero-based, meaning that it's index begins with zero. Let's look at how this might be represented in our students array:

| Index | Value |
| --- | --- |
| 0 | John Smith |
| 1 | Michael Johnson |
| 2 | Paula Sanford |
| 3 | Jenny Carter |

Let's say we wanted to determine the location of Michael Johnson. We can do this by simply using the findIndex method as follows:

```
let mjIndex = students.findIndex(element => element == "Michael Johnson");
console.log("Michael Johnson is at Index: " + mjIndex);
```

Here we are passing in an arrow function evaluating the "Michael Johnson" against each array element. The first index found will yield the result 1. An alternative to findIndex is the indexOf method, which essentially provides the same result but does not require a callback function as its argument. Try adding both to your script file below.

<script src="https://gist.github.com/icarnaghan/fd6d75786fb66ed4c54ebf6f764911e7.js?file=script-part-3.js"><span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span><span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span></script>

## The sort and reverse methods

The sort array method does exactly what you would expect, it sorts the elements in your array. By default this operation is done on string values, so for example if you wanted to sort the earlier defined students array you could do so by using sort:

```
console.log(students.sort());
```

This yields a list of the students sorted alphabetically (by first name in this example). In contrast to this, reverse can be used to sort in descending alphabetic order:

```
console.log(students.reverse());
```

This is fine for string values, however sort and reverse do not work as well for numbers. In order to demonstrate this I'm going to add an additional value to our examResults array. Let's take a look at how we add and remove elements.

## The push and pop methods

Push and pop are methods used to add and remove elements from an array. Imagine that the array is a stack and by using the push method you would be adding an additional element on the end of that stack. The pop method pops the new element off the stack so it works in a Last In First Out (LIFO) process. As with most things, this is best demonstrated through example. Open your script file and add the following methods on the end:

<script src="https://gist.github.com/icarnaghan/fd6d75786fb66ed4c54ebf6f764911e7.js?file=script-part-4.js"></script>

Notice the first command we enter under the 'push and pop' comment adds two new elements to our array with the numeric values 100 and 72. By using the pop method we eliminate the last element in our array leaving only the newly added 100 value along with the original array values.

## Revisiting sort with compare

Now that we have added 100, let's go back and revisit sort. Try entering the following into your console and see if the results are as you expected:

```
console.log(examResults.sort());
```

Did you notice the sort is not working as well as we expected here? The reason for this is because sort by default works with strings (non numeric) data. When it tries to sort numbers it sees that 1 is less than 7 without taking into regard the entire numbers. In order to get around this problem, we need to leverage additional functionality of the sort method. Thankfully, JavaScript includes a 'compare' function that allows us to sort numeric data and even control the sort order. The compare function will accept two parameters at a time (a and b) and compare their values. The result will yield on of the following:

- Return greater than 0 if a is greater than b
- Return 0 if a equals b
- Return less than 0 if a is less than b

Take the following example and consider the first three values of our examResults array 88, 79, 92 . . .

```
function(a, b){return a-b}

compare(88,79); // Returns 9, a is greater than b
compare(88.92); // Return -4, a is less than b
compare(79,92); // Return -13, a is less than b
```

The compare function when combined with array.sort() will be called on pairs in the to-be-sorted array elements, which will enable proper ordering. Let's put it all together. Update your **script.js** file to include the code under the 'sort and compare' comments:

<script src="https://gist.github.com/icarnaghan/fd6d75786fb66ed4c54ebf6f764911e7.js?file=script-part-5.js"><span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span></script>

You should now notice that sort with compare will yield the correct sort order of numbers.

## The unshift and shift methods

Just like the push and pop methods, unshift and shift provides the functionality to add and remove element from an array. The main difference between them is that unshift and shift add and remove elements from the beginning of an array. Let's take another look at our students array. Say we wanted to add a new student at the beginning of the list called Julia Brown. The shift method will let us do this. Let's give it a try. In your console run the following command (make sure your index.html file referencing script.js is open in your browser):

```
students.unshift("Julia Brown")
console.log(students);
```

You should now see an updated array reflected in the table below. Note that Julie Brown is now at the zero index essentially shifting the other elements up one.

| Index | Value |
| --- | --- |
| **0** | **Julia Brown** |
| 1 | Paula Sanford |
| 2 | Michael Johnson |
| 3 | John Smith |
| 4 | Jenny Carter |

**_Note your array order might look differently if you didn't apply the reverse sort method earlier._**

To remove Julia Brown, the shift method can be used (note shift does not require an argument):

```
students.shift();
console.log(students);
```

Review the results from the console. You should see the student array return to its previous list without Julia Brown. Unshift simply removes the first element in an array. If you were to enter students.shift(); again, the next element at the beginning of the array (at index 0) would be removed (John Smith).

## The splice and slice methods

The push and pop, unshift and shift methods are convenient for easily adding and removing elements to the beginning or end of our array. What if we want to add or remove a specific range of elements? This is where the splice and slice methods come in handy. Both of these methods can target a range of elements, making it easier to copy into a new array (slice) or delete them entirely and add replacements (splice). Let's take a look at an example. Taking our students array again, let's say we wanted to remove Michael Johnson and Paula Sanford. For reference I've included our array contents below. Note Michael is at index 1.

| Index | Value |
| --- | --- |
| 0 | Paula Sanford |
| 1 | Michael Johnson |
| 2 | John Smith |
| 3 | Jenny Carter |

In order to remove Michael, we need to provide an argument to the splice method that indicates the beginning index of the range to be modified. We also need to specify a second argument that provides the number of elements to change or remove in this case. Our method should look like:

```
students.splice(1, 1); // 1 = starting index, 2 = removal of 1 element
console.log(students); // Michael has been removed
```

Our array will now look something like this:

| Index | Value |
| --- | --- |
| 0 | Paula Sanford |
| 1 | John Smith |
| 2 | Jenny Carter |

Notice that Michael has been deleted from our array and we are left with Paula, John and Jenny, with John now at index 1. Let's look at another scenario where we have been told that Paula and Jenny are being replaced with 2 new students. The splice method will let us selectively delete at our specified index as well as add new elements. Take a look at the code below:

```
students.splice(1, 2, "Frank Welker", "Peter Cullen"); // Removing and adding students
console.log(students);
```

In this example we removed John and Jenny and replaced them with Frank and Peter. Another handy method for selecting and manipulating parts of an array is the slice method. It works in a similar manner to splice except it copies and places the range of selected elements into a new array. Let's say we wanted to create a new list of students who were receiving financial aid. For the sake of simplicity lets imagine we already know the students and their index locations (Paula and Frank). Take a look at the example below:

```
let financialAid = students.slice(1,  3); // selecting 2 students starting at index 1
console.log(financialAid);
```

The first parameter specifies the start of the list of elements you want to copy from the array. The second argument specifies the end of the selection. Note: the end of the selection should be the index of the last item you want to select + 1. Both of these parameters are optional. (If you do not specify a start argument, all items up to the end argument will be copied, likewise if no end is specified all items from the start argument will be copied. To copy the entire array you do not supply any arguments:

```
let examResultsCopy = examResults.slice();
console.log(examResultsCopy);
```

## The concat method

The concat method is handy for combining different arrays together. Keeping with our student examples, imagine we have three lists of rooms at a university for auditoriums, research labs, and classrooms and we want to merge them. Using arrays with the concat method would look like this:

```
let auditoriums = [23,67];
let researchLabs = [55,89,145,3];
let classrooms = [323,345,665,534,544]
let allRooms = auditoriums.concat(researchLabs, classrooms);
console.log(allRooms);
```

```
As you can see, this method is convenient for quickly merging arrays together. It will accept one or more arrays to concatenate from the starting array (auditoriums) and place them together in a new array allRooms.
```

To recap on everything covered in this lesson I've included all of the code used in the above examples below for reference.

<script src="https://gist.github.com/icarnaghan/fd6d75786fb66ed4c54ebf6f764911e7.js?file=script-part-6.js"></script>

We covered a lot of material in this lesson, so feel free to bookmark this page and use it as a reference. The best way to learn is through practice.
