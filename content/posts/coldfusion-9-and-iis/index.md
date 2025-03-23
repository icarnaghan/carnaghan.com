---
author: "icarnaghan"
title: "Coldfusion 9 and IIS"
date: 2011-03-01
categories: 
  - "coding"
  - "digital-media"
tags: 
  - "iis"
  - "programming"
---

I have been developing in ColdFusion for a while locally using the built in web server. Recently at work several of the projects I am involved with moved to an IIS production server. In order to test fully in my local environment I needed to install IIS and setup ColdFusion to use it as the server instead of its built in version. <!--more-->I ran into a few problems trying to figure this out so I decided to write a blog post of the process in case it is of help to others who need to do the same thing. I am including a set of steps below:

1. Download the latest version of IIS at http://www.iis.net/download
2. If you don’t already have ColdFusion installed, grab the latest version at http://www.adobe.com/products/coldfusion/
3. Be sure to also grab the latest CF patch, which fixes a number of different issues at: http://www.adobe.com/support/coldfusion/downloads\_updates.html#cf9
4. Install IIS. You can either use the recommended settings or the complete install. If you use the recommended settings be sure to install ISAPI extensions and the IIS Metabase detailed in this blog posting. If you don’t will get a page not found error when trying to access any cfm resource!
5. If you already have CF installed, run the Web Server Configuration Tool (this is located under the Adobe Coldfusion folder in the Windows Start menu). Next click ‘add’ in the server configuration prompt and then select IIS all sites or whatever additional configuration options you need. If the configuration tool fails, make sure you installed the ISAPI extensions and Metabase listed above.
6. If you are installing a fresh copy of ColdFusion, choose IIS server when the option choices are presented during the installation process.
7. At the end of the installation you should be able to access your administration area by browsing to http://localhost/cfide/administrator

If you are new to IIS as I was, you will want to figure out how to add your projects or sites. This can be done by running the IIS Services Manager (available under control panel -> administrative tools). Once loaded:

1. Expand the server tree on the right hand side to ‘sites’![](images/mysite-300x255.png "mysite")
2. Right-click sites and select ‘Add web site’
3. Type in a site name e.g. mysite
4. Select the physical path to your code base for this project / site
5. In the IP Assigned field type 127.0.0.1
6. In the hostname field type the hostname you would like to access e.g. mysite
7. Using a text editor (e.g. notepad++) open c:windowssystem32driversetchosts and enter the following line at the bottom of the file: 127.0.0.1 mysite

That’s it – now if you go to your browser you should be able to open http://mysite/. You may need to set up a few other things such as data sources, etc. but this should essentially get you up and running.
