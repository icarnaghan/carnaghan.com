---
author: "icarnaghan"
title: "Warning: Invalid argument supplied for foreach() in /components/com_comprofiler/plugin/user/plug_cbcore/cb.core.php on line 240"
date: 2018-04-06
---

I get the following error  "**Warning: Invalid argument supplied for foreach() in /components/com\_comprofiler/plugin/user/plug\_cbcore/cb.core.php on line 240**" when trying to edit my Community Builder profile. How can I solved this?

**NOTE**: Received this error using **Joomla! 1.5.10** together with **Community Builder 1.1**

 

**Answer**:

1. Locate the following file in the root directory of your **Joomla!** installation. {codecitation class="brush:plain;"}components/com\_comprofiler/plugin/user/plug\_cbcore/cb.core.php{/codecitation}
2. Change the following code on **line 528** {codecitation class="brush: php;"} $params =& $juser->getParameters(); {/codecitation} so that it reads
    
    {codecitation class="brush: php;"} $params =& $juser->getParameters(true); {/codecitation}
3. Delete line 520 {codecitation class="brush: php;"} $params->loadSetupFile(JApplicationHelper::getPath( 'com\_xml', 'com\_users' )); {/codecitation}
4. Problem should be solved!!!
