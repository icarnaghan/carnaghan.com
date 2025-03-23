---
author: "icarnaghan"
title: "How to change the Return-path email address using the PHPMailer class"
date: 2018-03-22
---

Fill the **$Sender** property with the email address you wish to have as the **Return-path** 

E.g.

```
$mail->Sender="test@testmail.com";
```

This property can be found on **Line 97** in the **class.phpmailer.php** file 

```
  /** 
   * Sets the Sender email (Return-Path) of the message.  If not empty, 
   * will be sent via -f to sendmail or as 'MAIL FROM' in smtp mode. 
   * @var string 
   */ 
  public $Sender            = '';
```
