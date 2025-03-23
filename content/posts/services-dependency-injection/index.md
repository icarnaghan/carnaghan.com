---
author: "icarnaghan"
title: "Services and Dependency Injection"
date: 2016-08-12
categories: 
  - "coding"
  - "cms"
tags: 
  - "drupal"
---

For several years I have worked as an ASP.NET MVC developer and have become intimately familiar with terms such as services and dependency injection and services. It is refreshing to see some of these familiar concepts surfacing in Drupal 8. Day 6 focuses mainly on introducing us to services and dependency injection via several online resources. There is no exercises or tasks in this card as the aim is to simply gain an understanding of some of these concepts. I saw a lot of overlap in terms of syntax and how dependency injection is handled in Drupal 8 compared with Unity and StuctureMap in ASP.NET, so anyone from background or other traditional object oriented languages such as Java will be familiar with a lot of this. I have outlined the main takeaways I got from the Day 6 below.

## Services

A service is simply an object that does something. This could include anything from a mail handler or logger to functionality that performs calculations and processes user input. The take away here however is that not all objects are services. In ASP.NET MVC examples of objects that would not be considered services could be domain objects or anything that contains properties only representing database entities. In Drupal 8 nodes would be a similar example of an object that would not be considered a service.

## Drupal 8 Service Container

A service container (sometimes referred to as a dependency injection container) is simply another type of object that contains references to all services available within a system. In Drupal 8 the service container is simply a class containing an associative array of all service references. The container is responsible for fetching the needed service once requested. In Drupal 8 core, all services are defined in the CoreServiceProvider.php and core.services.yml files. If you have Drupal Console installed you can retrieve a list of all services by issuing the command:

```php
drupal container:debug
```

This will give you a list of all core services registered within Drupal as well as any other services you may have added via contrib or custom modules.

## Dependency Injection

So services are basically objects that perform operations in our application and the service container houses references to all available services to us. Dependency injection is simply a method of providing these services to our class or controller which can then use them to perform the various operations desired. Why would we want to do this however instead of just calling what we need directly in our controller or code? This can be answered in the following example.

### Instantiating an object or service vs being provided with a service

Traditionally in object oriented programming we would simply instantiate an object or service needed in our code any time we needed to use it. In order to use an email configuration service that would return email server settings, we might do the following in our controller:

```php
public function EmailSettings() {
    $emailConfigService = new EmailConfigService();
    return new Response($settings);
}
```

In the above example we are simply instantiating the EmailConfigService service into a newly defined local variable called emailConfigService. We can then use $emailConfigService in our code to return the email configuration settings needed. The problem with this approach is that our code now 'depends' on EmailConfigService() being available at time of execution. We have created this inherent dependency that needs to be resolved any time we call our controller, in other words we have tightly coupled our code.

Dependency injection allows us to supply services or objects to our classes or controllers via a process called constuctor injection. An example of this might look something like:

```php
class MyController extends ControllerBase {

    private $ emailConfigService;

    public function __construct(EmailConfigService $emailConfigService) {
        $this->emailConfigService = $emailConfigService;
    }
...
```

In the above example we are setting a private variable called emailConfigService and next we are accepting an instance of EmailConfigService in our constructor. At this point we simply set our private variable to the service that was passed in or 'injected' into our controller. Other code would have to be setup to let the application know that it must pass in an instance of EmailConfigService and the service container would handle the reference to this.

Our EmailSettings function then might look like the following:

```php
public function EmailSettings() {
    $emailSettings = $this->emailConfigService&gt;GetSettings;
    return new Response($settings);
}
```

The nice thing about this approach is that we don't have to worry about the implementation of EmailConfigService. Dependency injection supplies this to us instead of us requesting it via instantiation. If at a later stage in our development we decide to switch out the functionality behind EmailConfigService, this can be done without effecting our controller. In addition to this if we want to introduce unit testing we can simply mock up a test version of EmailConfigService and use that for testing purposes so we don't get caught up in depending on real services needed in our code.

## Drupal 8 Dependency Injection

The article provided in Day 6 titled Drupal 8 Services, Dependency Injection, and Decoupling Your Code, provides a thorough overview of how dependency injection can be setup in a custom Drupal 8 module with your own service. There are three key steps this article points out:

1. Create your service.yml file - in the article nettv.services.yml is given, which defines the class that provides this service.
2. Create the service itself - e.g. src/servicename.php, which will contain all the operations / functionality needed
3. Inject the service into your controller, form, block, etc. using constructor injection

Instead of creating a controller and page, the article instead has you creating a block in code, which I was not familiar with. I found more information on blocks on the Block API documentation and also came across a simpler example in How to Create a Custom Block Programmatically which helped me understand how blocks are constructed in a custom module.

One last note: Day 6 provided links to Drupalize.me content which I was unable to access as I am not a member there. Thankfully someone posted a link to Knp University's Drupal 8: Under the Hood, that also provides the transcripts of these lessons for free of charge. The dino\_roar example exercises here were tremendously helpful in solidifying many of the concepts covered in the card and I highly recommend giving them a look. Finally, for even more clarification on dependency injection in Drupal 8, be sure to read Drupal 8 Dependency Injection, Service Container And All That Jazz.
