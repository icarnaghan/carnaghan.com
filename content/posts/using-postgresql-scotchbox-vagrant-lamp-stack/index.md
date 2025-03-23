---
author: "icarnaghan"
title: "Using PostGreSQL with Scotchbox Vagrant LAMP Stack"
date: 2016-08-03
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

I have been using Scotchbox for a while now and continue to be impressed by it's simplicity and ease of use compared to other Vagrant environments I have used in the past. Recently I started working on a Drupal 8 project that required the use of a PostGreSQL (PostGres) database. Thankfully, when I checked the Scotchbox 2.0 documentation, it appeared that PostGres came packaged up with the environment and ready to use. After doing a little bit of research I realized I needed to follow a couple of steps in order to get this running properly with a PostGres client. I am outlining the steps below.

## Choosing the right PostGreSQL Client

As a Mac user I was looking for a client that would work well with OSX. I limited my options to three applications:

- pgAdmin (https://www.pgadmin.org/) - Free and available for Windows and Mac
- pSequel (http://www.psequel.com/) - Free Mac only client, nicer looking interface than pgAdmin but more limiting
- Datagrip (https://www.jetbrains.com/datagrip/) - Commercial application for Windows and Mac - supports multiple database servers

After playing around with Datagrip, I realized it was a nice application, however it seemed a little overkill for what I needed. Datagrip supports multiple database types including MySQL / MariaDB, SQL Server, Oracle, etc. I went with pgAdmin in the end as this seems to be the main goto client for PostGres users and contains everything I need to connect and run queries against my databases. I may try pSequel at a later date and will report on my findings.

## Configuring PostGres within Scotchbox

The first time I tried connecting to my PostGres Vagrant server I received a 'Could not connect' / 'Permission Denied' error. After doing a bit of research I came across a helpful post on the subject by Ben Tenner. In his post Ben highlights a couple of additional steps needed in order to connect to PostGres from a client such as pgAdmin.

Login to Scotchbox using 'vagrant ssh' and then complete the following:

### 1\. Update Permissions on the pg\_hba.conf file

```
sudo nano /etc/postgresql/9.3/main/pg_hba.conf
```

Go to the end of this file and add the following line:

```
host all all all password
```

### 2\. Update listen\_addresses in postgresql.conf

```
sudo nano /etc/postgresql/9.3/main/postgresql.conf
```

Add the following line to this file:

```
listen_addresses = '*'
```

### 3\. Setup your connection in pgAdmin

Open pgAdmin and select File -> Add Server. Fill in the following details:

```
Name: scotchbox (this can be any name you like) Host: 192.168.33.10 (default scotchbox IP) Port: 5432 Maintenance DB: postgres Username: root Password: root Group: Servers
```

After you have completed these steps restart your Vagrant box and then attempt to connect. You should your server listed as scotchbox (192.168.33.10:5432) on the left hand side. pgAdmin will allow you to create new databases and run SQL queries against existing databases setup in your server.
