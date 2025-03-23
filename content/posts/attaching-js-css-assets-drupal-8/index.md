---
author: "icarnaghan"
title: "Attaching JS and CSS Assets in Drupal 8"
date: 2016-08-15
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

Drupal 8 has introduced a different way of attaching JavaScript and CSS to themes and custom modules via a new concept called libraries, which are covered in Day 9. Libraries are essentially .yml files that define different groups of assets that can later be attached via module code. When I started working with the theme layer in Drupal 8, I quickly realized that certain things are very different from Drupal 7. One of the main gotchas for anyone new to Drupal 8 is the idea that JavaScript libraries are now only loaded where they are needed. In contrast to Drupal 7 where jQuery for example, was loaded on every page, in Drupal 8 jQuery is no longer automatically loaded. This provides for a better optimized site with only the required libraries included in areas that they are needed.

## Creating and Using a Library (day8.libraries.yml) File in Your Custom Module

A library can be easily defined by creating a .yml file. The example below illustrates creating a library file with two libraries for my main custom modules style and then a second library for the DataTables jQuery plugin. In my example I am also using a CDN for DataTables and you will note I added 'type: external' to indicate this. If you are packaging minified code you will also want to include 'minified: true'.

```php
module-styles:
version: 8.0.0
css:
base:
css/my-module.css: {}

data-tables:
css:
theme:
https://cdn.datatables.net/t/bs/jszip-2.5.0,pdfmake-0.1.18,dt-1.10.11,b-1.1.2,b-colvis-1.1.2,b-flash-1.1.2,b-html5-1.1.2,b-print-1.1.2,cr-1.3.1,fc-3.2.1,fh-3.1.1,kt-2.1.1,r-2.0.2,rr-1.1.1,sc-1.4.1,se-1.1.2/datatables.min.css: { type: external, minified: true }
js:
https://cdn.datatables.net/t/bs/jszip-2.5.0,pdfmake-0.1.18,dt-1.10.11,b-1.1.2,b-colvis-1.1.2,b-flash-1.1.2,b-html5-1.1.2,b-print-1.1.2,cr-1.3.1,fc-3.2.1,fh-3.1.1,kt-2.1.1,r-2.0.2,rr-1.1.1,sc-1.4.1,se-1.1.2/datatables.min.js: { type: external, minified: true }
js/datatables-config.js: {}
```

The nice thing about libraries is that once they are defined, it is very easy to use them anywhere on your site or specific places in your custom module. If you have a controller you can simply pass your library into your returning render array like so:

```yaml
'#attached' [
  'library' [
    'day9/module-styles', //include our custom module library for this response
    'day9/data-tables', //include data tables libraries with this response
  ]
]
```

## Selectively Applying a Library to Tables

Since our example uses DataTables, we might decide to only include the data\-tables library on pages that include an HTML table. This can be done using hook\_element\_info\_alter directly in our .module file, which allows us to selectively apply our data\-tables library!

```php
/**
* Implements hook_element_info_alter().
*/
function my_assets_element_info_alter(array &$types) {
    if (isset($types['table'])) {
        $types['table']['#attached']['library'][] = 'day9/data-tables';
    }
}
```

## Using Libraries in our Theme

If you want to include libraries in every page of your custom theme, this can also be accomplished by simply adding a theme.libraries.yml file in the root path of your theme. Anything defined in this file will be called on every page of your site that uses the theme. You can also attach specific libraries in twig using the syntax

```twig
{{ attach_library('fluffiness/cuddly-slider') }}
```

There is more information on libraries and theming in the Drupal.org articles Adding CSS and JS to a Drupal 8 Theme, Adding CSS and JS to a Drupal Module, and Best Practices for Handling External Libraries in Drupal 8.
