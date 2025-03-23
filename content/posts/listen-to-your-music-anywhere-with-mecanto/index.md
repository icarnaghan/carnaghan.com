---
author: "Jake"
title: "Listen to Your Music Anywhere with MeCanto"
date: 2009-07-21
categories: 
  - "digital-media"
tags: 
  - "creative"
  - "music"
  - "web-20"
---

Being able to carry your music library on an iPod or MP3 player has revolutionized how we listen to music. It's allowed us to bring our favorite songs anywhere we go, keep us busy when waiting on appointments, and share some of our favorite music with friends. However, with MeCanto you can now bring your entire music library anywhere you can get an internet collection - that's practically anywhere!

<!--more-->

I got an interview with the creator of MeCanto, Yoav Steinberg. I got him to answer a few important questions about the MeCanto web application, how users can use their music library on-the-go, and where he plans to bring this application in the future. If you're a huge music fan, or just interested in the latest-and-greatest web 2.0 applications, be sure to check out Yoav's answers below!

#### What is the idea behind MeCanto and what does it allow users to do?

MeCanto allows users to store their entire music collection online and access it from anywhere. It also provides the tools to do this simply and easily without the hassle of long uploads, manual synchronization and changing old habits like sorting all your music in folders.

The idea behind MeCanto is to enable people to view and manage their personal content from anywhere. We believe that web services are often better than desktop applications and since everyone today manages their music collection on their computer we thought - why not manage your music collection on a web site dedicated for storing and organizing your music.

This concept brings lots of goodies with it:

- When all your music is stored online on MeCanto you can listen to it from anywhere, even your mobile phone.
- You don't need to sync your home and office computer, or your MP3 player anymore, since you always listen from your MeCanto account and everything is there.
- You have a single point where you organize your complete collection. For example if you create a new playlist or update a track's rating, it is immediately reflected everywhere.
- You don't have to worry about running out of storage place on your computer or mobile device - storage is much less limited online (if at all). You also get an automatic backup of your music so you’re much less likely to suffer data loss due to hardware failure or theft (although we don't guarantee this).

And we keep finding more benefits for using our online solution.

![MeCanto Home Page](images/mecanto-screenshot.jpg "MeCanto Screenshot - Home")

#### How many users are currently using MeCanto?

We’re currently in beta stage and starting a small promotional effort. We do not have many users at this point, a few thousand, and are hoping to increase this soon.

#### Are all of the music files uploaded and stored on your servers after members add their libraries to their profiles?

Yes, all the music is stored on our servers. This is part of our philosophy, to let our users mange their music collection from their online repository. Many of our users have quite large collection so uploading their complete collection takes some time. In the meantime they can access their music directly from their PC (as long as the client application is running on their computer) so the long upload time doesn’t really matter.

#### Which operating systems can access the MeCanto library (Mac, PC, Mobile)?

![Google Chrome Logo](images/google-chrome-icon.jpg "Google Chrome Compatible") The web application itself has been tested to work on all popular operating systems (Windows, Linux, Mac) and browsers (Firefox, Internet Explorer, Opera, Chrome).

The mobile application available today is for Symbian S60 phones. We also have an iPhone version that’s already tested and working and will hopefully be available soon. A Windows Mobile version is also in the works but will probably not be available in the near future.

The PC Client application which is used to upload your music and stream files that haven’t uploaded yet is designed for Windows XP and Vista. It is also known to work on Linux (under wine) and probably works fine under Windows 7. You can also use MeCanto without the PC Client using the manual upload feature where you manually select the files you want to upload to your account from within the web application. This way Mac users for example can upload music to their account.

#### Where did the name for the site come from?

This is a long and uninteresting story, so I won’t go into details. MeCanto is our second name and some early users might know us from the hyrax.fm service. Eventually we came up with this name because its connection to something personal "Me" and music "Canto" and the .com was free.

#### Can you share a bit about what it was like when first developing MeCanto? How did you get the idea, and were there any other sites you used as inspiration?

We came up with the idea while brainstorming about two years ago. Basically we thought of 2 points which led to the complete concept:

- Flickr for music – why do pictures deserve the benefits of being online while music files don't?
- We need a seamless way to transition from storing music on your PC to storing it on the web. How to overcome the long upload period.

Then we gradually updated our general design while working on other projects. Eventually we felt it’s time and started working on MeCanto. Timing had a lot to do with when mobile data plans were cheap enough to make such a service worthwhile for end users.

![Database](images/database.jpg "Database Development") We're still very much in the midst of our initial development. We’re a small team that’s trying to provide a valuable, reliable and scalable service. We started off reading about the architecture and development processes used by existing large scale web apps like Flickr, YouTube, Live Journal, MySpace. This was very helpful, especially in terms of how to approach scalability problems, and how to reduce h/w and s/w costs. It seems like there's a fine line between planning for scalability and wasting a lot of time with complex designs and bottleneck hypothesis.

We also found that working tightly with each other discussing our ideas together and managing a wiki for documenting development and ideas is very helpful, especially because we couldn’t afford a very hierarchical organization – everyone had lots of responsibility. As you can probably figure out our project touches many different fields: mobile, storage, servers, desktop apps, web development, databases… so even with all our experience, we’re all enjoying deepening our knowledge in these technologies as we go along.

I’d also like to mention that seeing the first users actually use our service and getting all the positive feedback is a great boost for us. I really speak for the entire team when I say that the more activity we see on our servers the more we get the drive to continue.

All in all it’s been really fun and educational so far.

#### How many people work for MeCanto?

We started out as 3, we’re up to 10 now :)

#### Do you have any updates or additions in the works that you can share with us?

I’ll list a few of the stuff that you can expect soon (don’t hold me liable if they take a bit more time)

![Twitter](images/twitter.jpg "Twitter Bird")

- Last.fm scobbling support
- Tweeting from the mobile app
- iPhone app, and an official Symbian S60 5th edition release
- MeCanto widgets for Netvibes and iGoogle.
- Good indication which files are unavailable if your PC Client application isn’t running and some of your music hasn’t uploaded yet. Also it’ll skip these tracks while trying to play them. You’ll also be able to see which of your computers is currently online/offline in case you have multiple PC's syncing your account.
- This might come a bit later, but it’s on its way: File metadata editing and file deleting from your account and many other organizational tools.

#### If you had any advice for someone starting their own web 2.0 application, what would it be?

I guess my advice is relevant to small teams working on something that needs to be scalable (like our project), and remember our site is still in its infancy.

If you read the previous question's answer, you can easily guess my advice: user Trac! Or something similar and utilize the hell out of the wiki. You can use it to document your ideas and requirements. You can use it to track your promotional efforts. To write down the protocols between components that are developed by different people. It’s alive unlike any other kind of document.

Worry about scalability to the point where you know that there’s a solution. Don’t develop it just because one day you’ll need it. Just make sure that your non scalable solution can one day be replaced. Don’t waste time on imaginary bottlenecks.

Use Linux. And if you do, work on Linux machines as your desktop computers. Don’t allow a windows/mac in site unless you **absolutely** need to (and using ms outlook doesn't qualify as "absolutely"). This way you (your team) get comfy with the platform that’s actually running on the servers and can easily debug, maintain and improve your deployment setup.

### Visit the Site!
