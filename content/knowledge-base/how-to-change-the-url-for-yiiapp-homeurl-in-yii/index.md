---
author: "icarnaghan"
title: "How to change the url for Yii::app()->homeUrl in Yii"
date: 2018-03-22
---

1. Open the main configuration file _**protected/config/main.php**_
2. Now in the _**main.php**_ file we can assign a Action or Url to _**homeUrl**_ \_highlight\[1\] = "\\n\\nreturn array(\\n\\n \\'basePath\\'=>dirname(\_\_FILE\_\_).DIRECTORY\_SEPARATOR.\\'..\\',\\n\\n  \\'homeUrl\\'=>array(\\'site/login\\'),\\n\\n  ....\\n\\n";
    
    ```
    return array(
     
     'basePath'=>dirname(__FILE__).DIRECTORY_SEPARATOR.'..',
     
      'homeUrl'=>array('site/login'),
     
      ....
    ```
