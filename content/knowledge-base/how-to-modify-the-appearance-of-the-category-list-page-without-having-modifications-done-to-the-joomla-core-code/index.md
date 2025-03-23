---
author: "icarnaghan"
title: "How to modify the appearance of the Category List page without having modifications done to the Joomla! Core Code"
date: 2018-04-06
---

Since **Joomla! 1.5** this feature has been made available.

**Answer**:

**STEP 1**

Via **FTP** copy the following file (**default\_items.php** ) from your **Joomla! 1.5 installation files** to your local machine.

Path to **default\_items.php**  **ROOT\_PATH/components/com\_content/views/category/tmpl/default\_items.php**

**NOTE**: For **FTP** use your favorite **FTP** client eg. **FileZilla**

**STEP 2**

Open the file and edit it as you want the **Category List page** to look!

I wanted to **remove** the **numbering** and **replace** the **numbers** with **Bullets**. I **opened**the file and replaced **line 70** **<?php echo $this->pagination->getRowOffset( $item->count ); ?>** with **<?php echo '& bull;'; ?>**  _**NB: no space between & and bull**_

**STEP 3**

**Save** the **file**

**STEP 4**

Again **access** your **Joomla! site** via **FTP** and locate your **template directory** and open it.

eg. **ROOT\_PATH/templates/YOUR\_TEMPLATE/**

**STEP 5**

Create an "**html**" **folder** within your **template directory** and within your **html** **folder**another **folder** with name "**com\_content**" and within **com\_content** another **folder**with name "**category**"

Now your folder structure should look like this: **ROOT\_PATH/templates/YOUR\_TEMPLATE/html/com\_content/category**

**STEP 6**

**Copy** your **edited** **default\_items.php** **file** to **ROOT\_PATH/templates/YOUR\_TEMPLATE/html/com\_content/category**

**STEP 7**

Open your **web page** and your **customized** changes will **show**.

**NOTE**:

- Only Joomla! 1.5 supports this feature.
- If you select another template the default Joomla! core pages will show
- For more information on this feature visit: http://docs.joomla.org/Tutorial\_talk:Template\_overrides
