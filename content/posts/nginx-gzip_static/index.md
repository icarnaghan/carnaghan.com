---
author: "prhost78"
title: "Nginx gzip_static: What it does and how to use it?"
date: 2017-12-18
categories: 
  - "coding"
tags: 
  - "affiliate"
  - "nginx"
---

![NGINX logo](images/NGINX-logo.jpg)

Like other top web servers, Nginx lets webmasters enable Gzip compression for their websites. It can compress scripts and stylesheets in a web page on the fly. The Gzip file's size is significantly lower than the original file. Nginx supports 9 Gzip compression levels.1 is the lowest and 9 is the highest. To gzip a file, Nginx will use invoke a function and the function will use system resources during the file conversion process. The function will take few milliseconds to execute.

#### What is the benefit of Gzipping scripts and stylesheets?

Gzipping content improves the performance of the website, but it increases the load on a web server. If you have got a popular site that receives tons of direct visitors, you can reduce the cost of hosting by compressing scripts.

As in real life, even a fraction of a second can make a huge difference on the Internet. According to renowned SEO experts, if e-commerce site's loading speed increases by a second, the customers will ditch the site or may not make any purchase. Google, the world's largest search engines consider page speed as one of its search engine ranking signals.

Gzip\_static is a module which makes Nginx serve precompressed GZIP files instead of compressing files on the fly. Along with the FastCGI cache, GS is one of the top features of Nginx.

### How to use Gzip static module?

**Step 1:**

Nginx will search for the Gzip files in the directory. If it doesn't find one, the web server will covert CSS/js files into Gzip. If you want to use the Gzip static module, the first thing you should do is create gzip versions of the static assets on your site (excluding images, and server-side code files). To do so, you can use the default Gzip tool in Linux OS i.e. Gunzip. For better compression and to save more bandwidth, you can use Google Brotli or Zopfli to generate Gzip files.

**Step2: (Very important)**

Make sure that Nginx has the permission to access the newly generated Gzip file. If you don't assign this permission to Nginx, won't send the Gzipped file to the client browser and search bots will report HTTP 500 error in the webmaster consoles.

Modify the below command's last 5 words as per your requirements, change the Nginx user and run the command

`chmod -R nginx_user:nginx_user directory path or file name`

**Step 3:**

Add the following file to the block in your website's Nginx configuration file where you've set expiry time for JS/CSS files

`gzip_static on;`

**Step 4:**

Restart the web server. That's it! To see whether Gzip\_static is working on your server or not, refer this answer on StackOverflow.
