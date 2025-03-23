---
author: "icarnaghan"
title: "How to copy a columns data from one table into a column in another table using PostGreSQL"
date: 2018-04-07
---

How to copy a **columns** **data** from one **table** into a **column** in another **table** using P**ostgreSQL**? Eg. **name** **columns** data from the **users** **table** into **name****column** in the **new\_users table**.

Execute the **query** below with different **column** names and **table** names and all the **data** for a specific **column** will be copied over to the selected **column** in another **table**.

**INSERT INTO n\_owners(owner\_name) SELECT owner\_name FROM owners;**
