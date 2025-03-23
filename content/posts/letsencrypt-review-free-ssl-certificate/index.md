---
author: "prhost78"
title: "Letsencrypt review: Should you use free SSL certificate?"
date: 2017-03-19
categories: 
  - "coding"
tags: 
  - "affiliate"
  - "security"
---

After Google declared HTTPS as a ranking signal, thousands of sites have switched to HTTPS from HTTP. To secure your site with HTTPS, you must install an SSL certificate on the server and configure the web server to redirect HTTP traffic to HTTPS.

Before Let's Encrypt Certificate Authority was launched in 2016, companies used to charge a hefty amount for providing SSL certificates. Now, you can easily get free SSL certificates to secure your personal or business portal, thanks to Let's Encrypt.

I'm using the free Let's Encrypt SSL certificate on one of my sites. Here's my review of LE.

### Ease of installation

Most shared hosting providers allow webmasters to secure their sites with a single click.

If you're using unmanaged hosting service, you'll have to edit the webserver's configuration files and run few Unix commands to implement SSL certificate.

Fortunately, there are plenty of tutorials that provide a step-by-step guide to install LetsEncrypt on a VPS running Apache or Nginx.

Hence, I won't share a tutorial here. To install LetsEncrypt, follow tutorials published on DigitalOcean website.

If you're using a shared hosting service, you will find an option to enable LetsEncrypt in the Cpanel.

![https - Letsencrypt review free SSL certificate](images/https.jpg)

### Renewing SSL certificate

You can add a cronjob to renew LetsEncrypt certificate after 3 months. If you have a sharp memory, you must fire the command to renew LetsEncrypt on the 89th or 90th day.

### The difference between LetsEncrpyt and other SSL certificates.

The only difference between LetsEncrypt and paid SSL certificates is their price.

According to the Built With, LE certificate is used on over 3 million websites. Over 400 top 10K sites use LetsEncrpt SSL certificate.

When you install LetsEncrypt, you must generate a private key with Diffie-Hellman key exchange algorithm. Premium SSL providers also ask their customers to generate PK with the same algorithm with the OpenSSL tool.

You must also provide SSL ciphers. Most sites using SSL certificates use the cipher provided by Mozilla Corporation.

I'm not a security expert but I think, LetsEncrypt and other premium SSL certificates use the same encryption algorithms.

### Support

LetsEncrpyt has a great support team. They have a support forum where you can post your question or report any issues.

Folks working for LetsEncrypt or members of the forum reply to your queries within a couple of hours. They reply faster than the technical support executives of shared hosting firms.

They don't taunt you for lack of knowledge about SSL certificates. The team answers to questions posted by newbie and advanced users.

### Will Let's Encrypt SSL slow down your site?

No, if you enable HTTP2 or SPDY support for your site, the performance of your site will improve. HTTP2 is an enhanced version of HTTP. Google is the company behind the SPDY protocol. It improves the performance of websites.

**Conclusion**: If you want to secure your website with a free SSL, use Let's Encrypt. LE is easy to install. It is backed by several prominent organizations. If you face any problem while installing it, you can seek help from the Let's Encrypt team.

Image credits: Pixabay
