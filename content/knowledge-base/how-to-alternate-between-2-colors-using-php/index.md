---
author: "icarnaghan"
title: "How to alternate between 2 colors using PHP"
date: 2018-03-22
---

This could come in handy if you have a table with multiple rows and if you wish to alternate between 2 colors.

We'll need to use the **Modulus Arithmetic Operator** for this **(%)**. **Modulus (%)** gets the remainder after a division has been made between 2 numbers. _**eg. 3%2 = 1**_

**Code Example**:

```
<table border="0" cellpadding="2" cellspacing="4">
<?php
   $rows = 10; //Number of rows
    for($i=0;$i<$rows;$i++){ //Looping through rows
        $a = $i % 2; //Modulus Calculation
        
        if($a == 1){ //If remainder is one we select grey as the color
            $color = "#3e3e3e";
        }else{ //If there's no remainder the color will be white
            $color = "#ffffff"; 
        }
        ?>
        <tr style="background-color:<?=$color?>"> //Applying the relevant color
            <td>Color 1</td>
        </tr>
        <?php
    }
?>
</table>
```
