---
author: "icarnaghan"
title: "Disabling the Layout and the View in cakePHP"
date: 2018-03-22
---

To **disable** the **view** and the **layout** in **cakePHP** set **autoRender** to **false** within the appropriate **action** in your **controller**

```
$this->autoRender = false;
```

To only **disable** the **layout** in **cakePHP** set the **layout** to **false**

```
$this->layout = false;
```

And to only **disable** the **view** for an **action** call the **render** **method** and set the **parameter** to **false**

```
$this->render(false);
```
