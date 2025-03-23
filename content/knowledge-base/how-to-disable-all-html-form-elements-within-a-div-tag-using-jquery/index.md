---
author: "icarnaghan"
title: "How to disable all html form elements within a DIV tag using JQuery"
date: 2018-03-21
---

**NOTE**: Please not that the **prop** **JQuery function** should be used instead of the **attr** function in **JQuery 1.6** and **higher**

**Answer**:

To **disable** all **input elements** within **div** use the following code: **$('#message :input').attr('disabled', true);**

To **disable** all **select elements** within **div** use the following code: **$('#message :select').attr('disabled', true);**

To **disable** all **submit buttons** within **div** use the following code: **$("#message :submit").attr("disabled", "true");**

**Explanation**:

- The **DIV** **tags** **ID** is **message**
- **attr**\- Access a property on the first matched element.
- **$("selector")**
- If disabled is set to false the element won't be disabled
