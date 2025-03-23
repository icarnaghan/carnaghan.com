---
author: "icarnaghan"
title: "Drupal 8 Migration"
date: 2016-08-11
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

I have had some exposure to the migrate module in the past, mostly with Drupal 7 and more recently for a Drupal 8 migration project that required importing of a small (under 1000) set of records stored in a CSV file. Todays D8Card focuses on the new migration module that comes partly with core and also partly in the form of contributed modules.

## Migrate Core & Migrate Contrib

The purpose of todays set of tasks was to import a couple of small CSV files using migrate and some of the contributed modules. I started out by reviewing the links posted in the card and then proceeded to download and install migrate\_tools, migrate\_plus, and migrate\_source\_csv. What comes with Drupal 8 core out of the box is pretty limited and only contains migration functionality for moving content from previous Drupal sites. It definitely makes the upgrade process less painful, however if you want to get into migration code that can manage a multitude of external sources, then you will want to grab to contrib modules above.

Migrate tools provides you with the familiar drush commands from the Drupal 7 module including migrate-import, migrate-status, migrate-rollback, etc. Migrate plus provides extended functionality including grouping capabilities for your migrations and extended prepare row functionality. Another nice addition to migrate plus is the extensive set of examples provided. Drupal 7 migration users will recognize right away the beer and wine migrations now with updated code for the newer Drupal 8 migration system.

## Drupal 8 Configuration System and Migrate

One of the first issues I ran into when I started working with the Drupal 8 migrate module was getting my head around how Drupal stores the actual migration code inside its configuration management system. In the past if I wrote  a migration and needed to change an error, I could have simply ran a drush migrate-rollback, edited my migration code, and then run a fresh drush migrate-import. Because Drupal 8 now stored migration code in its configuration system, all of this now sits in the database and must be accessed via the configuration management system. I briefly covered some Drupal configuration on day 1, however after learning a little more about how a lot of this works, I discovered much control and management can be had via the Drupal Console. Without getting too much into the weeds of configuration management (after all the purpose of this post is migration), I discovered quickly in order to edit an existing migration, it is necessary to delete its configuration. Because of the way you typically write a migration where the actual migrate code is placed in a config/install yml file, this gets placed into the configuration system at the time of installing the module. In order to ever make changes to this, you can either export the configuration, edit the file and re-import, or you can simply use Drupal Console to delete the config, uninstall your module and then re-install. There is probably a better way to do this, which I will no doubt discover over time, but at least for now here is how I managed a change to my migration yml code:

Step 1 - Rollback any migrations you may have started importing

Step 2 - Uninstall your custom module containing the migration

Step 3 - Deregister / delete the configuration by issuing the following command (provided Drupal Console is installed in your environment)

```php
drupal config:delete active
```

Step 4 - Reinstall your custom module - your config/install yml files will run and configurations will be recreated

## Movie and Actors Migration

Day 4 provided two main csv files for actors and movies. The purpose of the exercise was to create new content types to house this data and then create a migration that would pull the data into your Drupal 8 instance. I began by creating a day4 custom module with two install/config yml files to handle both movies and actors. I ran into trouble figuring out how to import a string of values from one cell in a csv file (multiple actors and genres per movie), however I came across the explode plugin which supposedly makes tasks like this easier for splitting values out in a migration. I ended up referring to one of the posted solution links on d8cards - shahinam's git repo for additional help in crafting my module. Unfortunately while I was able to bring in all actors, my migration failed to import movies (which I believe is probably down to the way I was using explode coupled with my entity reference field). I was able to migrate movies and actors individually (excluding the entity reference fields), however I would like to have been able to migrate relationships. My code is below and I will come back to this at a later time once I have more time to play with it. In the meanwhile, my work-in-progress migration module code is provided below.

day4/day4.info.yml

```yaml
name: Day 4 Migration
type: module
description: 'Creates a migration from CSV'
package: Custom
core: 8.x
dependencies:
- migrate
- migrate_plus
- migrate_source_csv
```

day4/config/install/migrate\_plus.migration.actors.yml

```yaml
# The source data is in CSV files, so we use the 'csv' source plugin.
id: movies_csv
label: CSV file migration
migration_tags:
- CSV
migration_group: movies
source:
plugin: csv
path: public://csv/movies.csv
# The number of rows at the beginning which are not data.
header_row_count: 1
keys:
- id
column_names:
0:
id: ID
1:
title: Title
2:
plot: Plot
3:
actors: Actors
4:
genre: Genre

destination:
# We are migrating into nodes (Content type - Movies)
plugin: entity:node
process:
# The content (node) type we are creating is 'Movies'.
type:
plugin: default_value
default_value: movies
title: title
field_plot: plot

# Here we are using the explode plugin to migrate multiple values in one field to another content type
field_actors:
-
plugin: explode
source: actors
delimiter: ','
-
plugin: migration
migration: actors_csv
field_genre:
-
plugin: explode
source: genre
delimiter: '|'

migration_dependencies:
required:
- actors_csv
```

day4/config/install/migrate\_plus.migration.actors.yml

```yaml
[code]# The source data is in CSV files, so we use the 'csv' source plugin.
id: actors_csv
label: CSV file migration
migration_tags:
- CSV
migration_group: movies
source:
plugin: csv
path: public://csv/actors.csv
# The number of rows at the beginning which are not data.
header_row_count: 1
keys:
- id
column_names:
0:
id: ID
1:
title: Title

destination:
# We are migrating into nodes (Content type - Actors)
plugin: entity:node
process:
# The content (node) type we are creating is 'Actors'.
type:
plugin: default_value
default_value: actors
title: title[/code]
```
