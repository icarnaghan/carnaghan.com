---
author: "icarnaghan"
title: "What's the difference between RIGHT, LEFT, OUTER, INNER, JOIN"
date: 2018-03-23
---

The difference is the way the tables are joined if no common records are available.

_**RIGHT**_ - **RIGHT JOIN** is the opposite of **LEFT JOIN** and the same as **RIGHT OUTER JOIN**. Shows all **records** from the right table and only matching **records** from the left table.

_**LEFT**_ - **LEFT JOIN** shows all **records** from the left table does not matter if matching **records** in the right table exists or not. Also the same as **LEFT OUTER JOIN**.

_**JOIN**_ - **JOIN** is the same as **INNER JOIN**. **JOIN** means to only show **records** common to both tables. Will only show **records** if the same ID value exists in all tables used. If we have a product's table and a categories table, both have columns with name product\_id. If the product\_id in the product's table does not match the product\_id in the categories table. No results will show.
