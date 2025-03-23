---
author: "icarnaghan"
title: "How to setup LAMP (Linux, Apache, mySql, PHP) and phpMyAdmin in Fedora Core 15"
date: 2018-04-07
---

**NOTE**: This is a basic guide to setup **LAMP** on **Localhost**

We will start off by installing **mySql Server** first

```
sudo yum install mysql-server
```

Now we will need to **start** the **mySql Server**

```
sudo service mysqld start
```

We set a **password** for **mySql**

```
sudo mysqladmin -u root password ENTER_YOUR_PASSWORD_HERE
```

The next step will be to install **phpMyAdmin**, when we install **phpMyAdmin**, the **yum installer** **automatically** gets all **dependencies** and then installs **Apache** and **PHP**together with **phpMyAdmin**

```
sudo yum install phpmyadmin
```

All needed software **packages** are installed and now we will need to restart **Apache**and **mySql**

Restart **mySql**

```
sudo service mysqld restart
```

Restart **Apache**

```
sudo service httpd restart
```

The above two command will need to be run everytime the PC reboots in order to start the **Apache** and **mySql services** to automatically start these **services** when the PC reboots enter the commands below as root

```
sudo chkconfig --add httpd
 
sudo chkconfig httpd on
 
sudo chkconfig --add mysqld
 
sudo chkconfig mysqld on
```

That's all for a basic **LAMP** install
