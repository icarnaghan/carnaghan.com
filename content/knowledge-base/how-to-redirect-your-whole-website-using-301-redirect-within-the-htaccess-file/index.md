---
author: "icarnaghan"
title: "How to redirect your whole website using 301 redirect within the .htaccess file"
date: 2018-03-22
---

In your **Document root** open the **.htaccess** file if present otherwise create a **.htaccess** file

Once the file is open edit the contents of the file and add the following code to it

```
Redirect 301 / http://yoursite.com/
```

Replace the url with your url where you want your website to be redirected to.

Upload the **.htaccess** file and test, the redirection should work
