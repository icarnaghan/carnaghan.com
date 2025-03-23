---
author: "icarnaghan"
title: "How to convert all text to uppercase using CSS"
date: 2018-03-22
---

If you have text within a **div** tag that you want to convert to **Uppercase** you can achieve this using the **CSS _text-transform_** property that was introduced in **CSS1**

E.g.

You want to convert 

```
<div>
Lorem Ipsum is simply dummy text of the printing and typesetting industry.
</div>
```

to  

```
<div>
LOREM IPSUM IS SIMPLY DUMMY TEXT OF THE PRINTING AND TYPESETTING INDUSTRY.
</div>
```

to do this we assign the **text-transform: uppercase;**  css property to the **div** tag's styling 

```
div {
     text-transform: uppercase;
}
```
