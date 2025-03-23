---
author: "icarnaghan"
title: "DHTML menu appears behind form field selector dropdowns in Internet Explorer 6"
date: 2018-04-06
---

When the **menu** loads, it is loading behind the **html** **form****selectors** (select boxes).

Unfortunately there isn't a fixed solution to this since **select boxes** have an infinite **Z-Index** in **Internet Explorer 6**.

**Possible Solutions**:

1. Try putting the **select bo**x in an **iframe** for **Internet Explorer 6**. And the main page will be in front of the **Iframe**.
    - **Note**: **Opera 8** has the same problem with **iframes** as **Internet Explorer 6**has with **selects**.
2. Try to **hide** the **select box** with **Javascript** everytime the **Menu** **hovers** over the **select box**.
3. Simplest fix is that the **menu** never overlaps the **select box**.
