---
author: "icarnaghan"
title: "How to get the last Inserted Id using the Joomla! Platform"
date: 2018-03-25
---

After you performed an **Insert statement** use the **insertid** method to get the auto-incremented value from the last Insert statement

```
$db = $this->getDbo();
$query  = $db->getQuery(true);
 $query->clear();
$query->insert('#__database_table1');
$query->set("id=".(int)$id);
$db->setQuery($query);
 $db->query();
 
//Now we get the last inserted id
$lastInsertId = $db->insertid();
 
echo $lastInsertId;
```

Note in the above code we used _**$db->insertid();**_ to obtain the last inserted id.
