---
author: "icarnaghan"
title: "How to auto submit a Sitemap to Google using PHP"
date: 2018-03-22
---

This can be done via a ping service from Google Webmaster Tools

Add the following PHP function 

```
	function submitSitemap($site)
 
	    {
 
	        $url = 'http://www.google.com/webmasters/sitemaps/ping?sitemap='.htmlentities($site.'/sitemap.xml');
 
	        $response = file_get_contents($url);
 
	        
 
	        if($response){
 
	          echo $response;
 
	        }else{
 
	          echo "Failed to submit sitemap";
 
	        }
 
	    }
```

Now you need to call the above function as example below to submit your sitemap to Google.

```
submitSitemap('http://www.mysite.com'); //Replace http://www.mysite.com with your website
```

Once the sitemap has been submitted the following message will be returned

**Sitemap Notification Received

Your Sitemap has been successfully added to our list of Sitemaps to crawl. If this is the first time you are notifying Google about this Sitemap, please add it via http://www.google.com/webmasters/tools/ so you can track its status. Please note that we do not add all submitted URLs to our index, and we cannot make any predictions or guarantees about when or if they will appear.**
