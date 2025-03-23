---
author: "icarnaghan"
title: "How to get the number of Words, Characters and Rows within a text file on Linux via the Command Line"
date: 2018-04-07
---

- By using the wc command. _wc = print newline, word, and byte counts for each file_ 
- In the CLI type in the following command:
    
    ```
    wc -wcl < /home/user/textfile.txt
    ```
    
    _textfile.txt = The file that we need to get the information from -w = print the word count -c = print the character count -l = print the line count_
