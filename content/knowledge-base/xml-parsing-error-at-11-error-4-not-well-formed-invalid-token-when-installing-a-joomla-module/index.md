---
author: "icarnaghan"
title: "XML Parsing Error at 1:1. Error 4: Not well-formed (invalid token) when installing a Joomla! module"
date: 2018-04-06
---

What to do if you receive the following error "**XML Parsing Error at 1:1. Error 4: Not well-formed (invalid token)**" when installing a Joomla! module.

**Explanation**: The files in the **module** have been **zipped** using an **Apple MAC**. The **MAC** adds an **extra folder** called **\_\_MACOSX** into the **modules** **zip** file.

Follow these steps in order to solve the problem.

**STEP 1**

**Unzip** (Extract) the **modules** **zip file**.

**STEP 2**

Open the **unzipped (extracted) folder**.

**STEP 3**

**Delete** the  **\_\_MACOSX** folder within the **unzipped (extracted) folder**.

**STEP 4**

**Zip** the **unzipped (extracted) folder** (_The extracted module_) and **re-install** the **module** and the **error message** will disappear.

 

**NOTE**: The **module** will still be **installed successfully** whether the **error message**appears or not.
