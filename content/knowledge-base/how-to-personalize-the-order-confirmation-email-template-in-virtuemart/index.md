---
author: "icarnaghan"
title: "How to personalize the Order Confirmation Email Template in Virtuemart"
date: 2018-04-06
---

The Order Confirmation Email template defines the layout of the email being sent to the user after he/she placed an order. Sometimes you may want to personalize this email being sent out to fit your needs.

**STEP 1**

Locate the email template in the following directory **administrator/components/com\_virtuemart/html/templates/order\_emails/email\_english.html.**

Remember the language at the end of the file **email\_your\_language.html** , the filename with the default language of your **Virtuemart** Installation is usually the file that needs to be edited.

In this file you will be able to edit the layout of the email template

**STEP 2**

The email template is populated with content from the **administrator/components/com\_virtuemart/classes/ps\_checkout.php file** using the method **function email\_receipt().** The **email\_receipt()** function defines placeholders in the template and the values of them are being assigned by using the function **str\_replace**.

**STEP 3**

To modify the image on the email confirmation, log into the back end of your Joomla! website. And edit the **Virtuemart Store**. Under the **Store** section upload the image you need and this will be the image you see in the confirmation email
