---
author: "icarnaghan"
title: "How to import a CSV file into a PostgreSQL database table"
date: 2018-04-07
---

1. Type in the following **command** in **postgres** using the command line: copy products from '/home/user/products.csv' using delimiters ','
    - **products** = _(Database Table)_
    - **'/home/user/products.csv**' = _(Location of the csv file)_
    - You need to have insert **privileges** on the **table** you need to insert the data to

How to export data to csv file from postgres database?
