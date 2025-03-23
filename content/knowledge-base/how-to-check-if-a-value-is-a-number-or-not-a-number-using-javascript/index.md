---
author: "icarnaghan"
title: "How to check if a value is a number or not a number using JavaScript"
date: 2018-03-21
---

By using the **isNaN()** **JavaScript** function. **isNaN** = _Is Not A Number_

**Examples**:

document.write(**isNaN**("Hello World!")); _//Will print true since Hello World! is not a number_ document.write(**isNaN**(123456)); _//Will print false, since 123456 is a number._

**var** phoneNumber = 0724956785234; if(**isNaN**(phoneNumber) == **true**){ **alert**("Please enter a valid phone number"); return false; }
