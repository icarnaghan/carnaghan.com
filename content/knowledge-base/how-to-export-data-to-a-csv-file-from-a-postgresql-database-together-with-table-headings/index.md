---
author: "icarnaghan"
title: "How to export data to a CSV file from a PostgreSQL database together with table headings"
date: 2018-04-07
---

1. Type in the following **command** in **postgres** using the command line: copy products to '/home/user/products.csv' delimiters ',' CSV HEADER
    - **products** = _(Database Table)_
    - **'/home/user/products.csv**' = _(Location where to save the csv file)_
    - You need to have **write permissions** to **write** the file to the **filesystem** with the **postgres** **user**
    - **CSV HEADER** \- This is the feature that let's you export the table headings as well, please note that the **HEADER** argument has only been introduced in Postgres 8.1

How to import a CSV file into a postgresql?
