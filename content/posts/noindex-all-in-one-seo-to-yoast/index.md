---
author: "prhost78"
title: "Bulk move noindexed posts from All in One SEO to Yoast"
date: 2017-08-09
categories: 
  - "cms"
tags: 
  - "affiliate"
  - "database"
  - "wordpress"
  - "wordpress-plugins"
---

The Yoast SEO plugin includes an option to import meta description and title tags from other popular plugins. While using other plugins, you may have noindexed or nofollowed some or several posts. There are a couple of plugins that enable you to move settings from AIOSEO to Yoast. Unfortunately, none of the plugins provide an option to bulk move noindex posts. People noindex posts to recover from Google quality updates or prevent penalty during an algorithm update.

If these posts are thin, Google may index the posts and your site may suffer a Google Panda penalty. To avoid the penalty, you don’t have to edit the posts one by one to enable the no-index option. Follow the below instructions:

### Bulk noindex WordPress posts

The AIOSEO plugin saves SEO settings for individual posts in the post meta database table. This table has the following columns.

1. meta\_id.
2. post\_id.
3. meta\_key.
4. meta\_value.

When you noindex a post, the AIOSEO inserts the following row in the post meta table.

1. meta\_id: a unique value
2. post\_id: The ID of the post marked as noindex.
3. meta\_key: \_aioseop\_noindex
4. meta\_value: on

Note: Before proceeding forward, backup your database.

When you disable and remove AIOSEO plugin from your site, records of the above type are not removed. Likewise, when you install and activate Yoast plugin, the above records are not updated. If the plugin updates the records, the post meta table will have the \_yoast\_wpseo\_meta-robots-noindex records instead of \_aioseop\_noindex. The meta value for the noindexed posts will be "1" instead of "on".

![All In One SEO bulk noindex transfer Yoast](images/All-In-One-SEO.jpg)

To avoid the headache of manually noindexing posts, you can update the records with the meta\_key \_aioseop\_noindex by firing the following two queries:

`update wp_postmeta set meta_value = "1" where meta_key=" _aioseop_noindex";`

`update wp_postmeta set meta_value = "_yoast_wpseo_meta-robots-noindex" where meta_key=" _aioseop_noindex";`

Note: If you've set a DB table prefix in the wp-config file, replace wp with the table prefix in the above queries with the one you've mentioned in the WordPress configuration file.

You can modify the above queries to nofollow posts in a bulk.

**Conclusion**: The noindex meta robots tag can remove your site from Google Penalty. If you've used AIOSEO plugin to no-index posts and want to migrate from AIOSEO to Yoast, enable maintenance mode on your site. Open PHPMyAdmin or terminal/putty, log in to MySQL server, backup your DB, select the database table of your site and fire the above two queries.
