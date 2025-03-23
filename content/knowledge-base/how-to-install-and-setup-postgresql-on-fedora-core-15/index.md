---
author: "icarnaghan"
title: "How to install and setup PostgreSQL on Fedora Core 15"
date: 2018-04-07
---

1. Open a new **Terminal Window** and then install the latest **PostgreSQL** **Server**
    
    ```
    sudo yum install postgresql-server
    ```
    
2. Now we need to initialize the Database Cluster
    
    ```
    sudo service postgresql initdb
    ```
    
3. Now start the server
    
    ```
    service postgresql start
    ```
    
4. Now login with the postgres user
    
    ```
    sudo su -l postgres
    ```
    
    This user automatically gets created when the **PostgresSQL** server gets installed
5. Now we create a new PostgreSQL user
    
    ```
    createuser --no-superuser --no-createdb --no-createrole --pwprompt testUser
    ```
    
    When prompted for a password just enter any password you prefer
6. Create a **new Database** and assign it to the newly created user
    
    ```
    createdb --owner testUser Database
    ```
    
7. In order to allow connections from servers to this server edit the _**pg\_hba.conf**_ file
    
    ```
    vi /var/lib/pgsql/data/pg_hba.conf
    ```
    
8. Reload the **postgreSQL server** so that all changes can take effect
    
    ```
    service postgresql reload
    ```
