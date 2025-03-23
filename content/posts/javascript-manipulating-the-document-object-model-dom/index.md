---
author: "icarnaghan"
title: "JavaScript Manipulating the Document Object Model (DOM)"
date: 2019-10-14
categories: 
  - "coding"
tags: 
  - "bitesize-javascript"
  - "cmst-388"
  - "javascript"
---

The way in which logical structure of a document is accessed and manipulated in HTML is known as Document Object Model or DOM. It is a programming interface for HTML. Whenever a document loads in the browser, a tree-like (or forest) structure is created. Methods provided by the DOM can be used to access and manipulate this tree programmatically.

## Why use DOM?

The DOM is used to access and manipulate elements in an HTML document. But why do we need to use the DOM for this? Let's understand this by use of an example. Let's suppose we have an input field and a button next to it. When the button is clicked, whatever typed in the input field should appear below the input field. How can we do this with plain HTML? We need to dynamically access the value of the input field on the button click and then display the value below in a paragraph. We will implement this example, but first, we should discuss DOM methods that will be needed for accessing and manipulating elements.

## Methods and properties of DOM

There are three basic methods of DOM for accessing elements.

- document.getElementById(): This method is used to access element by ID.
- document.getElementsByTagName(): This method is used to access element by the tag name.
- document.getElementsByClassName(): This method is used to access element by the class name.

Out of these three, getElementById() is the most commonly used method. There are a few properties that can be used with these methods:

- innerHTML: This property is used to change the inner HTML(value) of an element.
- attribute: This property is used to change the attribute value of an element.
- style.property: This property is used to change the style of an element.
- value: This property is used to access the value of the input text field.

## Adding and deleting elements

The DOM also provides methods for adding and deleting elements.

- document.createElement(): This method is used to create a new element.
- document.removeChild(): This method is used to remove an element.
- document.appendChild(): This method is used to append an element.
- document.replaceChild(): This method is used to replace an element with another element.

## Accessing and manipulating elements

Earlier, we discussed an example of displaying data typed in the input field, let's take a look at this in more detail. This is the HTML code for the input field and the button.

```javascript
<input type="text" id="input" />
<button onclick="myFunction()">
    Display
</button>
<p id = "para" > </p>
```

When the button is clicked, myFunction() will be invoked. We will access the input field using the document.getElementById() method.

```javascript
var value  = document.getElementById("input").value;
```

Here we are **using the value property to access the value of the input text field, and then we are storing it in the value variable**. Now we have the value, the next step is to display this value in the paragraph. But first, we need to access the paragraph. Again, we will use the document.getElementById() method.

```javascript
document.getElementById("para")
```

But we also need to change its value. Currently, its value is nothing. So to change its value, we will use the innerHTML property.

```javascript
document.getElementById("para").innerHTML = value;
```

Now, let's put this altogether in one file.

```javascript
<html>
    <body>
        <input type="text" id="input" />
	<button onclick="myFunction()">Display</button>
	<p id = "para" > </p>
    </body>
    <script>
    function myFunction(){
        var value  = document.getElementById("input").value;
        document.getElementById("para").innerHTML = value;
    }
    </script>
</html>
```

This is how we access and manipulate elements using DOM.

## Changing style

We can also change the style of an element using DOM. Consider the following HTML code.

```javascript
<p onclick="myFunction()" id="para"> Click on this paragraph to change its color. </p>
```

There is a paragraph. Clicking on this paragraph will invoke myFunction(). We will change the color as well as the text of this paragraph.

To change the color, we will use the style.property method.

```javascript
document.getElementById("para").style.color = "red";
```

To change the text, we will use the innerHTML property.

document.getElementById("para").innerHTML = "Color of this paragraph is red";

```javascript
document.getElementById("para").innerHTML = "Color of this paragraph is red";
```

Here, we again used the document.getElementById() method to access the element.

Let's put all of this together.

```javascript
<html>
    <body>
        <p onclick="myFunction()" id="para"> Click on this paragraph to change its color. </p>
    </body>
    <script>
        function myFunction(){
	    document.getElementById("para").style.color = "red";
	    document.getElementById("para").innerHTML = "Color of this paragraph is red";
        }
    </script>
</html>
```

Now, when the text is clicked, its color, as well as the text of the paragraph, will be changed.

## Creating an element

The DOM also provides methods to create a new element. Let's create a paragraph and adding into the body using these methods.

The first step is to create a paragraph using the createElement() method.

```javascript
document.createElement("P");
```

We need to store it into a variable.

```javascript
var newPara = document.createElement("P");
```

We have a paragraph, now we need to add some text into it. We will use the innerHTML property to add the text.

```javascript
newPara.innerHTML = "This is a paragraph"
```

Our element is ready. Let's append it to the body of the document using the appendChild() method.

```javascript
document.body.appendChild(newPara)
```

Everything is ready now. But we need something to implement all this. Let's create a button for this.

```javascript
<button onclick="myFunction()"> Click </button>
```

Let's put all this in one file.

```javascript
<html>
    <body>
	<button onclick="myFunction()"> Click to add an element </button>
    </body>
    <script>
        function myFunction(){
	    var newPara = document.createElement("P")
	    newPara.innerHTML = "This is a paragraph"
	    document.body.appendChild(newPara)
        }
    </script>
</html>
```

When the button is clicked, a new paragraph will be created and appended to the body of the document.

## querySelector()

```javascript
querySelector()
```

Until now, we discussed three ways of selecting elements. We used getElementById(), however there is another method we can use called the querySelector() method.

The querySelector() method returns only the very first matched element. Let's understand with the help of an example.

```javascript
<html>
    <body>
	<button onclick="myFunction()">Click </button>
	<p class="para"> This is the first paragraph </p>
	<p class="para"> This is the second paragraph </p>
	<p class="para"> This is the third paragraph </p>	
    </body>
    <script>
        function myFunction(){
	    document.querySelector(".para").style.color = "red"
        }
    </script>
</html>
```

The above example has a button and three paragraphs. All the paragraphs have a common class. In the script, inside myFunction(), we have used the querySelector to change the color where the class is "para". Since each paragraph has the same class, what do you think will happen here? Colors of all the paragraphs will change? No! Because we are using querySelector, the color of only the first matching paragraph will change.

This is how the querySelector() method works. But if we want to match all the elements, we can use the querySelectorAll() method.

## Wrapping it up

So this is the basic overview of DOM and how to use its methods and properties to access and manipulate elements. These were the basic as well as the most commonly used methods in DOM manipulation. When you will dive deeper, you will find many other methods and properties. DOM manipulation is one the easiest and at the same time, one the most important part of web application development.
