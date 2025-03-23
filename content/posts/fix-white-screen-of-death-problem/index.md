---
author: "prhost78"
title: "How to fix White Screen of Death Problem?"
date: 2016-10-03
categories: 
  - "cms"
tags: 
  - "affiliate"
  - "tips"
  - "wordpress"
---

Like the Blue screen of death error, the WSOD is the most commonly reported error. The white screen problem occurs because of few lines of code crashing the entire application. Experienced programmers can fix the issue in a few minutes. If a novice user who hired a freelancer or uses a content management system sees the white screen, he should follow the below two methods to fix the problem.

### WSOD in sites other than CMS

When you see the white screen of death, the first thing you should do is check log files. Unless you change the path of log files in the server's config file, the web and DB server creates log files in the /var/ directory in Linux. In most of the cases, you'll find the root cause problem for the WSOD problem in these files.

If you are the developer of the site, fix the code and restart the web server. If you hired a freelancer for developing the website, contact him/her immediately because the issue won't resolve unless you fix the erroneous code.

### WordPress White screen of death error

Plugins and themes are the two of the most important parts of a WP site. WordPress is an open-source CMS. It is the best CMS because developers from various parts of the world have launched high-quality plugins and themes. The developers use PHP for writing themes and plugins. Thinking and coding style differ from person to person, but WP developers should refer WordPress coding standards.

Despite the excellent Coding Standards, sometimes, a plugin may conflict with a theme (or vice versa) making the web server use a large amount of RAM. In such case, you'll see white screen of death page instead of your theme's single post, page, archive, category or post page.

The best way to fix WSOD problem in WordPress is to enable WP DEBUG option in the wp-config.php file. You'll find the below function to make WordPress enter the debug mode in the WP configuration file.

`define( 'WP_DEBUG', true );`

If you don't find the above line in the config.php file, add it manually.

Once you enable the mode, you'll see the error message in the web-browser's tab instead of the white screen. The message shows the full path of the error causing file.

Remove the faulty plugin or theme, disable it and clear the cache created by the WordPress caching plugin you use. Now, change the parameter "true" to "false".

**Conclusion**: You can easily fix the WSOD problem by following one of the two techniques we've described above.
