---
author: "icarnaghan"
title: "How to return a associated array from an single record in the table using Joomla! 2.5 and 1.5 API"
date: 2018-03-24
---

Use the loadAssoc() method as in example below

```
$db = $this->getDbo();
$db->getQuery(true);
$db->setQuery("SELECT count(id) as count FROM #__database_table");
$count = $db->loadAssoc();
echo $count['count'];
```
