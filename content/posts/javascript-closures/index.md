---
author: "icarnaghan"
title: "JavaScript Closures"
date: 2019-09-15
categories: 
  - "coding"
tags: 
  - "javascript"
---

Anyone who has worked in JavaScript for any amount of time will likely come across concepts that require a deeper level of study in order to fully understand. Closures is certainly one of those areas that has caused me to review and experiment with several times. The purpose of this article is to provide a succinct overview of closures and offer several snippets of code to play around with in order to better understand this often tricky to grasp concept. Consciously or Unconsciously, most developers use closures while programming in JavaScript. Most of the time, everything works fine, but it is always better to understand how they work as they provide better control over your code. Moreover, at some point you might be asked to explain what closures are and hopefully by the end of this you will be in a much better position to do that. So let's start with what a closure is. A simplified explanation would be that a closure is an inner function that has access to the variables of the outer function. This is called the scope chain. See my earlier article on JavaScript Scope if you need a refresher.

A closure has three scope chains:

- Access to its own variables.
- Access to variables within the outer function.
- Access to global variables.

A closure has access to the parameters of the outer function. It cannot call the outer function’s arguments object, but calling the outer function's parameters directly is possible.

Some of this is easier to understand with the help of an example.

<script src="https://gist.github.com/icarnaghan/518ce2fcf4e86a3a9a65daf912e2610c.js?file=script-part-1.js"></script>

In the above code, we have two functions, outer and inner. The inner function is a closure declared inside the outer function. The inner function is returning a variable that is declared in the outer function and the outer function returns the inner function. Pay attention to the following line of code.

```
var get_inner = outer();    
```

Here, we are done with the execution of the outer function. The entire body of the inner function is returned and stored in the get\_inner variable. Let's take a look at what will happen in the next line.

```
console.log(get_inner())
```

Here we are calling the inner function that is stored in the get\_inner variable. This will print the value of the variable val, that was declared inside the outer function. This happens because the variable val is in the **scope** of the inner function.

As mentioned earlier, the inner function also has access to the parameters of the outer function. In order to better understand this, let's look at another example.

<script src="https://gist.github.com/icarnaghan/518ce2fcf4e86a3a9a65daf912e2610c.js?file=script-part-2.js"></script>

In this example we are setting the variable get\_inner to the outer function passing an argument of 100. The outer function passes back the inner function in its return statement. We now have access to the inner function via get\_inner and can pass it an argument of 50. When we call get\_inner (50), we are executing the outer function with an argument of 100, which in turn returns inner, where we pass in 50. These values are summed and yield a result of 150.

```
var get_inner = outer(100);  
```

The execution of the outer function ends here. But still, when we use get\_inner to call the inner function, The inner function returns the correct sum of the arguments. This happens because the closures can access the parameters of the outer function.

We can also store anonymous functions at every index of an array.

<script src="https://gist.github.com/icarnaghan/518ce2fcf4e86a3a9a65daf912e2610c.js?file=script-part-3.js"></script>

In the above javascript code, We have an outer function and in this function, we declared an array **arr**. The function returns this array. Observe the for loop in the outer function.

<script src="https://gist.github.com/icarnaghan/518ce2fcf4e86a3a9a65daf912e2610c.js?file=script-part-4.js"></script>

The for loop runs from i=0 to i=4, and at each index, we are storing the value of i at that point. Each index has a function, that is why used the following line of code to print the value returned for that function in the console.

```
get_inner[0]()
```

As the index specified here is 0, you might imagine the the value stored in it to be 0, however that is not the case. Here the value is 5. Similarly, all the indexes of this array will 5. This happens because the closures do not remember the value, they only store the reference of the variable. At the end of the for loop, the value of i is 5, thus storing the value at each index of the array.

The following shows us how to get around this problem.

<script src="https://gist.github.com/icarnaghan/518ce2fcf4e86a3a9a65daf912e2610c.js?file=script-part-5.js"></script>

Here we are passing a different argument every time the inner function is called. Now, at the 0th index, value is 0 and at the 1st index, value is 1. Similarly, all other indexes have different values.

Hopefully this example helps better articulate that closures only store the reference, not the value.

To recap, remember the following three rules about the closures.

1. Closures have access to variables of the outer function even after the outer function returns.
2. Closures have access to the parameters of the outer function.
3. Closures store the reference of variables of the outer function.

Finally, there are a few excellent articles I highly recommend you check out if you are still struggling with closures. I never understood JavaScript closures by Olivier De Meulder is probably one of the best articles I've read on explaining closures through easy to follow examples and a simple analogy to a backpack, be sure to give it a read. Secondly check out Pat Whitrock's Practical Uses for Closures. Finally, if you haven't already come across the excellent You Don't Know JS Series by Kyle Simpson, be sure to check it out and dig into his second book in the series, Scope & Closures. Good luck with your JavaScript studies!
