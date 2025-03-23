---
author: "icarnaghan"
title: "PDF button opening HTML page in popup when AceSEF has been enabled"
date: 2018-03-25
---

When I installed the **AceSEF** component, and **enabled** it all of a sudden the **PDF links**did not work anymore, it opens a **new window** but instead of displaying the **PDF version** it displays the **HTML version** of the **page**, when I **disabled** the **AceSEF component** it works again.

Luckily I managed to solve this problem. Please see the Answer

Open the **AceSEF configuration page** and click on the **URLs** tab.

Under the **Global Variables** section in the **non-SEF variables** section, add the following **format=pdf**, clear the cache refresh the page and the PDF link will work again.

![non-SEF variables, format=pdf](images/aceSEF.png "non-SEF variables, format=pdf")
