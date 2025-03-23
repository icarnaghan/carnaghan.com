---
author: "icarnaghan"
title: "JHTMLform not supported. Invalid Token"
date: 2018-04-06
---

After you upgraded from **Joomla! 1.5.0** to **1.5.2**/**1.5.3** you receive the error message **JHTMLform not supported. Invalid Token.** when trying to login to the **backend**. Or when trying to fill in a **form** or **login** on **Front End** you get **Invalid Token or** **JHTMLform not supported. Invalid Token.**

Follow the steps below in order to solve this problem

**STEP 1**

Locate the following path in your **Joomla! installation** in the **root** directory **/libraries/joomla/html/html/**and check if the file **form.php** is present.

**STEP 2**

If the file is missing create the file **form.php** in the **/libraries/joomla/html/html/**directory and add the code below in the **form.php** file.

CODE

<?php

> /\*\* \* @version $Id: form.php 9944 2008-01-14 21:10:22Z eddieajau $ \* @package Joomla.Framework \* @subpackage HTML \* @copyright Copyright (C) 2005 - 2008 Open Source Matters. All rights reserved. \* @license GNU/GPL, see LICENSE.php \* Joomla! is free software. This version may have been modified pursuant \* to the GNU General Public License, and as distributed it includes or \* is derivative of works licensed under the GNU General Public License or \* other free or open source software licenses. \* See COPYRIGHT.php for copyright notices and details. \*/
> 
> /\*\* \* Utility class for form elements \* \* @static \* @package Joomla.Framework \* @subpackage HTML \* @version 1.5 \*/ class JHTMLForm { /\*\* \* Displays a hidden token field to reduce the risk of CSRF exploits \* \* Use in conjuction with JRequest::checkToken \* \* @static \* @return void \* @since 1.5 \*/ function token() { return '<input type="hidden" name="'.JUtility::getToken().'" value="1" />'; }

}

?>

**STEP 3**

Save the file and refresh your **Joomla!** page and the problem should now be solved.
