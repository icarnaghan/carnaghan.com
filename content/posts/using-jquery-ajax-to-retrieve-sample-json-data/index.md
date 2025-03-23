---
author: "icarnaghan"
title: "Using jQuery.AJAX() to Retrieve Sample JSON Data"
date: 2016-10-10
categories: 
  - "coding"
tags: 
  - "cmst-488"
---

Traditionally the X in AJAX has usually equated XML (eXtensive Markup Notation). In recent years, JSON (JavaScript Object Notation) has taken over in many cases due to its overall efficiency and ease of use. In general, JSON is a much less verbose syntax, which has gained a lot of popularity in modern JavaScript frameworks. Part of this popularity can be attributed to the fact that JSON data can be parsed quicker and because it's less verbose, less bandwidth is needed to transmit it back and forth. In this overview we will look at how easy it is to get up and running consuming JSON data using the popular jQuery library.

> I recently published an updated article on retrieving sample JSON data using JavaScript natively. See Using JavaScript Fetch API to Retrieve sample JSON data for more details.

Out of the box, jQuery comes standard with a number of Ajax related functions that can be used to request, send and manipulate JSON data. A full list of these functions can be found in the jQuery documentation. In the examples that follow, we will be using the $.ajax function.

## Step 1 - Writing the JSON File

In our first step, we need to create a basic json file that will contain records of information to display on the web page. In this example I am going to simply include a list of five training and reading resources for JavaScript:

- You Don't know JS - Book Series (Kyle Simpson): https://github.com/getify/You-Dont-Know-JS
- Shaping Up with Angular.JS (Code School): https://www.codeschool.com/courses/shaping-up-with-angular-js
- HTML/JS: Making webpages interactive with jQuery (Khan Academy): https://www.khanacademy.org/computing/computer-programming/html-js-jquery
- JQuery AJAX (W3 Schools): http://www.w3schools.com/jquery/jquery\_ajax\_intro.asp
- JQuery API Documentation (jQuery): https://api.jquery.com/

You will note each entry includes a name, provider (or author) and the URL to the resource. Next we need to place the above information into a properly formatted JSON text file. Normally JSON will be provided via a service or API call, however in this example we are simply going to create our own and include three fields for name, provider, and URL.

<script src="https://gist.github.com/icarnaghan/f832ad67f36791beac2fd5943bf0f246.js?file=resources.json"></script>

In order to ensure our JSON is valid, it is always a good idea to run it through the free JSON Lint service. Save your json file as **resources.json**.

## Step 2 - Creating the JavaScript file to handle our JSON

Now that we have our JSON file created, we will need to write some JavaScript in order to parse it correctly on our web page. Thankfully jQuery has a number of helpful libraries that make the AJAX call to our JSON file relatively straight forward. The code that follows demonstrates use of jQuery.Ajax(). Save your file as **script.js**.

<script src="https://gist.github.com/icarnaghan/f832ad67f36791beac2fd5943bf0f246.js?file=script.js"></script>

In the above code, we are using the standard document.ready function to wrap our code inside so that nothing executes until the page is ready. An event click function follows that targets the #retrieve-resources id, which we will add to a button on our HTML document. Within this function is the heart of our code, the jQuery.Ajax call. In our example we are only using type, url and success attributes. Type defines whether we are expecting a get or post response, the url points to our JSON file. In this case url is a relative path, we would normally define an absolute link to a given service that would provide a JSON response. We are not using the data attribute, which is commonly used to provide data sent to the server via the previously stated 'get' response. Since this example provides a static JSON implementation, data is not needed, however normally this would be required when interacting with a service. The success attribute contains the 'result' variable, in this case our JSON data. For a better example of using the data attribute with form data, see this parse.js example which defines form\_data username and password variables.

After we have retrieved our data from the JSON file, we can simply use a basic for loop to iterate over its contents and then place into an HTML string that will later be rendered as a table in this example on our web page. Additionally I have added a table class here as our HTML file will use the Bootstrap framework for nicer styling of our finished page.

## Step 3 Creating our HTML Page

Finally we are ready to bring everything together in our basic HTML page. The code follows. Save your file as **index.html**.

<script src="https://gist.github.com/icarnaghan/f832ad67f36791beac2fd5943bf0f246.js?file=index.html"></script>

Our above html simply used the free Bootstrap CDN for styling and setups up our display-resources section with a link and id for retrieve-resources. The retrieve-resources id will trigger the click event in our JavaScript code, which will in turn replace the placeholder content inside our display-resources div with content from our JSON file.

> See the Pen jQuery AJAX JSON for a demo using the above code. (Note in this codepen demo I am using the myjson.com service to serve resources.json)

This is a relatively short and basic demo of bringing in some JSON data into an HTML file. Be sure to checkout the excellent **Pluralsight jQuery Path**, which goes into more depth with both jQuery in general and covers topics including **jQuery.getJSON** and **jQuery.Ajax**. Also for more information, refer to the jQuery.Ajax API documentation over at jQuery.
