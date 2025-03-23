---
author: "icarnaghan"
title: "How to add a favicon to your Joomla! 1.5 site"
date: 2018-04-06
---

**What is a favicon?** A **favicon** is a **small 16px X 16px square image** with the **.ico**extension that appears on the left side of the **URL** in the **addressbar** and on the **browsers tabs**.

**Answer**:

Follow these steps in order to successfully create a **favicon** for you're **Joomla! site**.

**STEP 1**

Create a **square pixel image** with **height 16px** and **width 16px** using a **graphic tool** like **Gimp** or **Photoshop**. Save the image.

**STEP 2**

Now **convert** the image type to **.ico** using **free online tools** like http://www.favicongenerator.com/ or http://tools.dynamicdrive.com/favicon/

**STEP  4**

After the **conversion** of the **image** **type**, you need to **upload** the converted **favicon** to your **Joomla! templates directory**.

Connect via **FTP** to your **Joomla! installation files** and locate the following **directory**:

**ROOT->templates->YOUR\_TEMPLATE**

**Copy** **favicon.ico** to the **directory**.

**STEP 5**

Open your **webpage**

**Hard refresh** your **webpage** by pressing the following key combinations. **CTRL+SHIFT+R** or **CTRL+F5**

**STEP 6**

Now your **favicon** should appear on the **browser tabs** and left next to the **URL** on the **addressbar.** If not you may need to clear your **Internet History** and **Cache** files of your **browser**.

**NOTE**: Some **templates** contain code that directs the browser to a **different directory**to find the **favicon**, in order to determine where the **favicon** is being fetched from open the **index.php** file of your template (**ROOT->templates->YOUR\_TEMPLATE** ) and locate the following code: <link rel="shortcut icon" href="http://www.yoursite.co.za/templates/yourtemplate/favicon.ico" /> and in the **href****attribute** you'll find the **directory** where the **favicon** is displayed from.
