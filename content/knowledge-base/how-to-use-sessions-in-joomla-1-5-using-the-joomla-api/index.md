---
author: "icarnaghan"
title: "How to use sessions in Joomla! 1.5 using the Joomla! API"
date: 2018-03-30
---

- This can be obtained using the _**JFactory/getSession object**_
- Instantiate the **getSession** object
    
    ```
    $session =& JFactory::getSession();
    ```
    
    There are a couple of parameters that you can pass with this object. They are
    - name - The session name
    - id - Unique ID of the session
    - expire - Expiry date and time
    - security - Comma separated security options, have a look at JSession
- Now we set the session
    
    ```
    $session->set( 'mySession', 'sessionValue' );
    ```
    
- We get the session variable as follows
    
    ```
    $session->get( 'mySession' );
    ```
    

**NOTE**: For more information refer to the Joomla! API documentation.
