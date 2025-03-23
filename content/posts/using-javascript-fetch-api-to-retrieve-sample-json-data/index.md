---
author: "icarnaghan"
title: "Using JavaScript Fetch API to Retrieve sample JSON data"
date: 2018-11-11
categories: 
  - "coding"
tags: 
  - "cmst-488"
  - "javascript"
---

A while ago I wrote an article called Using jQuery.AJAX() to Retrieve Sample JSON Data. Since this time I've been slowly using more and more native JavaScript to get things done, so I thought it was time to revisit this concept using the fetch() API.

> It has been very convenient over the years to use jQuery to simplify tasks that otherwise would have been more challenging to write in native JavaScript. Since ES6 has become pretty much mainstream nowadays, it is safe to take advantage of some of the features and benefits it brings.

This article will walk you though setting up a basic response using the fetch API.

## What is Fetch API?

According to MDN Web Docs, Fetch API simply provides an interface for fetching resources. It provides a more powerful feature set over the traditional XMLHttpRequest, and it is easier to use. The fetch() method

- **accepts** one mandatory argument (this should be the path to your API or JSON resource)
- **returns** a promise (the promise will resolve to the JSON response)

Because of its simplicity, fetch has quickly become the common goto method for consuming responses from API endpoints, or in the case of the example covered here, a simple JSON response from a static file.

## Writing the JSON File

To get started we will need to first create a basic JSON file. If you followed my previous article, we will be using the same JSON file, which lists five training and reading resources for JavaScript detailed below.

- You Don't know JS - Book Series (Kyle Simpson): https://github.com/getify/You-Dont-Know-JS
- Shaping Up with Angular.JS (Code School): https://www.codeschool.com/courses/shaping-up-with-angular-js
- HTML/JS: Making webpages interactive with jQuery (Khan Academy): https://www.khanacademy.org/computing/computer-programming/html-js-jquery
- JQuery AJAX (W3 Schools): http://www.w3schools.com/jquery/jquery\_ajax\_intro.asp
- JQuery API Documentation (jQuery): https://api.jquery.com/

Each of the entries include name, provider (or author), and URL of the resource. Copy and paste the JSON code below into a text file and call it **resources.json**. Keep in mind in real life we would most likely be hitting an API endpoint with our fetch call, however for the sake of keeping this simple we are using a static file.

<script src="https://gist.github.com/icarnaghan/f832ad67f36791beac2fd5943bf0f246.js?file=resources.json"></script>

Once you're done, be sure to check your work using the free JSON Lint service.

## Writing the JavaScript and Fetch API Call

We have our JSON file created. The next step is to write some JavaScript using fetch() to retrieve the contents of our JSON file. Remember earlier I mentioned that fetch accepts one mandatory argument and returns a response. Our argument will be the JSON file itself.

<script src="https://gist.github.com/icarnaghan/ef6648c5d71b9bf07ef22731e3cc15d5.js?file=script.js"></script>

Let's break the code down.

1. document.querySelector is used to manage a click event from a button with an id of #retrieve-resources that will be used to grab the JSON
2. a variable called displayResources is set to the #display-resources id in the HTML file (see below for HTML code)
3. a temporary message, "Loading data from JSON source..." is placed in displayResources.textcontent
4. fetch() is used with the mandatory parameter of the MyJson file and returns a response
5. the result is then parsed into a variable called output using a for loop to iterate the JSON records
6. output is finally appended to displayResources.innerHtml

All of the code in the above example used native JavaScript, without the need to load additional libraries such as jQuery. The true power of fetch is both its efficiency and simplicity. In order to wrap this up, we will need to create the final HTML file that will display the information to the user.

## Writing the HTML

The HTML file is rather simple and contains the various elements needed in the JavaScript to perform our AJAX call.

<script src="https://gist.github.com/icarnaghan/ef6648c5d71b9bf07ef22731e3cc15d5.js?file=index.html"><span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span></script>

The code above uses Bootstrap and includes the retrieve-resources and display-resources ids needed for the click event and placeholder for the data retrieved from JSON. Once a user clicks the retrieve-resources link, the JS code above will begin.

> See the Pen JavaScript Fetch JSON for a demo using the above code. (Note in this codepen demo I am using the myjson.com service to serve resources.json)

That's it. This was a pretty basic tutorial, but it should be enough to get you up and running with basic requests using fetch(). For more information, be sure to check out the Fetch API documentation.
