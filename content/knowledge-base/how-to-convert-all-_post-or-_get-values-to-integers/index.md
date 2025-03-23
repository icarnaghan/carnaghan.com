---
author: "icarnaghan"
title: "How to convert all $_POST or $_GET values to Integers"
date: 2018-03-22
---

By using the built-in PHP functions  **array\_map** and **intval**.

- array\_map = _Applies the callback to the elements of the given arrays, this applies the function for each value of an array_ (PHP 4 >= 4.0.6, PHP 5)
- intval = _Get the integer value of a variable_ (PHP 4, PHP 5)

**Examples**:

{codecitation style="brush: PHP;"} $post\_int = array\_map('intval', $\_POST); //Converting every post value to integer $get\_int = array\_map('intval', $\_GET); //Converting every get value to integer {/codecitation}
