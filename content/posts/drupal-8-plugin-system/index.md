---
author: "icarnaghan"
title: "Drupal 8 Plugin System"
date: 2016-08-14
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

There is a lot of new terminology in Drupal 8 and for anyone not familiar with Object Oriented programming, some of it can be downright confusing. For myself, I have worked with OOP for quite a while, however I have not spent as much time writing custom modules for Drupal 7. While I am familiar on the surface with the hook system and API at a very novice level, I have never really had to do any intense back end development in D7. Now that I am working in Drupal 8, things are quite different with my projects at work. Thankfully my OOP background has filled in some of the gaps, however my lack of Drupal 7 module development knowledge has proven to be a burden.

In Day 8 we are looking at the Plugin System and I have to be honest I was a little bit confused when I started looking at plugins. Part of the reason for this was down to my lack of knowledge of Drupal 7 development concepts, most notably, hook\_info. In addition to this, I had just gotten my head around the concept of services in Drupal 8 and found a blur between what I envisioned to be a service vs what could be considered a plugin. Thankfully I was able to find some answers.

## Plugins vs Services

The best description I could find of a plugin with Drupal 8 was found in the Drupal.org Why Plugins? article. The author describes a plugin as something that would typically be exposed via a user interface which users can then configure, interact with, or select which implementation of functionality they desire. This contrasts a service which is 'intended to be something that modules do programmatically to other modules.' The Lullabot article, Creating a Custom Filter in Drupal 8 provides a nice analogy for a plugin manager to that that of an ice cream shop and the plugins themselves, ice cream, flavors, accounting systems for the business, etc.

If you're like me and are not as well versed in Drupal 7 module development, you might not have realized that the new Drupal 8 plugin system is essentially a replacement for hook\_info (a handy hook that allowed for organizing of other hooks as well as separating their logic out of the .module file which could become large and unmanageable for more sophisticated modules. In addition to the above, unlike services, plugins are setup to be 'discoverable' by Drupal via annotations. The Talking Drupal podcast illustrates this well in their Intermediate Module Development Concepts episode. When researching plugins, I found a really good video from DrupalCon Barcelona by Kris Vanderwater, who walks through setting up a basic example plugin called plugin\_message.

https://youtu.be/BVwi29Kpv8E

As of writing, in Drupal 8.2, there are currently sixteen plugin managers in Drupal 8, each of which are responsible for providing access to various plugins within their grouping that can be used and extended in your own Drupal project. You can also write your own plugin managers and plugins by extending DefaultPluginManager and Plugin respectively.

| plugin.manager.action | Drupal\\Core\\Action\\ActionManager |
| --- | --- |
| plugin.manager.archiver | Drupal\\Core\\Archiver\\ArchiverManager |
| plugin.manager.block | Drupal\\Core\\Block\\BlockManager |
| plugin.manager.condition | Drupal\\Core\\Condition\\ConditionManager |
| plugin.manager.display\_variant | Drupal\\Core\\Display\\VariantManager |
| plugin.manager.element\_info | Drupal\\Core\\Render\\ElementInfoManager |
| plugin.manager.entity\_reference\_selection | Drupal\\Core\\Entity\\EntityReferenceSelection\\SelectionPluginManager |
| plugin.manager.field.field\_type | Drupal\\Core\\Field\\FieldTypePluginManager |
| plugin.manager.field.formatter | Drupal\\Core\\Field\\FormatterPluginManager |
| plugin.manager.field.widget | Drupal\\Core\\Field\\WidgetPluginManager |
| plugin.manager.mail | Drupal\\Core\\Mail\\MailManager |
| plugin.manager.menu.contextual\_link | Drupal\\Core\\Menu\\ContextualLinkManager |
| plugin.manager.menu.link | Drupal\\Core\\Menu\\MenuLinkManager |
| plugin.manager.menu.local\_action | Drupal\\Core\\Menu\\LocalActionManager |
| plugin.manager.menu.local\_task | Drupal\\Core\\Menu\\LocalTaskManager |
| plugin.manager.queue\_worker | Drupal\\Core\\Queue\\QueueWorkerManager |

Source: core.services.yml
