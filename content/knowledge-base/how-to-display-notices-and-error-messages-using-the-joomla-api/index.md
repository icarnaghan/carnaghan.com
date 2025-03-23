---
author: "icarnaghan"
title: "How to display Notices and Error Messages using the Joomla! API"
date: 2018-03-24
---

Errors, warnings and notices can be displayed at any time within any custom component, module and plugin.

Ensure that you have the following code inside your **Joomla! template** where you would like the **errors, warnings and notices** displayed.

```
<jdoc:include type="message" />
```

To display a Message user the following code within your **Component**, **Module** or **Plugin**

```
JFactory::getApplication()->enqueueMessage('Your Message');
```

To raise a notice use the following code

```
JError::raiseNotice( 100, 'Your Notice' );
```

To display a Warning use the following

```
JError::raiseWarning( 100, 'This is a Warning' );
```

To display an Error

```
JError::raiseError( 4711, 'A error occurred' );
```

 

Since **Joomla! 3.x** uses bootstraped templates, standard bootstrap **CSS styles** for **Alerts** will be used

```
JFactory::getApplication()->enqueueMessage('Your Message', 'type');
```

In the above **type** can be one of

- EMPTY - yellow
- 'info' - blue
- 'error' - red
- 'success' - green

To display a error use the example below

```
JFactory::getApplication()->enqueueMessage('ERROR', 'error');
```

 

For more information click here
