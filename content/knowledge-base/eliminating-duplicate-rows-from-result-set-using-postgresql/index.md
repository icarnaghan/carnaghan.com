---
author: "icarnaghan"
title: "Eliminating duplicate rows from result-set using PostgreSQL"
date: 2018-04-07
---

- Use the **DISTINCT ON** keyword in your **query**
- To do a **case-insensitive search** do the following query **SELECT DISTINCT ON**(**upper**(surname)) surname **FROM** employees **ORDER BY** **upper**(surname)
- This will return **non-duplicate** surnames.
