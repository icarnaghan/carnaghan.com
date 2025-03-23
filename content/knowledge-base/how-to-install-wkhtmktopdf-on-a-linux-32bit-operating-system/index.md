---
author: "icarnaghan"
title: "How to install wkhtmktopdf on a Linux 32bit Operating System"
date: 2018-04-07
---

1. Open a new _**Terminal Window**_
2. Download the _**wkhtmltopdf**_ library
    
    ```
    http://wkhtmltopdf.googlecode.com/files/libwkhtmltox-0.11.0_rc1-i386.tar.bz2
    ```
    
3. Extract the library
    
    ```
    tar xvjf libwkhtmltox-0.11.0_rc1-i386.tar.bz2
    ```
    
4. Move the library to the _**/usr/local/bin/wkhtmltopdf**_ directory
    
    ```
    mv wkhtmltopdf-i386 /usr/local/bin/wkhtmltopdf
    ```
    
5. Make the _**/usr/local/bin/wkhtmltopdf**_ executable
    
    ```
    chmod +x /usr/local/bin/wkhtmltopdf
    ```
    
6. Try it
    
    ```
    wkhtmltopdf http://google.co.za /home/roland/Desktop/google.pdf
    ```
