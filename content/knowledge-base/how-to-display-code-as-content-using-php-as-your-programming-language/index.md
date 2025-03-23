---
author: "icarnaghan"
title: "How to display code as content using PHP as your programming language"
date: 2018-03-22
---

I have the following **JavaScript** code that I need to display as plain content on a page and when I add it the page handles it as code instead of content.

The code below I need to display as content

```
<script src="/fancybox/jquery-1.3.2.min.js" type="text/javascript" charset="utf-8"></script>
```

**Answer**:

- Use the '**htmlspecialchars**' PHP function tdisplay the code as content
    - **htmlspecialchars** - Convert special characters to HTML entities _(PHP 4 & 5)_
- See the example below
    
    ```
    htmlspecialchars('<script src="/fancybox/jquery-1.3.2.min.js" type="text/javascript" charset="utf-8"></script>');
    ```
    
- The code above will display the below as content
    
    ```
    <script src="/fancybox/jquery-1.3.2.min.js" type="text/javascript" charset="utf-8"></script>
    ```
