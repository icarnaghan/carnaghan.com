---
author: "icarnaghan"
title: "How to search and replace text within a text file using the Command Line on Linux"
date: 2018-04-07
---

This can be accomplished by using the **sed** command.

_**sed** =  stream editor for filtering and transforming text_

 

For this example we will have a file called **test.txt** that contains the following text _"This is a test file with some test information, containing some test data."_

We want to replace all instances of **test** in the file with **cool** and save the output to a new file called **cool.txt**

To accomplish this open a new **command line window** and type and execute the following command:

```
sed -e 's/test/cool/g' test.txt > cool.txt
```

_**\-e** =  add the script to the commands to be executed **s** = s/regexp/replacement/ Attempt  to match regexp against the pattern space.  If success‐ ful,  replace  that  portion  matched  with  replacement.    The replacement may contain the special character & to refer to that portion of the pattern space  which  matched,  and  the  special escapes  \\1  through  \\9  to refer to the corresponding matching sub-expressions in the regexp._ _**g** = Copy/append hold space to pattern space._

 

If you view **cool.txt** by using the **cat** command

```
cat cool.txt
```

you'll see the following output

```
This is a cool file with some cool information, containing some cool data.
```

To learn more about the set command type in **man sed** in the command line

```
man sed
```
