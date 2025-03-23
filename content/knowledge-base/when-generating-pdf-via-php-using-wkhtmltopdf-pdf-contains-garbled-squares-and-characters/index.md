---
author: "icarnaghan"
title: "When generating PDF via PHP using wkhtmltopdf PDf contains garbled squares and characters"
date: 2018-03-22
---

I recently installed **WKHTMLTOPDF** on a **Centos 6** Box to generate **PDF's** via **PHP**, after a huge struggle to get **WKHTMLTOPDF** working, I encountered another problem, whenever trying to generate a **PDF** via the **PHP class** that I got from http://code.google.com/p/wkhtmltopdf/wiki/IntegrationWithPhp the PDF generated with funny Square's funny characters etc.

I initially thought this might be an encoding problem, so after another few days, I figured it could be a Font issue.

I installed all the X11 packages and that also didn't solve the problem. So initially I read somewhere I need the **urw-fonts** package. So I gave it a try and it worked.

So to solve the issue I SSH'd to my **Centos 6** server and installed the **urw-fonts** via **yum** and this eventually solved my problem

**SOLUTION:**

```
yum install urw-fonts
```
