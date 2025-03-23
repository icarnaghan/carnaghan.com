---
author: "icarnaghan"
title: "How to set a timer in JavasScript"
date: 2018-03-21
---

If we want to call a function every 10 seconds using JavaScript we can accomplish it by implementing the following piece of code

```
window.setInterval('yourfunction()', 1000);
 
function yourfunction(){
alert('test');
 
}
```

With the code above every 10 seconds a JavaScript function with the name yourfunction will be called that will prompt an alert.

**window.setInterval** = Evaluates an expression each time a certain number of seconds have elapsed
