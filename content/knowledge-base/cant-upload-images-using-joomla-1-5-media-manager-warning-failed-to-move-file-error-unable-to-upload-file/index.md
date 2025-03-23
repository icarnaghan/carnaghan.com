---
author: "icarnaghan"
title: "Can't upload images using Joomla! 1.5* Media Manager * Warning: Failed to move file! * Error. Unable to upload file"
date: 2018-04-06
---

If you try to upload images via the Joomla! 1.5.\* Media Manager and it fails with the error message belowand need to solve it

**\* Warning: Failed to move file! \* Error. Unable to upload file.**

**Solution**

Change the permissions of you're images folder recursively to 755 or 777 (Not advisable) by using the following Linux Command: **chmod -R images 755 images**
