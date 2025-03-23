---
author: "icarnaghan"
title: "Javascript: Creating a basic popup window"
date: 2018-03-21
---

Javascript gives you the ability to open new windows in you're browser. You'll also have the ability to run any code in these windows, you could even have actions in the one window that will affect another window.

The following statement is used to open up a basic popup window

**window.open("popup.html","PopUp Window","menubar=no,width=600,height=360,toolbar=no");**

The syntax for the example above is to first specify the web page to load into the window, then the title of the window. And last we specify the options for the window.

**NOTE:** The options are all in a single set of quotes.

To use the above code. (Example).

Create a Javascript function **popUp();** in the Javascript tags defined. And place the code above in the function.

Example:

**function popUp(){**

> **window.open("popup.html","PopUp Window","menubar=no,width=600,height=360,toolbar=no");**

**}**

Now call the function by placing it into an anchor tag (**<a></a>**) or where you wish to.

Example:

**<a href="javascript:popUp();">OPEN WINDOW</a>**

To close the window place the following code in the page that is being displayed in the popup

**<a href="javascript:self.close()">CLOSE WINDOW</a>**

**Options for JavaScript Popups**

| **Option** | **Values** | **Description** | **Version** |
| --- | --- | --- | --- |
| location | yes\|no | Does the location bar show? | ver 1.0 |
| menubar | yes\|no | Does the menubar show? | ver 1.0 |
| scrollbars | yes\|no | Do scrollbars show? | ver 1.0 |
| status | yes\|no | Does the status bar show\| | ver 1.0 |
| titlebar | yes\|no | Does the titlebar show? | ver 1.0 |
| toolbar | yes\|no | Does the toolbar show? | ver 1.0 |
| resizable | yes\|no | Can you resize the window? | ver 1.0 |
| height | pixels | height of window | ver 1.0 |
| width | pixels | width of window | ver 1.0 |
| directories | yes\|no | Does the personal toolbar show? | ver 1.2 |
| innerHeight | pixels | specifies the inner height of window | ver 1.2 |
| innerWidth | pixels | specifies the inner width of window | ver 1.2 |
| screenX | pixels | specifies distance from left edge of screen | ver 1.2 |
| screenY | pixels | specifies distance from top edge of screen | ver 1.2 |
