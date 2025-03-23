---
author: "icarnaghan"
title: "How to solve error: 'PHP Warning: DOMDocument::createElement(): unterminated entity reference' when creating a new element using the DOMDocument object model"
date: 2018-03-22
---

**DOMDocument** \= _Represents an entire HTML or XML document; serves as the root of the document tree_.  (PHP 5) **DOMDocument::createElement()**  \= _Create new element node_. (PHP 5)

Now to the solution!

**Solution**:

- Use the **htmlentitites** function to convert all applicable characters to HTML entities.
- **$****dom-****\>createElement**('value', **htmlentities**($text\_value));
    - **htmlentitites** \= _Convert all applicable characters to HTML entities_ (PHP 4, PHP 5)

Problem should be solved!
