---
author: "icarnaghan"
title: "Creating a Super Simple JavaScript Validated Form"
date: 2020-06-24
categories: 
  - "coding"
---

There are times when you need to create a basic HTML form that provides validation to end users. Without leveraging a framework or additional libraries, this can be easily achieved by using JavaScript directly. This article walks through the basic steps of creating a simple validated form using basic selectors and error handling. Our requirements are:

1. For successful submission, all fields must be entered correctly within our validation rules
2. If one or more error occurs, the form will not submit. Feedback provided to the user
3. A correct form with no errors once submitted, will send an email to the recipient

> In real life we would most likely have a call to a web service or some other piece of code that would execute once a form was submitted with no errors.

To get started, you will need to create a directory structure on your local computer that resembles the following:

- index.html (our main form)
- js/script.js (the JavaScript needed to validate our form inputs)
- css/style.css (our form styling)

Next, grab the html below to render the basic form we will be building in this exercise and copy this into a new file called index.html.

```markup
<!DOCTYPE html>
<html>

<head>
    <title>HTML5 Form</title>
    <link rel="stylesheet" href="css/style.css" />
</head>

<body>
    <div class="container">
        <h1>Basic Membership Form Example</h1>
        <form name="registration" action="mailto:testemail@testemail.local" onsubmit="return validateForm()"
            method="post" autocomplete="off">
            <div class="form-row wrap">
                <label for="firstname">First Name:*</label>
                <input type="text" class="alpha" id="firstname" placeholder="Enter first name" />
                <div class="invalid-feedback">Please enter a valid first name</div>
            </div>
            <div class="form-row">
                <label for="lastname">Last Name:*</label>
                <input type="text" class="alpha" id="lastname" placeholder="Enter last name" />
                <div class="invalid-feedback">Please enter a valid last name</div>
            </div>
            <div class="form-row">
                <label for="email">Email:*</label>
                <input type="text" id="email" placeholder="Enter email" />
                <div class="invalid-feedback">Please enter a valid email address</div>
            </div>
            <div class="form-row">
                <label for="confirmemail">Confirm Email:*</label>
                <input type="text" id="confirmemail" placeholder="Confirm email" />
                <div class="invalid-feedback">Email address doesn't match</div>
            </div>
            <fieldset class="form-row">
                <legend class="col-form-label">Membership Type:*</legend>
                <div id="membership" class="controls">
                    <div class="form-row">
                        <div class="col">
                            <div>
                                <input type="checkbox" id="membershipfree" value="online" />
                                <label class="form-check-label" for="membershiponline">Online</label>
                            </div>
                            <div>
                                <input type="checkbox" id="membershipbasic" value="paper" />
                                <label class="form-check-label" for="membershippaper">Paper / Mail</label>
                                <div class="invalid-feedback">
                                    Please select at least one membership option
                                </div>
                            </div>
                        </div>
                        <div class="col">
                            <div>
                                <input type="checkbox" id="membershippremium" value="premium" />
                                <label class="form-check-label" for="membershippremium">Premium Membership</label>
                            </div>
                        </div>
                    </div>
                </div>
            </fieldset>
            <div class="form-row">
                <button type="submit" class="btn btn-primary" name="submit" id="submitform" value="Submit">
                    Submit
                </button>
            </div>
        </form>
    </div>
    <script src="js/script.js"></script>
</body>

</html>
```

The HTML references our CSS / styles in the header and the JavaScript is referenced before the closing body tag at the bottom of the document. You will notice for every form element, I am using form-row classes, which are needed for styling as well as a class called **invalid-feedback**. We'll be using this class to supply feedback to the end user if information has been entered incorrectly into the form. The idea behind this is to hide all of these **invalid-feedback** class elements on page load, and only make them visible if and when an error is registered in our JavaScript, which we will be getting to shortly.

Another thing to note here is that within the form tag, I am calling a function called validateForm(). This function will return a boolean (true or false value) based on the state of the form once a user submits. If a false is returned, the form will not submit, otherwise if the form is filled out correctly, the form action 'mailto' will execute.

Next we will style the form using Flexbox, which provides a nice way for us to control the layout of our form. For more information on Flexbox, be sure to visit CSS Tricks and review their Complete Guide to Flexbox article.

Copy the following code into a new file: css/style.css.

```css
/* Main Form Container */
.container {
  font-family: Arial, Helvetica, sans-serif;
  max-width: 800px;
  margin: 2em auto;
  background-color: #f5f5f5;
  padding: 1rem;
  border-radius: 1rem;
  border: solid #ccc 1px;
}

/* Error Handling */
.invalid-feedback {
  display: none;
  margin-top: 0.25rem;
  font-size: 80%;
  color: #dc3545;
  flex: 100%;
}
.is-invalid ~ .invalid-feedback {
  display: block;
}
.is-invalid,
.is-invalid ~ .form-check-label {
  border-color: #dc3545;
  color: #dc3545;
}

/* Layout with Flexbox */
.form-row {
  display: flex;
  justify-content: flex-end;
  padding: 0.5em;
  flex-wrap: wrap;
}
label {
  flex: 1;
  padding: 1em 0em;
}
input,
select,
textarea {
  flex: 3;
  padding: 1em;
}

#area,
.col {
  flex-grow: 1;
}

/* Form Controls */
input {
  margin: 0.5em;
  border-radius: 4px;
  border: 1px solid #bbb;
}
select {
  font-size: 1em;
}
fieldset {
  border: 1px solid #bbbbbb;
  margin-bottom: 10px;
}
legend {
  padding: 0.8em;
  border: 1px solid #bbbbbb;
  font-size: 90%;
}
button {
  background: #808080;
  color: #ffffff;
  padding: 1em;
  font-size: 1em;
}
```

The CSS contains a number of styles for the overall form container, error handling, and form layout using flexbox. Note the error handling code where I am setting invalid feedback to display:none, so that the error divs will not show on initial page load.

## Writing the JavaScript

To get us started, we need to define a number of variables that we will be using for our validation function. These include variables for error handling, form fields, and regular expressions. Our error handler is going to be a simple integer which will be initialized to zero once the validation function executes and updated if any errors are found. The form elements are going to be set using document.querySelector. For more on document.querySelector and a general overview of the DOM, see JavaScript Manipulating the Document Object Model (DOM). Finally, we're going to want to use regular expressions to determine if our input is correct. In this basic example we are going to use two kinds of regular expressions to evaluate alpha text and email validation. If you are unfamiliar with regular expressions, take a look at my other article, Regular Expressions in JavaScript. I use https://regexr.com/ for experimenting with different regular expressions, and I encourage you to check it out as it is very helpful for testing your regex values. Let's start putting this together. Copy the code below and place it into a new js/script.js file.

```javascript
// Error handler
let errors;

// Form Elements
let firstname = document.querySelector("#firstname");
let lastname = document.querySelector("#lastname");
let email = document.querySelector("#email");
let confirmemail = document.querySelector("#confirmemail");
let membership = document.querySelectorAll('input[type="checkbox"]');

// Regular Expressions
let alpha = /^[a-z]+$/i;
let emailValidation = /^[a-z0-9._%+-]{1,64}@[a-z0-9.-]{1,252}\.[a-z]{2,3}$/i;
```

In the code above we are setting variables for our errors (handler), our fields using document.querySelector to target the associated elements from the DOM, and our two regular expressions. Under Form Elements, you will see standard use of document.querySelector for firstname, lastname, email, and confirmemail. These will set our variables to these HTML elements, which we will then be able to use to determine their inputted values. We are using querySelectorAll to store all checkboxes in an array, which we can then evaluate to determine if the minimum required number have been selected in the form. Note under Regular Expressions, alpha will be reused on the firstname and lastname fields. In real world situations, you would most likely use other regular expressions to evaluate other types of data including numerical, etc.

Our last step is to write the validation function, which will both evaluate every field to determine if an error occurred, and it will also update the error (handler) variable, which will prevent the form from being submitted if one or more validation errors have occurred. Copy the code below and place it under the previous code from above in your script.js file.

```javascript
// Validation Function
function validateForm() {
  errors = 0;
  let membershipchecked = document.querySelectorAll(
    'input[type="checkbox"]:checked'
  );

  // Textboxes
  alpha.test(firstname.value) ? valid(firstname) : invalid(firstname);
  alpha.test(lastname.value) ? valid(lastname) : invalid(lastname);
  emailValidation.test(email.value) ? valid(email) : invalid(email);
  confirmemail.value == email.value
    ? valid(confirmemail)
    : invalid(confirmemail);

  // Radio and Checkboxes
  membershipchecked.length < 1
    ? membership.forEach(element => invalid(element))
    : membership.forEach(element => valid(element));

  // Validation Helpers
  function invalid(element) {
    element.classList.add("is-invalid");
    errors++;
  }
  function valid(element) {
    element.classList.remove("is-invalid");
  }

  return errors > 0 ? false : true;
}
```

You will see in this function I have defined two validation helpers, which get passed an element and will add or remove a class called 'is-invalid'. If an element gets sent to invalid, is-invalid class will be added to that element. If an element is sent to valid, the function will check to see if is-invalid exists, and if it does it will remove it. Finally, if an element is invalid, the errors variable will be incremented, meaning the form will not be submitted. **Remember once the user fixes any errors and clicks submit, the validateForm function will run again resetting errors to zero before re-running the validation checks.**

Let's take a look back at our earlier CSS (Lines 12 - 27)

```css
/* Error Handling */
.invalid-feedback {
  display: none;
  margin-top: 0.25rem;
  font-size: 80%;
  color: #dc3545;
  flex: 100%;
}
.is-invalid ~ .invalid-feedback {
  display: block;
}
.is-invalid,
.is-invalid ~ .form-check-label {
  border-color: #dc3545;
  color: #dc3545;
}
```

Notice the sibling combiner next to the is-invalid class. This will enable us to set the invalid-feedback class (which contains the error messages) to either block (to display) or none (to hide). Going back to our validateForm function, we initialize the errors variable with zero each time this function is called. In addition to this we also create a second checkbox array, only this time we are setting a variable called membershipchecked to contain only those selected checkboxes. Next we're going to run our validation tests against firstname and lastname form elements by using our alpha regular expression to test or evaluate the value entered. If the value is not alphabetic, the invalid function is called passing the form element. Likewise if the value is alphabetic, the valid function is called, again passing the form element passed. We use a ternary operator in both of these tests.

Next our email validation test is executed and we compare the values of both email fields. Again, we call the invalid or valid function depending on the result. Finally we evaluate our checkboxes for membership. If we have less then 1 checkbox selected, we want to apply the is-invalid class to each box. This is done by using a forEach statement. In the code above we are using an arrow function to simply reduce the code. For more information on arrow functions, take a look at JavaScript Arrow Functions: How They Work.

That's it. This is a very basic form, however the code demonstrates how quickly you can write some JavaScript code coupled with regular expressions and a little CSS to produce a responsive form with error handling and user feedback. I have also uploaded a completed version of this sample form to CodeSandbox at https://codesandbox.io/s/basic-validation-0x92n.
