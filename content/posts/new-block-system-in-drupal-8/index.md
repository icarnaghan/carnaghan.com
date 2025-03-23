---
author: "icarnaghan"
title: "The New Block System in Drupal 8"
date: 2016-08-11
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

Among the many changes in Drupal 8, the blocks system received an overhaul, which has improved much of its functionality significantly. Some of the most notable take aways include the new block page layout and UI for updating, adding, and editing blocks, the addition of custom blocks and fieldable types (similar to content types), and integration with display view modes to allow for rendering changes based on block placement. Day 5 directs you to a good introductory video of the new blocks system by the Drupalize.me team.

https://www.youtube.com/embed/3Yc8WlibNEw

## Using the New Block System

Several exercises have been provided to help gain familiarity with the new block system. The first of which involves the creation of a new block type with various fields and then the creation of several blocks based on this type. I found the new block system relatively intuitive and easy to understand. While there are differences from the previous Drupal 7 block system, overall I found it pleasant to use and with the addition with block types that are fieldable, I can imagine several use cases I will have for this in the near future. One of the take aways I found in this exercise was the ability to now place different 'instances' of a block within different regions. In Drupal 7 you could only place a block in one place, however now a block is treated as an instance and can therefore be duplicated across different parts of your layout. I'm yet to find a valid use case for this, however it was an interesting change. With the integration of display view modes, each new block type created can be setup to have its own set of display modes. Once you create a block of that type, the user will have the ability to choose which display view mode to use for that block. The Drupalize.me video above demonstrates this well using a thumbnail image in one view mode and full image in the other.

## Blocks in Code

As with many other parts of Drupal 8, the block system is now part of the configuration management system. What this means is that whenever a block is created, corresponding configuration code will represent it in configuration management. If you export all of you configuration via the drupal console by issuing the command **drupal ce** (Content Export), all config files including individual yml files for your blocks will be exported. This gives you greater control in editing and crafting new blocks within custom modules.

In the exercise, part 2 requires the use of an external API to populate fields within the blocks created in part 1. The process involves writing a custom module that will run on cron and will retrieve the blocks, iterate through each instance, call the external API, and populate fields with information returned from the API call. After doing a little research, it appears there are two main ways you can use cron in Drupal 8. The first is by using the familiar hook\_cron function, and the other uses the Drupal 8 Queue API.  Using the hook system would involve writing module code directly in the .module file similar to the Drupal 7 way of writing modules. Queue API on the other hand uses the newer services oriented approach. I am not sure if the Queue API will eventually replace hook\_cron, however it seems to encapsulate all of its functionality and provides greater extensibility.

I was a little bit lost in trying to complete part two but I reviewed two good examples linked from d8cards.com, the first by neetuymorwani, who uses hook\_cron,  and the second by mirsoftacquia who uses the Queue API. The hook\_cron example used entityTypeManager to grab all of the blocks that needed populating by the service. Then Drupal::httpClient() was used to access the service along with Json::decode to parse the data correctly into the block fields. When I was reviewing this code I also came across a handy Content Entity / Entity Query cheatsheet. I found myself a little bit confused with the Queue API example, howewver I found a good tutorial at SitePoint which helped clarify some of this, Drupal 8 Queue API – Powerful Manual and Cron Queueing. The Queue API will also be covered in Day 7 of this series, so there will be more to come on that subject.
