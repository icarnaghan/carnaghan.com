---
author: "icarnaghan"
title: "How to redirect using the Joomla! 1.5 and 2.5 API"
date: 2018-03-25
---

When developing a **Joomla! Component** or **Module** you can use the **Joomla! API** to redirect the user from one page to another

**Joomla! 1.5 Example**

```
global $mainframe;
$link = 'http://yourlink';
$msg = 'message'
$mainframe->redirect($link, $msg, $msgType='message');
```

**Joomla! 2.5 Example**

```
$app = JFactory::getApplication();
$link = 'http://yourlink';
$msg = 'message'
$app->redirect($link, $msg, $msgType='message',$moved=false);
```

Take note that **$msgType** can be either _**message**_, _**notice**_ or _**error**_

The API page can be accessed here for Joomla! 1.5 and here for Joomla! 2.5
