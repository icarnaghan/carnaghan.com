---
author: "icarnaghan"
title: "Adding a link head tag with Joomla 3"
date: 2018-03-24
---

If you have a custom Joomla plugin or component and you would like to add a link head tag to the page, then Joomla has a way for you to do this.

To accomplish this you would make use of the **JDocumentHTML** class using the **addHeadLink** method.

This method adds tags to the head of the document. The syntax for this method is as follows:

```
addHeadLink(string $href, string $relation, string $relType = 'rel', array $attribs = array()) : \JDocumentHTML
```

- **$href** is of _**Data type** **string**_ and contains the linked resource.
- **$relation** is of _**Data type** **string**_ and contains the relation.
- **$relType** is of _**Data type** **string**_ and contains the relation type. May be '**rel**' indicating a forward relation, or '**rev**' for a reverse relation.  The default value is **rel**
- **$attrbs** is of _**Data type array**_ and contains a associative array of remaining attributes.

If you would like to build the following link

```
<link href="http://example.com/mycontent/" rel="canonical" >
```

Then the syntax would be:

```
$document = JFactory::getDocument();
$document->addHeadLink( 'http://example.com/mycontent', 'canonical', 'rel');
```
