---
author: "icarnaghan"
title: "Configuring your Local Drupal 8 Development Environment"
date: 2016-08-16
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

I have struggled with properly optimizing my local environment in terms of enabling debugging and disabling cache for a while. There isn't that many steps you need to cover in order to have a proper working development environment. After reviewing Day 10 I completed setting up my environment the correct way and have outlined this in the following sections.

## Step 1 Enable settings.local.php

- Copy and Rename /sites/settings.example.local.php -> /sites/default/settings.local.php
- Uncomment the following lines in your settings.php file:

```php
# if (file_exists(__DIR__ . '/settings.local.php')) {
#   include __DIR__ . '/settings.local.php';
# }
```

## Step 2 Disable Cache Services

- In your sites/default/settings.local.php file, uncomment the following:

```php
# $settings['cache']['bins']['render'] = 'cache.backend.null';
```

- Rebuild your site configuration by visiting yoursite.local/rebuild.php

## Step 3 Disable Twig Cache and Enable Debugging

- Add the following lines to your /sites/development-services.yml (Refer to /sites/default/default-services.yml for all options)

```php
parameters:
twig.config:
debug: true
auto_reload: true
cache: false
```

- Clear Cache and then verify Twig debugging has been enabled by refreshing your Drupal 8 homepage. Review your source code and you should see something similar to:

```php
<!-- THEME DEBUG -->;
<!-- THEME HOOK: 'html' -->;
<!-- FILE NAME SUGGESTIONS:
* html--front.html.twig
* html--.html.twig
x html.html.twig
-->;
```

Twig debugging gives a lot of helpful information scattered throughout your source code in the form of comments.
