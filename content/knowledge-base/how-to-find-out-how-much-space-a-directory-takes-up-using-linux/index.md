---
author: "icarnaghan"
title: "How to find out how much space a directory takes up using Linux"
date: 2018-04-07
---

In the command line type the following command within the desired directory

{codecitation class="brush: bash;"}du -c{/codecitation} This will give you the usage/size of all the folders within that particular directory. 

**du =  _estimate file space usage_ -c = _total_**

To get the size/usage in a Human readable format eg. **Megabytes/Gigabites** append the **-h** option to the command above.

Example below:

{codecitation class="brush: bash;"}du -ch{/codecitation}
