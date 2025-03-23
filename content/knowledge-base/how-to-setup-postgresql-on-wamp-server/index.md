---
author: "icarnaghan"
title: "How to setup PostgreSQL on WAMP server"
date: 2018-03-22
---

1. Ensure that **PostgreSQL** has been **installed** on your **machine**. The **Windows installers** can be **downloaded** from http://www.postgresql.org/download/windows/
2. Assuming **WAMP Server** is installed on **c:\\wamp**, copy **_C:\\wamp\\bin\\php\\php5.4.3\\libpq.dll_** to **_C:\\wamp\\bin\\apache\\apache2.4.2\\bin\\libpq.dll_**
3. Also see that the following files exist
    - **_C:\\wamp\\bin\\php\\php5.4.3\\ext\\php\_pgsql.dll_**
    - **_C:\\wamp\\bin\\php\\php5.4.3\\ext\\php\_pdo\_pgsql.dll_**
4. The above two files are **PHP extensions** and should be enabled using the **WAMP menu** or the **php.ini** file
