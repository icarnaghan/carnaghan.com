---
author: "icarnaghan"
title: "How to iterate through an array in a Bash Shell Script"
date: 2018-04-07
---

- Create a new **Bash Shell Script** _eg. loopThroughArray.sh_
- Open the **Script** with an **Editor** eg. **GEdit**
- Add the **array definition** through which the **script** should **iterate**
    
    ```
    array=( one two three four five )
    ```
    
- The **expression** _**${array\[@\]}**_ contains all **values** within the **array**
    
    ```
    ${array[@]}
    ```
    
- Now we create a **for** loop to **iterate** through the **array**
    
    ```
     
    for num in ${array[@]}
     
    do
     
    echo $num
     
    done
     
    
    ```
    
- Once the **Script** **executes**, all values within the **array** be be **echoed** to the **screen**.
    
    To **extend** the **Script additional statements** can be added to the **body** of the **for loop**
