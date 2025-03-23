---
author: "icarnaghan"
title: "CMST 385 Software Setup and Webpage Publishing"
date: 2015-05-25
categories: 
  - "coding"
tags: 
  - "cmst-385"
---

## Software Setup

For this class you will require three main applications, a text editor, an SSH client and an FTP client. A text editor will be used to write your HTML documents. SSH (Secure SHell) is a text based application which will enable you to setup your Nova web server account, which we will be using to host your web pages online. Finally an FTP (File Transfer Protocol) client will be needed to actually copy over or upload your files to Nova from your PC or Mac. I am recommending your install Atom for text editing, FileZilla for FTP, and PuTTY SSH client for Windows users.

For you're convenience I have created a video below demonstrating downloading and installation of these applications on PC and Mac computers.

<iframe src="https://player.vimeo.com/video/130000137" width="800" height="450" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

Download links are provided below.

- **Atom** - Text Editor for Mac and Windows
- **FileZilla** \- File Transfer Protocol Client for Mac and Windows
- **PuTTY** \- SSH Client for Windows Only **(Mac Users do not need PuTTY)**

The above applications are free. If you run into any problems with installation, please let me know.

## Writing your First HTML page

Your first HTML page will include a splash page, or introductory place-holder to publish on Nova, while you develop your web site.  This page will include a draft outline of preliminary ideas for your web project including, site purpose, site audience, general outline of proposed content and at lease one mentioned resource you will include as a link in your final project.  This is just draft / idea information, so don't get too concerned if you do not have a project idea yet.

I have created a video below outlining the following steps for creating your first web page:

1. Open Atom, select File -> Open Folder
2. Create a CMST385 directory in your **Documents** location on your computer
3. Inside CMST385, create a **www** directory which will mirror the www directory on Nova
4. In Atom create a new file and save it as index.html inside your newly created www directory
5. Copy and paste the Project Template code below into your file.

This video provides directions for both PC and Mac users:

<iframe src="https://player.vimeo.com/video/130000001" width="800" height="450" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

I have created a template below to help you create index.html.  You should by now be familiar with this basic html layout from reading along in your text book.  Try to fill out the site purpose, target audience, outline and resources sections as much as you can.

**Project Template Code**

```
<html>
   <head>
     <title>My Project Website Title</title>
   </head>
   <body>
     <h1>My Project Website Name</h1>
     <h2>CMST 385</h2>
     <p>Welcome to my project website! This site will launch later this semester. In the meanwhile,  please find the information below detailing the content and structure of this site.</p>
     <p>Site Purpose: </p>
     <p>Site target audience: </p>
     <p>General site outline of proposed content: </p>
     <p>Names of links and resources: </p>
     <p><em>Name and E-mail address</em></p>
   </body>
</html>
```

## Publishing via FTP

So far you’ve used SSH to connect to Nova. You’ve created your account. You’ve created a location for publishing your webpages and you’ve set permissions for both your root (.) and (www) folders. Now you’ll be using another internet tool called FTP (File Transfer Protocol). More importantly, you will be using a connection called SFTP (Secure FTP).  This is used to transfer files from your computer’s hard drive into your www folder on Nova. When you create a website, you can view it from your hard drive. But nobody else can see it until you place it in your www folder on Nova. Sometimes this transfer is referred to as “uploading.”

_Please read the background information on FTP in the Commentary section of Module 2._

_The video above demonstrates uploading index.html using FileZilla, however I have also included the steps below for your convenience:_

**Uploading web pages to Nova**

You will need the following information for any FTP client in order to successfully upload your html pages to Nova:

1. FTP Server Address: nova.umuc.edu
2. Nova Username: ct385c## (replace ## with your account number)
3. Nova Password

**Follow the steps below to upload your file to Nova:**

- Open your FTP client and create a new connection
- Select **SFTP** Connection (Important, otherwise your connection will fail)
- Connect to your Nova account
- Locate your local files
- Locate your remote www directory
- Upload your local file(s) to your www directory (drag and drop or click the upload button)

Note: When connecting to Nova, you will need to use SFTP or your connection will fail.
