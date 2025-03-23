---
author: "icarnaghan"
title: "How to set the Page Title in Yii Framework 1.1.x"
date: 2018-03-22
---

In your **main layout file** always have the following code between the **title tag** in order to **display** the **title**

```
<title><?php echo CHtml::encode($this->pageTitle); ?></title>
```

Please note that conditional statements can also be use within the title tag to make displaying of the title more dynamic.

You can set the **title** in your **Controller** or **View files** by using something similar like

```
$this->pageTitle = 'My new page title';
```

**NOTES**:

- In the **controller** if the **Page Title** is not set **Yii** **defaults** the **Page Title** to the **Controller** and **Action** **name**
- The easiest way to set the **Page Title** is by setting it within your **view** files '_Everybody has there own choice of preference_'
- The **Page Title** won't display if not **echoed** between the **title tag** eg.
    
    ![View source](images/vista_plana.png "View source")
    
    ```
    <title><?php echo CHtml::encode($this->pageTitle); ?></title>
    ```
