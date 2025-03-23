---
author: "icarnaghan"
title: "Cron Queuing in Drupal 8"
date: 2016-08-13
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

Day 7 focuses mainly on the Drupal Queue API. The main resource for this card is an article called Drupal 8 Queue API – Powerful Manual and Cron Queueing, which I had referenced in an earlier post. Before completing any of the materials, I had no previous experience with the Queue API, nor hook\_entity\_insert, which was used to create a demo queue system in the referenced article. After going through the article I gained a better understanding of how the queue system works. At a high level the following steps outline the process of constructing the module that is documented in this article along with relevant links to the API.

## Creating the Queue

1. Create the .module file and use hook\_entity\_insert to grab any newly inserted entities of type node, check publish status, and if unpublished create a queue via the QueueFactory (step).
2. Get the queue factory service via \\Drupal::service('queue') which references the QueueFactory class and then use the get method to create a new queue of type QueueInterface.
3. Instantiate a new class stdclass() called $item and pass in the nid from the inserted entity.
4. Use the QueueInterface createItem method to pass in $item.

## Building the QueueWorker Plugin

We will be getting more into plugins in Day 8, however for the purpose of using the Queue API in this example, a plugin was created to manage publishing of and processing items in the queue.

1. Create the plugin at src/Plugin/QueueWorker which extends QueueWorkerBase and implements the ContainerFactoryPluginInterface.
2. Inject EntityStorageInterface into the plugin (required for publishing nodes).
3. Write the methods for processing queue items and publishing nodes.

The Drupal 8 Queue API article setup the plugin as an abstract class and extended it to provide both cron as well as manual calls to the plugin. An additional form was buit to provide user feedback on queue items left and for a way for the user to manually process the queue. The article also provides a git repo of all sourcecode to download and test locally.

## Registered Users Welcome Email Queue

The task for Day 7 was to build a custom module that would similarly use a queue within Drupal 8, only this time instead of queueing inserted nodes, the module would build a queue of new users and then email a welcome message on the next cron run. In order to write this module, I followed similar steps to the article above. First of all I found myself reviewing Drupal 8 Hooks in order to find a registered user hook that I could use for my queue. I quickly realized that no such hook existed and I could in fact use the same hook\_entity\_insert on users instead of nodes.

The next thing I needed to figure out was which service I could use for processing emails. I took a look in core.services.yml and came across MailManager which provides a Mail plugin manager. More detailed documentation for the MailManager function is available and this helped figure out how to use it correctly in my code including what parameters needed to be passed in:

- **string $module**: A module name to invoke hook\_mail() on.
- **string $key**: A key to identify the email sent.
- **string $to**: The email address or addresses where the message will be sent to.
- **string $langcode**: Language code to use to compose the email.
- **array $params**: (optional) Parameters to build the email.
- **string|null $reply**: Optional email address to be used to answer.
- **bool $send**: If TRUE, call an implementation of \\Drupal\\Core\\Mail\\MailInterface->mail() to deliver the message.

One thing I noticed was that the options to pass into $params were not on this page, nor could I find documentation for this. I did however come across a very helpful article by Danny Sipos called Using and Extending the Drupal 8 Mail API. This article has everything you need to know on this subject and helped me figure out that I could use $params\['message'\] and $params\['subject'\] for my email. Below is my 'draft' code for the day7 module as there are some improvements that could be made including additional code to test if the email was sent and logging.

day7.info.yml

```php
name: Day 7 Cron Email
type: module
description: Sends welcome email to registered users
package: Custom
core: 8.x
```

day7.module

```php
<?php

use Drupal\Core\Entity\EntityInterface;
use Drupal\Core\Queue\QueueFactory;
use Drupal\Core\Queue\QueueInterface;

/**
* Implements hook_entity_insert().
* @param EntityInterface $entity
*/
function day7_entity_insert(EntityInterface $entity) {
if ($entity->getEntityTypeId() !== 'user') {
return;
}

/** @var QueueFactory $queue_factory */
$queue_factory = \Drupal::service('queue');
/** @var QueueInterface $queue */
$queue = $queue_factory->get('user_mailer');
$item = new \stdClass();
$item->nid = $entity->id();
$queue->createItem($item);
}
```

Plugin/QueueWorker/UserMailer.php

```php
<php

/**
* @file
* Contains Drupal\npq\Plugin\QueueWorker\NodePublishBase.php
*/

namespace Drupal\day7\Plugin\QueueWorker;

use Drupal\Core\Entity\EntityStorageInterface;
use Drupal\Core\Mail\MailManagerInterface;
use Drupal\Core\Plugin\ContainerFactoryPluginInterface;
use Drupal\Core\Queue\QueueWorkerBase;
use Drupal\node\NodeInterface;
use Symfony\Component\DependencyInjection\ContainerInterface;

/**
* User mailer to send a welcome email to new user.
*
* @QueueWorker(
*   id = "cron_user_mailer",
*   title = @Translation("Cron User Mailer"),
*   cron = {"time" = 10}
* )
*/
abstract class UserMailer extends QueueWorkerBase implements ContainerFactoryPluginInterface {

/**
* The node storage.
*
* @var \Drupal\Core\Entity\EntityStorageInterface
*/
protected $userStorage;

/**
* The mail manager.
*
* @var \Drupal\Core\Mail\MailManagerInterface
*/
protected $mailManager;

/**
* Creates a new UserMailer.
*
* @param \Drupal\Core\Entity\EntityStorageInterface $user_storage
*   The user storage.
* @param \Drupal\Core\Mail\MailManagerInterface $mail_manager
*   The mail manager.
*
*
*
*/
public function __construct(EntityStorageInterface $user_storage, MailManagerInterface $mail_manager) {
$this->userStorage = $user_storage;
$this->mailManager = $mail_manager;
}

/**
* {@inheritdoc}
*/
public static function create(ContainerInterface $container, array $configuration, $plugin_id, $plugin_definition) {
return new static(
$container->get('entity.manager')->getStorage('user'),
$container->get('plugin.manager.mail')
);
}

/**
* {@inheritdoc}
*/
protected function sendEmail($data) {
$user = $this->userStorage->load($data->nid);

$module = 'Day7';
$key = 'cron_email',
$to = $user->getEmail();
$langcode = $user->getPreferredLangcode();
$params['subject'] = 'Welcome to our site';
$params['message'] = 'Thank you for registering at our site';
$send = true;

// TODO: Add Logging in Real Implementations
$this->mailManager->mail($module, $key, $to, $langcode, $params, NULL, $send);
}
}
```
