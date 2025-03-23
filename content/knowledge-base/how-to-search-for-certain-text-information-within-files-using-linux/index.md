---
author: "icarnaghan"
title: "How to search for certain text/information within files using Linux"
date: 2018-04-07
---

**Example**: If you have a **directory** with 10 000 text files in it and you need to find a certain **word** in a certain **file** but you aren't sure what the name of the file is. You can use the method described below to find the **file** with selected **text** within it.

**Answer**:

In the **command line** type the following command: _**grep -rni "Hello World" \*.txt**_ and press enter to **execute** the **command**. What this **command** does it **searches** within all the **txt (text) files** to find the **sentence** "_**Hello World**_" and list the results.

**Parameter Explanation**:

**\-r** : (_\--recursive_) Read all  files  under  each  **directory**  **recursively**. **\-n** : (_\--line-number_)  Prefix  each  line of output with the 1-based line number within its input file. **\-i** : (_\--ignore-case_) Ignore  case  distinctions  in  both  the  PATTERN and the input files.
