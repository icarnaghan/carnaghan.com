---
author: "icarnaghan"
title: "Nusoap - PHP Warning: Attempt to modify property of non-object in nusoap/lib/nusoap.php on line 4603"
date: 2018-03-22
---

Open the file **_lib/nusoap.php_** and change line 4594 from

```
$this->schemas[$ns]->imports[$ns2][$ii]['loaded'] = true;
```

to

```
$this->schemas[$ns][$ns2]->imports[$ns2][$ii]['loaded'] = true;
```

Source: http://sourceforge.net/projects/nusoap/forums/forum/193578/topic/4566878
