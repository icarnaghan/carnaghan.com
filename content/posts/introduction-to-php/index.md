---
author: "icarnaghan"
title: "Introduction to PHP"
date: 2012-06-02
categories: 
  - "coding"
tags: 
  - "developing-with-php"
---

This week I have been reading the first five chapters of Beginning PHP 5.3, Doyle (2010).  Chapter 1 gave a good overview of PHP and it's advantages.  It drew comparisons to other programming languages, which I found interesting coming from a ColdFusion background.

<!--more-->

Doyle concludes that PHP occupies something of a middle ground when it comes to web programming languages.  He enforces the strength of the language or key benefits being its popularity and the fact that it is free of commercial licensing costs.  I have heard mixed opinions of PHP over the years.  The lead developer on one of my projects at work sent me this article: http://me.veekun.com/blog/2012/04/09/php-a-fractal-of-bad-design/.  He told me to read this, not to communicate the faults of PHP in terms avoidance, but to learn about some of the shortcomings which will help better my understanding of the various nuances of the language as I move forward.  I found some of the article interesting but much of it is difficult to follow as I am not familiar with the core PHP functionality.  I will revisit this article after my independent study concludes and hopefully will find it more useful.

The second chapter of the book spent much of the content helping the reader set up their local development environment.  I already have WAMP installed on my PC and have been running local instances of Drupal so much of this was familiar to me.  I have also created a PHP info file in the past using a basic script with the phpinfo() function, in order to check for things like physical paths, configuration information, etc.  While I have never programmed in PHP before, I have installed and configured (at a very basic level) pre-written scripts.  I did however find the tip for setting the local time zone helpful, as this is something I had not done before.

**Setting PHP Timezone**

- Check the current timezone by calling phpinfo(); (On my local development environment my timezone was set to UTC, this needed to be changed).
- Look for the timezone settings for America published at php.net: http://www.php.net/manual/en/timezones.america.php (I noted I would need to set mine to America/New\_York)
- Edit the date.timezone setting inside the php.ini file and change it (to America/New\_York)

There was other information in the second chapter that discusses manually compiling of PHP and links to resources for further guidance.  There was also information on how PHP is embedded in standard html pages through the use of the <?php ... ?> operators.  The example stating script included displaying of both static and dynamic text (date information) and included code comments.

Both of these chapters gave me a good introduction to the language and while much of what I read was familiar, there were some important concepts covered that I was unaware of.  My next blog entry will cover the next few chapters starting with PHP Language Basics in chapter 3.
