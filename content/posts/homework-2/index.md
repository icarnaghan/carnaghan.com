---
author: "icarnaghan"
title: "More PHP String Functions"
date: 2012-06-17
categories: 
  - "coding"
tags: 
  - "developing-with-php"
---

This week I rewrote one of the PHP tasks from earlier and created a new function to emulate the functionality of str\_pad.  The function I wrote accepts a text string parameter, length, a reverse parameter (for padding on left or right) and finally an optional symbol parameter to show where the padding is happening.  In addition to this I have outlined what I am planning on developing for a Drupal module later in the semester.

<!--more-->

#### Padding Function

The padding code I created is listed below.  This code can be run by accessing the following URL: http://www.carnaghan.net/padding.php.

```markup
<html doctype=”html”>
  <head>
    <title>My String Padding Script</title>
  </head>
  <body>
    <h1>String Padding Example</h1>
    <?php
      function padding ($padding_text, $padding_length, $reverse_padding, $padding_symbol=" ") {
        for ( $index = 1; $index <= $padding_length; $index++ ) {
          if ( $reverse_padding == 0 ) {
            $padding_text = $padding_text . $padding_symbol;
          }
          else {
            $padding_text = $padding_symbol . $padding_text;
          }
        }
        return $padding_text;
      }
      $text_example = "This is text that is being padded";
      $padded_right = padding($text_example, 10, 0, ".");
      $padded_left = padding($text_example, 20, 1, ".");
      echo "<p><strong>Original text:</strong> $text_example</p>";
      echo "<p><strong>Padded 10 on right:</strong> $padded_right</p>";
      echo "<p><strong>Padded 20 on left:</strong> $padded_left</p>";
    ?>
  </body>
</html>
```

#### **Drupal Module for Development**

I spent much of the past week reading up on writing modules for Drupal.  Much of what I covered included information on hook functions and how to tie into these hooks in Drupal core to use them for a module.  The reading started with a basic module and went on to explain the power behind module\_invoke functions.  Later I learned about the hook\_menu hook (used for creating new pages / content via modules).  I found some of the concepts tricky and I was able to locate additional resources at http://www.buildamodule.com to help with understanding some of the concepts of module building.

**Doctoral Project**

Initially when I enrolled in this class I envisioned creating a Drupal site or custom modules for an online resource aimed at online adjunct instructors (who are often isolated from the main campus and resources).  One of the challenges online faculty face is the learning curve (and time commitment) associated with tools to make effective and interesting interactive learning materials.  A few years ago a colleague of mine and I created a basic decision-point simulation.  It was originally intended as a prototype model to eventually be rolled out as an interactive 'case study' for various disciplined at UMUC.  The original simulation can be seen here: http://www.carnaghan.net/slr.  The problem with this prototype, which was created in Flash, is that there was no easy way to 'customize' it for faculty needs.  A Flash programmer was required and additional sound and audio tools were needed to develop this simulation.  Furthermore later iterations were to include video and other effects which would have required a greater learning curve.  For my doctoral project I hope to build an online resource or set of tools that will enable online faculty to 'rapidly' develop such simulations and learning resources for deployment via their Learning Management System with a much smaller learning curve.  My idea is to create a tool that is as easy for faculty to use as commonweb media tools such as YouTube, Vimeo and Prezi are for every day people.  The use of technology and creation of interactive learning should not be left to the Flash programmers, media professionals and web experts, the technology should be within reach of everyday faculty as it is in so many other ways we use the web.

**Proposed Project for this Class**

I am proposing to build a basic decision point / tree system for Drupal aimed at creating text-based decision simulations.  My hope is this will be the starting point for a much bigger project in the future that will include other resources to help faculty create similar learning resources with additional media types (including embedding Youtube, a library of royalty-free sounds and a framework of toolsets).  I have researched decision trees with Drupal and came across an older module developed for Drupal 6: http://drupal.org/project/decision\_tree.  This is a more general use module and used the ID3 algorithm.  I am proposing a more basic approach with an educational focus in mind and an emphasis on ease of use.  The tool should allow a faculty member to draft their decision points and link them accordingly to create the final learning resource (which would eventually be embedded in their classrooms directly).  My next steps are to learn more about the module building process and re-read the materials from this past week along with other Drupal resources.  I will publish an initial skeleton sketch of the module structure and provide a basic .info file for the proposed project.
