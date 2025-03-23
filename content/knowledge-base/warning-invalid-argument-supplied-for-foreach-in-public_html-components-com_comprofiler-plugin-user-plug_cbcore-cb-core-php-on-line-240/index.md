---
author: "icarnaghan"
title: "Warning: Invalid argument supplied for foreach() in /public_html/components/com_comprofiler/plugin/user/plug_cbcore/cb.core.php on line 240"
date: 2018-04-06
---

If you get the error message **Warning: Invalid argument supplied for foreach() in /public\_html/components/com\_comprofiler/plugin/user/plug\_cbcore/cb.core.php on line 240** when using **Community Builder** together with **Fireboard** and clicking on **My Profile** and also receive weird descriptions in the form (**missing language file**) and need to fix it, follow the short steps below to solve the problem.

 

![Error](images/cbfb.JPG "Error")

 

**STEP 1**

To solve the **language** issue, locate the **language file** and add the following lines at the bottom of the file and save it and upload it. (**/components/com\_comprofiler/plugin/language/YOURLANG/YOURLANG.php**)

**DEFINE('\_UE\_USER\_FAVS','Your favorite'); DEFINE('\_UE\_THREAD\_UNFAV',':: Remove favorite ::'); DEFINE('\_UE\_USER\_NOFAV','No favorites found for you'); DEFINE('\_UE\_USER\_UNFAV\_ALL','Remove all your favorites'); DEFINE('\_UE\_fb\_CONFIRMUNFAVEALL','Confirmation removal'); DEFINE('\_UE\_FB\_TABTITLE','Forum Settings'); DEFINE('\_UE\_FB\_TABDESC','Description'); DEFINE('\_UE\_FB\_VIEWTYPE\_TITLE','View type'); DEFINE('\_UE\_FB\_ORDERING\_TITLE','Ordering'); DEFINE('\_UE\_FB\_SIGNATURE','Signature'); DEFINE('\_UE\_FB\_VIEWTYPE\_FLAT','Flat View'); DEFINE('\_UE\_FB\_VIEWTYPE\_THREADED','Threaded View'); DEFINE('\_UE\_FB\_ORDERING\_OLDEST','Oldest First'); DEFINE('\_UE\_FB\_ORDERING\_LATEST','Latest First');**

Refresh your page and the language problem will be sovled.

**STEP 2**

To solve the **Warning: Invalid argument supplied for foreach() in /public\_html/components/com\_comprofiler/plugin/user/plug\_cbcore/cb.core.php on line 240** problem locate the **cb.cb\_core.php** file and edit it as described below.

On about **line 475** comment the following lines out

 **/\* //Implementing Joomla's new user parameters such as editor $userParams = array(); $userParams = $this->\_getUserParams($ui, $user);

if ( ( count( $userParams ) > 0 ) && in\_array( $\_CB\_framework->getCfg( "frontend\_userparams" ), array( '1', null) ) ) { //Loop through each parameter and render it appropriately. foreach($userParams AS $userParam) { $return .= "<tr>\\n"; $return .= "<td class=\\"titleCell\\">" . $userParam\[0\] . ":</td>\\n"; $return .= "<td class=\\"fieldCell\\">" . $userParam\[1\]; $return .= getFieldIcons($ui, false, false, (isset($userParam\[2\]) && class\_exists(" JText") ? JText::\_($userParam\[2\]) : null), (isset($userParam\[3\]) && class\_exists("JText") ? JText:: \_($userParam\[3\]) : null)); $return .= "</td></tr>\\n"; } } \*/**

 

After you've commented those lines out. Remove the following line **$params->loadSetupFile(JApplicationHelper::getPath( 'com\_xml', 'com\_users' ));** in the **cb.cb\_core.php** file.

Change line **$params =& $juser->getParameters();** to **$params =& $juser->getParameters(true);**

Save the file and upload it.

Refresh your page and the error message should be gone and problem solved.
