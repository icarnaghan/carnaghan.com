---
author: "icarnaghan"
title: "Editing the pg_hba.conf file on a PostgreSQL database server so that a specific (other) server will be able to connect to the PostgreSQL database server"
date: 2018-04-07
---

Editing the **pg\_hba.conf** file on a **postgresql** **database** **server** so that a specific (other) server will be able to connect to the **postgresql** database server.

**Example**: Say I have a server where all of my **postgresql** databases are running and I have an application on another server that needs to access a database from the database server. To make this possible I need to edit the **pg\_hba.conf** file to allow access to the application server.

Please follow the steps below for enabling this

1. Make sure your using the **CLI**
2. First step is to take a backup of the **pg\_hba.conf** file so that if you mess up you'll have a backup to restore. The **pg\_hba.conf** file is stored in the following directory '**/var/lig/pgsql/data**'
    
    Excecute the command below in order to take a backup
    
    ```
    sudo tar cvf /var/tmp/pg_hbaConf_backup.tar /var/lib/pgsql/data/pg_hba.conf
    ```
    
    By using the **tar archive** you are preserving the permissions and directories of the files and directories that got compressed.
3. To restore the **pg\_hba.conf** file execute the commands below
    
    ```
    cd /var/lib/pgsql/data/
    
    sudo tar xvf /var/tmp/pg_hbaConf_backup.tar
    ```
    
4. Now we need to edit the **pg\_hda.conf** file as the commands below illustrate
    
    ```
    sudo echo '#SERVER 10.0.26.11 will be able to access the postgres database' 
    
    sudo echo 'host    all         all         10.0.26.11         255.255.255.255   trust' >> /var/lib/pgsql/data/pg_hba.conf
    ```
    
    This code will be appended to the **pg\_hba.conf** file. First we add a comment to explain why the server should have access and then the actual command. To edit the newly inserted lines, use the **VIM editor** or any other **editor** to edit the **pg\_hda.conf** file.
5. In order for the change to take effect restart the **postgresql** database by using the command below. {codecitation type: bash}sudo service postgresql restart{/codecitation}
6. Locate the **postgresql.conf** located in **/var/lib/pgsql/data/** and change or add the line below. By default **postgresql** listens on **localhost**.
    
    ```
    listen_addresses = '*'
    ```
