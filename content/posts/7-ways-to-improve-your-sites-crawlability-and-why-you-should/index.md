---
author: "icarnaghan"
title: "7 Ways to Improve Your Site's Crawlability (And Why You Should)"
date: 2019-09-24
categories: 
  - "blogging"
  - "coding"
  - "digital-media"
  - "internet-marketing"
---

While keyword research, link\-building, content optimization, and other on-page strategies can improve your domain's search ranking, search engine optimization (SEO) starts with getting your pages indexed and to do that you need to ensure they're crawler\-friendly.

Crawler bots, like human users, appreciate sites which have clear, structured, readable data. However, since crawlers can only spend a limited amount of time and resources per site, domains with incoherent site maps, broken links, or 404 errors might not get indexed at all, effectively invisibilizing it for all potential users.

Want to know how to avoid indexation issues and increase your site's visibility? Follow the simple tips below to ensure your website is as robot-friendly as possible.

## **1\. Remove noindex tags**

Noindex tags are a helpful tool you can use to keep pages which are duplicated or should only be viewed by administrators or users doing certain actions, from popping up in search results. However, if you add these tags by mistake to a page, or later decided to make the page indexable but forgot to remove it, leaving them unchanged will make your page invisible for both crawler bots and users. You can find noindex meta tags in the <head> section of a page, and they'll look something like this:

```javascript
<meta name="robots" content="noindex">
```

To find, and change, all the pages with a noindex meta tag on your domain, you can use a site audit tool and run your own crawl to get an internal pages report. Then, all you'll need to do is click on the noindex page warnings and see which tags are warranted and which ones have to go.

## **2\. Enable crawling in your robots.txt file**

Before crawling your website, Google's bots will read your site's robots.txt file to learn how it's configured. If you've set up a clawl block in your robots.txt file, whether it's by chance or design, crawlers will simply skip your domain altogether without having indexed a single page in it. If you think this might be the issue, check your yourdomain.com/robots.txt and see if you can find this code:

```javascript
user-agent: Googlebot 
disallow: /
```

If the answer is yes, simply remove the crawl block snippet and save your changes. On the other hand, if only some pages are being blocked, you can use the URL inspection tool in Google's Search Console to see which pages are being blocked and then look for any disallow rules you might have missed in your robots.txt file.

## **3\. Delete rogue canonical tags**

Canonical tags are used to indicate the preferred version of a page. Although most pages don't use them, canonical tags are a useful way to ensure Google indexes the pages you want while also skipping duplicates and older versions. A typical canonical tag will look like this:

```javascript
<link rel="canonical" href="/page.html/">
```

Rogue canonical tags, on the other hand, refer to preferred versions of a page that don't exist and their existence can lead to Google indexing the wrong pages and leaving your preferred versions invisibilized. To prevent this from happening, you can use an URL inspection tool to scan your domain for rogue tags. If the crawler finds any misplaced canonical tags, it'll return a warning message with the page's URL so you can remove the tag and get the best version of the page indexed.

## **4\. Optimize your website for crawler experience**

Crawlers are extremely busy pieces of software. Each day, they have to go through thousands of websites to update their indexes, so they only have a limited amount of time and effort they can spend on each site, also known as "Crawler Budget." If your site is unoptimized and slow to craw, bots will have a hard time exploring it and will probably quit before all of your pages are indexed.

You can increase the likeliness of your pages getting indexed by increasing load times and removing, or keeping to a minimum, backend elements likely to slow down your indexed pages, such as JavaScript, Flash, and CSS. Alternatively, if these elements are indispensable for user experience, you can put them on separate pages and use noindex tags to keep them from eating up your crawl budget.

## **5\. Look for orphan pages**

Crawlers will skimp over orphan pages because they simply can't find them. Google bots find new pages by crawling through an existant path, not unlike a car uses roads to move from one area to another. However, since orphan pages don't have any internal links pointing at them, crawlers are unable to see or index them.

To find orphan pages in your website, use an audit tool to get a links report of every page on your domain. This will give you a full list of all the indexable pages in your sitemap and show you which ones have no internal links pointing at them. Then, you'll be able to fix these pages by adding relevant links from other pages in your website or, if the page is redundant, deleting it and then removing it from your sitemap.

## **6\. Upload your sitemap to Google Search Console**

Submitting your sitemap to Google Search Console is one of the best ways to improve your site's crawlability. If you've ever looked for a direction in an unfamiliar city, you know how hard it is to find a place without a map. The same principle applies to bots since they rely on sitemaps to find a route to each of your pages and decrease the time and effort it takes to crawl them.

To create an XML sitemap of your site, you'll need to use a sitemap generator or create it by manually tagging the preferred version of each page. This will ensure that Google indexes the pages that matter without expending any of your valuable crawler budget on duplicate content.

## **7\. Submit your domain's URLs to Google**

Although crawling is the most common way to index pages, there's no reason why you can't manually submit your URLs for indexation yourself. In fact, doing so could help you speed up the process and make your pages appear in search results sooner. So, if you're working on seasonal content and can't afford to miss a deadline, submitting your pages directly will help you save time and make the most out of your content while it's still fresh.

To submit new URLs to Google, simply sign up for Google Search Console and use the tools it provides to submit your content and monitor how it's doing in search results. However, before you do so, make sure the pages you're submitting comply with the standard Google guidelines for SEO and URL submission.

Good SEO starts with ensuring all of your searchable pages are indexed and crawler\-friendly. But unlike standard SEO, optimizing for crawler experience is an easy-to-do task. Just use meta tags carefully, decide which content you want to be indexed and which not, improve load times, don't overuse recourses like JavaScript or CSS, and you'll have a website that bots will love crawling and users will love visiting!
