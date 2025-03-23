---
author: "icarnaghan"
title: "Lessons Learned using Drupal’s Domain Access Module"
date: 2017-10-03
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
  - "php"
---

Over the last few months my team has been developing microsites to accompany our main website. The requirements for these sites included having their own domain, theme and separate content. After reviewing options in Drupal 7, I decided the best approach given our situation was to use the Domain Access Module. The Domain Access Module provides a very solid and powerful framework for developing additional sites within your existing Drupal CMS, but it can also be somewhat complicated to setup for any given use case. I have documented some of the lessons learned over the last few months as we implemented Domain Access in our own project.

## Careful Planning

Before starting work on any of the implementation details, it is essential to have a solid content strategy plan up front. What content types will be needed for the new site, what will the restrictions be, what base theme would be most suitable, etc. In addition to this careful consideration should be given to views, context and taxonomy. Careful naming for content types should be considered (We went with prefixes to sort and separate the micro-sites from main site content types). Also consider what impact will the new site or sites have upon the existing CMS infrastructure. By thinking a lot of these issues through at the beginning, you will save a lot of headaches during the development phase.

## Understand the Bundled Modules

When I first started using the Domain Access module, I only enabled one or two of the included modules. I quickly found myself enabling the majority of these modules as my project required more functionality. Here is a quick run-down of the modules I currently use:

### Domain Alias

Essential if you need to forward or setup other sub-domains pointing to your Drupal domain sites. The best use case for us was handling www and non-www domain names.

### Domain Content

Absolutely a must of setting up default values across content types. Works well with the Domain Source module (which adds canonical source paths to your content).

### Domain Source Module

This comes in really handy when looking at content lists from multiple sites and ensuring the user lands on the correct domain and path. Not a problem on the front-end so much, but a must for backend administration screens.

### Domain Theme

Self explanatory, without this you will not be able to assign your new theme to the new site. I found the best approach was to assign the theme to site-specific content types.

### Domain Configuration & Domain Settings

Both are needed for site/domain specific settings which you will use throughout your development phase.

## Rebuilding Content Permissions

One thing to consider when using Domain Access is that it will need to rebuild your content permissions upon enabling it. This is mandatory, there is no way around this and it can sometimes be problematic so of course test thoroughly in your dev and integration environments first. If you do run into problems it will most likely be due to the fact the rebuilding process never completes. I had a problem where content permissions would fail at 99.98% completion but never make it to 100. It would simply sit there and mock me. After doing some research I quickly discovered that other contributed modules or poor configuration can result in content permissions not rebuilding correctly. Upon further research I found that the Drush command for rebuilding content permissions seemed to work, but the UI method would not. For anyone out there having a similar problem, try using Drush:

```
drush php-eval 'node_access_rebuild();'
```

It will take a long time, so do be patient. Go grab a coffee and come back and fingers crossed content permissions will be rebuilt. I’ve yet to see this fail on our projects using the Drush method, however I am still not sure why it sometimes fails using the UI.

## The ‘All Affiliates’ Problem

This is something that WILL come back to bite you if not configured correctly from the start. When you initially enable the Domain Access module you will notice that it automatically assigns all existing content to the ‘All Affiliates’ bucket. This means that all existing content on your site will be accessible by new domain sites if not changed. The problem with this is when you have a site of over 4000 nodes, it becomes cumbersome to reset this for all nodes. There are articles out there that describe ways to use a custom module to reset this, however I found the following simple SQL query worked just as well:

```
delete from domain_access where gid = 0
```

Use the above with caution and test and re-test on your integration and test environments before doing this in production. After you have purged the ‘all affiliates’ entry you must rebuild content permissions again! If you structure your sites well, you may not even have to do this. The problem we ran into was that Google began indexing content on a micro site that was meant only to be displayed on the main site. This can look bad (rendering with the wrong theme, or worse), so I recommend to not use ‘All Affiliates’ wherever possible. I don’t see a use case for us to reuse duplicate content across sites, however others out there may have that need for whatever reason.

## Using Domain Access with $base\_url

This was a struggle for me at first. Everything I read about Domain Access was that we should not be setting the $base\_url variable. The problem however was that our setup required this variable in several contrib modules. $base\_url essentially locks in the domain for your site, but when you are rendering multiple sites via one Drupal core, this can be problematic. The best way around this is to use the $\_SERVER PHP function, which allows us to pass in the host name dynamically to $base\_url. Simply set this in your Drupal settings file.

## Automating configuration across Development Environments

Alright so you’re up and running and everything looks great, the only other problem is when you refresh your lower test, dev, integration environments, you have to manually go in and change the domain URLS as these will not be the same as production. I use the following SQL command to update my domains in our Continuous Integration scripts (I have separate scripts for each tier). You could also use Drush if you prefer:

```
update domain set subdomain='site1.com' where domain_id = 1; update domain set subdomain='site2.com' where domain_id = 2; update domain set subdomain='site3.com' where domain_id = 3;
```

You can also change http/https values in scheme column of the domain table.

Well that’s about it from my lessons learned. If anything else comes to mind I’ll update this post. If you have any experiences or lessons learned from using the domain access module, please feel free to leave a comment below.
