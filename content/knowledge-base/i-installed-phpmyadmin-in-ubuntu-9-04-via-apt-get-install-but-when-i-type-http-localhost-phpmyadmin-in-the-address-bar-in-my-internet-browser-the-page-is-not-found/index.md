---
author: "icarnaghan"
title: "I installed phpMyAdmin in Ubuntu 9.04 via apt-get install but when I type http://localhost/phpmyadmin in the address bar in my Internet Browser the page is not found"
date: 2018-04-07
---

I installed **phpMyAdmin** in **Ubuntu 9.04** via **apt-get install phpmyadmin** but when I type **http://localhost/phpmyadmin** in the address bar in my Internet Browser the page is not found?  I have installed PHP, Apache2, mySql and have restarted Apache but still nothing happens when I type **http://localhost/phpmyadmin**.

1. Create a **symbolic link** in **/etc/apache2/conf.d** that points to**/etc/phpmyadmin/apache.conf**
    - Files included in the **/etc/apache2/conf.d/** directory are included as part of the **Global Server Configuration** and will load up everytime **Apache** loads
2. Use the following command to create a **symbolic link** of **apache.conf** in the **conf.d directory**: **sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf.d**
    - **sudo =** execute command as **root**
    - **ln -s =** command used to create a **symbolic link**
3. Restart **Apache** with **sudo service apache2 restart** on the command line
4. Enter the **root password**
5. Open your browser
6. Type in **http://localhost/phpmyadmin**
7. **phpMyAdmin** should now load
