---
author: "icarnaghan"
title: "How to Ban an IP Address using .htaccess"
date: 2018-03-22
---

If you do not want a certain person/IP Address to access your website you can add the following code to your .htaccess file 

```
order allow,deny 
deny from xxx.xxx.xxx.xxx 
allow from all
```

In the above code replace the xxx with the IP Address that you would like to Ban accessing your website
