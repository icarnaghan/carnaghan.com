---
author: "icarnaghan"
title: "Dependency Injection Service Container Example"
date: 2016-08-22
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

In an earlier post, I outlined the basics of dependency injection and talked a little bit about the Drupal 8 service container and how we can use this in our code. Day 16 of Drupal Activity Cards provides a task for us to implement dependency injection in one of the Drupal 8 Example modules.

The examples module is a great resource for developers getting started in Drupal coding. The modules included gives us basic functionality that provides easy to follow starting points for a number of different needs. For our dependency injection example we are going to look at page\_example, a simple module for generating a Drupal 8 page via a controller. A function called simple() returns a basic page. We are going to extend this function to provide a log entry every time a use visits this page.

```php
public function simple() {
    Drupal::logger('page_example_module')->notice('Simple Page was displayed');
    return array(
        '#markup' => '<p>' . $this->t('Simple page: The quick brown fox jumps over the lazy dog.') . '</p>',
    );
}
```

This can be tested by visiting the examples/page\-example/simple page and then reviewing your recent log messages. Now that we have logging working with this simple page method, it is time to look at how we can improve this implementation. By calling Drupal::logger, we are essentially using a procedural call to the service logger from our controller. This can be improved by using dependency injection and having our logger.factory provided to us instead.

```php
class PageExampleController extends ControllerBase {

private $logger;

public function __construct(LoggerChannelFactory $logger) {
    $this->logger = $logger;
}

public static function create(ContainerInterface $container) {
    return new static ($container->get('logger.factory'));
}
```

The first thing we are doing in this code is setting a private variable called $logger, which will house our logger factory. The create function is being overridden from ControllerBase, which allows us access to ContainerInterface. ContainerInterface in turn gives us access to all services available within Drupal 8. For a list of services, take a look at core.services.yml. We are interested in logger.factory which we call in our create method via the container. Now that we access to logger.factory we can define a new instance and pass it to our $logger private variable, which we do in the constructor.

So whats the point of doing all this? We now have a controller that is getting an instance of logger.factory passed into it via its constructor, in contrast of the controller looking for / requesting a service directly. We no longer depend on Drupal::logger. Instead we now have a $logger instance injected into our controller, which can represent logger.factory or any other interface we care to use. For the purpose of unit testing we could for example mock up a dummy logger method so we are not depending on having the actual logger.factory available to us at time of testing.

At this point we are ready to update our simple() method by using our new $logger with the get method from logger factory.

```php
public function simple() {
    $this->logger->get('page_example_module')->notice('Simple Page was displayed');
    return array(
    '#markup' => '<p>' . $this->t('Simple page: The quick brown fox jumps over the lazy dog.') . '</p>',
    );
}
```

After updating our code we can then test by visiting our reports again. This provides a basic example of dependency injection in Drupal 8, however for more information on the new service container, be sure to check out Service Container for Drupal Geeks and the other resources posted at Drupal Activity Cards Day 16.
