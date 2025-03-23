---
author: "icarnaghan"
title: "How to use the Custom, stockable variants plugin in VirtueMart 2.0"
date: 2018-03-25
---

This is a basic tutorial to help you get started. We will use a Basic Size and Colour selection per product, say if you had a clothing store you would want users to select a Size and Colour for a clothing item, with a different price and different stock levels, you would use the **Custom, stockable variants plugin** for **VirtueMart 2.0**

**Steps**

1. Open the **Administration Panel** for **VirtueMart 2.0**
2. On the Left hand side under **Products** select **Custom Fields****
    
    ![Custom Fields](images/vm2-step1.png "Custom Fields")
    
    **
3. Click on **New** to create a new **Custom Field****,** and fill in the following values
    - **Custom Field Type**: Select Plug-ins
    - **Title**: Size & Colour
    - **Published**: Yes
    - **Parent**: No, you can set this later if you know what you doing
    - **Cart Attribute**: Yes
    - **Description**: The size & colour of the item
    - **Default**: Leave blank for now
    - **Tooltip**: Please select size and colour
    - **Layout position**: Leave blank for now
    - **Admin onl**y: No
    - **Is a list?**: No
    - **Hidden**: No
    - **Select a plug-in**: VM - Custom, stockable variants
4. You will notice you have 4 different options to make use of, Option 1 we would like to list all the different Sizes and Option two we will add in all the different colours together with Sizes that we need.
    
    The first option name we will name **Size** and **in Option Values** we add all the different **Sizes** underneath each other. The second option will be **Colour** and in the **Option Values** we add in all the different **Colours** for a item.**
    
    ![VM - Custom, stockable variants](images/vm2-step2.png "VM - Custom, stockable variants")
    
    **
5. Click on **Save**
6. Now it's time to add it to a product
7. Once saved, on the left menu under **Products** select **Products** and then select a **product** were you would like to apply **Sizes and Colours** to
8. Once the **product** is open click on the **Custom Fields** tab
    
    ![Custom Fields tab](images/vm2-step3.png "Custom Fields tab")
9. No under **Custom Field Type** select **Size and Colour**
    
    ![Custom Field Type](images/vm2-step4.png "Custom Field Type")
10. Now you will notice a New box appears under **Plug-ins**. this box will allow you to add new **CHILD PRODUCTS** to the **MAIN PRODUCT**, each **child product** will act as a **Variant for Size and Colour** for the **Main Product**, this will allow you to add **additional pricing**, **stock**, **SKU** and **Product Name** to a specific **Size and Colour**. All products added here will be shown under **Products** as **Child Products**
11. Every time you want to add a new **Child Product** '_**Size and Colour**_' you will need to fill in the 4 fields and click on the **New** button. This will add a new **Child Product** above the **New Product** label, where you can select the **size** and **colour. To edit the child product you will need to search for it under the product list where all the products are listed.
    
    ![Plug-ins Size & Colour ](images/vm2-step5.png "Plug-ins Size & Colour ")**
12. **Click on** Save or **Save** **& Clos**e to save the **Variants** for the product
13. After all has been **Saved** open the front end and you will notice the different sizes and colors will appear. ![Front End](images/vm2-step6.png "Front End")
