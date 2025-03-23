---
author: "icarnaghan"
title: "Catchable fatal error: Object of class JVersion could not be converted to string in /components/com_acajoom/classes/class.jmail.php on line 1083 using Acajoom News 1.6.0 or later in Joomla! 1.5"
date: 2018-04-06
---

If you are using Acajoom News 1.6.0 or later in Joomla! 1.5 and you are getting Error Message at STEP 4 **Catchable fatal error: Object of class JVersion could not be converted to string in /components/com\_acajoom/classes/class.jmail.php on line 1083** when trying to send a newsletter .

To solve this problem, please follow the steps below.

**STEP 1**

In the **Acajoom configuration page** under Tab: **'Logs & Stats'**

- Locate **Send out performance**
- **Turn it off**, by selecting **no** next to **Send out performance**
- Re-try sending and it should work.
