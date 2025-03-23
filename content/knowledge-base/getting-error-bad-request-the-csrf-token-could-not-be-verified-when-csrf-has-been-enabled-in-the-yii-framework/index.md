---
author: "icarnaghan"
title: "Getting error: Bad Request The CSRF token could not be verified: when CSRF has been enabled in the Yii Framework"
date: 2018-03-22
---

Getting error: **Bad Request The CSRF token could not be verified**: when CSRF has been enabled in the Yii Framework and I'm clicking on a **linkButton** within a form.

Add  **'YII\_CSRF\_TOKEN' => Yii::app()->request->csrfToken** to the params array in the linkButton

**Example** 

```
<?php echo CHtml::linkButton('Register', array('submit' => ' ',
                                              'params' => array('reg'=>'new', 'YII_CSRF_TOKEN' => Yii::app()->request->csrfToken ),
                        ));
 
?>
```
