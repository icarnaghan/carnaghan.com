---
author: "icarnaghan"
title: "How to export data to a CSV file from a PostgreSQL database"
date: 2018-04-07
---

1. Type in the following **command** in **postgres** using the command line: copy products to '/home/user/products.csv' delimiters ','
    - **products** = _(Database Table)_
    - **'/home/user/products.csv**' = _(Location where to save the csv file)_
    - You need to have **write permissions** to **write** the file to the **filesystem** with the **postgres** **user**

How to import a CSV file into a postgresql?
