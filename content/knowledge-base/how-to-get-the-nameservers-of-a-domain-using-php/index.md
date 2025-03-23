---
author: "icarnaghan"
title: "How to get the Nameservers of a domain using PHP"
date: 2018-03-22
---

Use the  **dns\_get\_record** function with type **DNS\_NS**

**Example**:

_//Add this piece of code to your PHP will_ $result = dns\_get\_record('yourdomain.com',DNS\_NS);

Execute the script

_//An array will be returned similar as below_

```
Array
(
    [0] => Array
        (
            [host] => yourdomain.com
            [type] => NS
            [target] => ns1.yourdomain.com
            [class] => IN
            [ttl] => 70144
        )

    [1] => Array
        (
            [host] => yourdomain.com
            [type] => NS
            [target] => ns2.yourdomain.com
            [class] => IN
            [ttl] => 70144
        )

)
```

**Explanation**:

**dns\_get\_record** = Fetch DNS Resource Records associated with a hostname (PHP 5)
