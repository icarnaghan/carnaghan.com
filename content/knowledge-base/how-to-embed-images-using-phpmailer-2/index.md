---
author: "icarnaghan"
title: "How to embed images using PHPMailer"
date: 2018-09-02
---

1. Use the **AddEmbeddedImage** method provided by the **PHPMailer** class.  eg. $mail->**AddEmbeddedImage**('test.gif','testImage','test.gif');
2. Parameters for **AddEmbeddedImage**($path, $cid, $name = '', $encoding = 'base64', $type = 'application/octet-stream')
    1. **$path** \= _Path to the attachment_
    2. **$cid** \= _Content ID of the attachment.  Use this to identify the Id for accessing the image in an HTML form._
    3. **$name** \= _Overrides the attachment name._
    4. **$encoding** \= _File encoding_
    5. **$type** \= _File extension (MIME) type._

**Example**:

**<?php**     _//Include the PHPMailer class_ include = '**class.phpmailer.php**';

$mailer=new phpmailer(); $mailer->From =’sender@techportal.co.za’; $mailer->FromName=’TechPortal'; $mailer->Subject =’TechPortal Example’; $mailer->AddAddress(’recipient@techportal.co.za’);

$mailer->IsHTML(true);  **$mailer->AddEmbeddedImage(’test.gif’,'testImage’,'test.gif’);** $mailer->Body =’<img src=”**cid:testImage**”>’;

$mailer->Send(); **?>** 

 

DOWNLOAD PHPMailer Class (Version: 2.0.4)
