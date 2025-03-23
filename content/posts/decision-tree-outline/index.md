---
author: "icarnaghan"
title: "Decision Tree Outline"
date: 2012-07-15
categories: 
  - "coding"
tags: 
  - "developing-with-php"
---

The decision tree application is currently a work-in-progress.  The main source files can be downloaded here: **Source Files.**  The current demo is non-functional and only shows a subset of the application, which will be developed in the upcoming weeks: **Demo Application (Work in progress)**

<!--more-->The proposed text-based decision tree will be written in PHP and contain the following files:

**config.php**

All configuration information needed for the application stored in the form of global constants including database connection credentials.

**common.inc.php**

A basic template include file which contains the applications HTML header and footer used on various pages throughout the site.  By creating one main common.inc.php file, layout changes can be implemented more easily.

**controller.php**

This file will contain the heart of the application including all of the main functions required to make changes to current decision trees and branches and to add and remove content accordingly.  The controller will also contain common database functions for easier updating calls from other parts of the application.

**index.php**

The starting file of the application will include a tabular display of all available decision trees with the ability to drill down into the details of each.  The user will also be able to add new trees directly from the home page.

**view\_\*.php**

The various view files will be prefixed with view\_ and display the relevant information of the various trees and branch details.

**style.css**

The global CSS styles will be used throughout the site.

**decision\_tree.sql**

The database structure used to create an instance of the decision tree database.
