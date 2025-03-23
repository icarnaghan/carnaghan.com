---
author: "icarnaghan"
title: "Testing email in a local development environment"
date: 2014-03-20
categories: 
  - "coding"
---

Have you ever had a need to test email functionality on an application within your local development setup?  I have found this process to be both time consuming and confusing in the past, especially when working within firewall restrictions.  Of course we can always test with real dummy email addresses, but what if we accidently send a mass email out to real users?  It is much better to test everything locally first.<!--more-->

About a year and a half ago, I discovered a really valuable small application that has made my development life much easier.  The application is called smtp4dev and is available for free at Codeplex.

smtp4dev is a small Windows application that sits neatly in your taskbar.  It is designed to work with your localhost setup and sits quietly in the background until it receives mail.  It effectively acts like an Outlook notification when anything arrives, letting you see new messages easily.  You can even click on anything that arrives and have the message open in your default email client.

I have been using smtp4dev with several ASP.NET and Drupal projects since I discovered this valuable little app.  If you are interested in using this application, the download link is below.  Simply unarchive the zip file and place the exe into a directory in your Program Files folder, or anywhere you like.  Hopefully you will find this application as useful as I have!

**smtp4dev homepage at Codeplex**
