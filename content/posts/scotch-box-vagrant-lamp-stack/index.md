---
author: "icarnaghan"
title: "Scotch Box Vagrant LAMP Stack"
date: 2015-04-28
categories: 
  - "coding"
---

For a while now I have been using WAMP as my daily driver for Drupal development on my Windows 8 machine. For anyone who is a Drupal developer and uses WAMP (or a variation LAMP stack on Windows) has probably felt the pain it brings in terms of sluggishness, incompatibility with native Linux applications (Drush anyone?), and a headache administer PHP modules. I won’t even get into the problems I’ve had in the past getting cURL to work properly in Windows. I decided it was finally time for me to explore Vagrant as I had heard a lot about it but had never taken the time to do any amount of research.

My goal was to find a basic LAMP replacement for my current environment and after some research I found Scotch Box. Scotch Box has been designed to be a really simple LAMP stack for developers to get up and running quickly. Since I have started using Scotch Box I have ditched WAMP and I am not looking back. I have a lean, fast and native Linux development experience that has been a lot of fun to work with. In order to install Scotch Box you will need to download and install Virtualbox and Vagrant. Full setup instructions are provided on the Scotch Box website. Once you are up and running you can begin setting up your environment.

## Setting up your sites

The default Scotchbox setup includes the default Ubuntu Linux file system. The most important directories you will be working in are

- /var/www - this is your main web directory where you can store your site files. Under www I have a collection of sub-directories for my various projects
- /etc/apache2/sites-available - this is where you will clone the default 000-default.conf file for any sites you decide to host in your new VM

Browse over to the excellent step-by-step guide for creating multiple virtual hosts  for your sites at Digital Ocean. Once you have created your new conf files, you should then be able to easily enable and disable sites using the **sudo a2ensite** and **sudo a2dissite** commands. Don't forget to restart apache any time you make changes to the configuration by issuing the **sudo service apache2 restart** command.

Once you are setup, you can also easily install other tools by using the apt-get command. For Drupal developers, if you use Drush, you will want to install this by issuing sudo apt-get install drush. More details can be found in the Upgrading/Downgrading Drush on Ubuntu documentation at drupal.org.

## Working in your Primary OS

Whether you are a Mac or Windows user, you will be able to continue to use your favorite code editors and database tools locally. One of the nice things about Scotchbox is the way it sets up directory shares. In the location where you install scotchbox, any sub-directories created here are automatically cloned in your /var/www directory in the guest OS. This basically means that your guest OS will be using its own native file system for serving your site pages, but you also get a synchronized copy locally so you can edit files directly in Windows or on the Mac. Currently my setup includes Sublime text editor, several other IDEs and MySQL Workbench. For setting up a connection to the database you will need to use SSH, full details on this can be found under 'Database Access' at on the main Scotchbox site.

**Get started now with Scotch Box by visiting their article Introducing Scotch Box - A Vagrant LAMP Stack That Just Works.**

Cover page image property of box.scotch.io
