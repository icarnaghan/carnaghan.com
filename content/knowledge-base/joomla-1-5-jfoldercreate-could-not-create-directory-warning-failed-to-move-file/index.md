---
author: "icarnaghan"
title: "Joomla! 1.5 - JFolder::create: Could not create directory Warning! Failed to move file"
date: 2018-04-06
---

When trying to install a new **Component**, **Module**, **Template** or **Plugin** using **Joomla! 1.5** I receive the following error

**JFolder::create: Could not create directory**

**Warning! Failed to move file.**

**Question:** How do I solve this?

**Answer:**

To solve this issue access the **configuration.php** file in the root folder where your Joomla! files are located.

Open the **configuration.php** file and look for the following lines

**var $log\_path = '/usr/home/web/joomla/logs';**

**var $tmp\_path = '/usr/home/web/joomla/tmp';**

Make sure the paths to the **logs** and **tmp** folder is correct.

Change it to something like below and the error message should disappear

**var $log\_path = './logs';**

**var $tmp\_path = './tmp';**

 

**nagaraju** Thursday, 22 April 2010

thank u very munch dude

VOTES:2

**TechPortal** Thursday, 22 April 2010

Glad this how-to was helpful

VOTES:0

**Alen** Wednesday, 12 May 2010

Thank you very much m8... :)

VOTES:1

**ashraf melhem** Thursday, 20 May 2010

:woohoo:

i want to thank you for this solution , it\\'s simple and fast ,

you are great .

VOTES:1

**Ivan** Wednesday, 26 May 2010

I have tried that and double checked with the exact path that im seeing in cpanel as well and nothing works.

VOTES:0

**TechPortal** Wednesday, 26 May 2010

in cpanel in will be something like

/home/website/public\_html

VOTES:1

**fax** Wednesday, 23 June 2010

When trying to insert an image i get the following error;

Error

\* JFolder::folder: Path is not a folder

Warning: Invalid argument supplied for foreach() in /public\_html/home/administrator/components/com\_media/models/manager.php on line 74

Error

\* JFolder::files: Path is not a folder \* JFolder::folder: Path is not a folder

I read somewhere, i need to create a folder, but don\\'t know which directory it needs to be in? Please help, i\\'m stuck on this and can\\'t continue! ...

VOTES:0

**TechPortal** Wednesday, 23 June 2010

fax wrote:

When trying to insert an image i get the following error;

Error

\* JFolder::folder: Path is not a folder

Warning: Invalid argument supplied for foreach() in /public\_html/home/administrator/components/com\_media/models/manager.php on line 74

Error

\* JFolder::files: Path is not a folder \* JFolder::folder: Path is not a folder

I read somewhere, i need to create a folder, but don\\'t know which directory it needs to be in? Please help, i\\'m stuck on this and can\\'t continue! ...

Check if a images folder is present in your Joomla! root directory and make sure that it is writable.

VOTES:0

**Khurram Fraz** Friday, 25 June 2010

many thanks, its really helpful.

VOTES:0

**Chuck** Friday, 06 August 2010

Many, many THANKS.. this info was very helpful..it works

VOTES:0

**JJ** Thursday, 09 September 2010

Thanks for the Joomla fix on extension installs. I fixed the config file as directed and it worked like a charm!

VOTES:1

**Chege** Tuesday, 28 September 2010

:woohoo: You are a legend ...it worked like magic was quick and easy to do.. Thanx be blessed m8

VOTES:0

**Anonymous** Sunday, 10 October 2010

I don\\'t know what to say but man you are a geneous man thank you very much

VOTES:0

**Gabriel** Wednesday, 20 October 2010

Thanks man... you are THE DUDE!!

VOTES:0

**voula** Wednesday, 10 November 2010

SO SIMPLE ! i was searching a solution for hours... Thank you so much !!!!!!!!!!!!!!

VOTES:1

**niral** Friday, 03 December 2010

WORK LIKE A CHARM AWESOME SOLUTION

VOTES:0

**Navjinder** Tuesday, 07 December 2010

Finally !!!! well done man!! lot of thanks to you

VOTES:0

**niyaz** Tuesday, 14 December 2010

thanks friend, it works..

VOTES:0

**Sincere337** Tuesday, 28 December 2010

When I edited the config file as stated above, I said there is no way that this simple fix will get rid of the problem, then.....Holly Crap! It worked! Thanks a lot for posting this up.

VOTES:0

**TechPortal** Thursday, 30 December 2010

Yip, never underestimate simple solutions :D

VOTES:0

**emmceegee** Wednesday, 23 February 2011

thanks so much - works great!

VOTES:0

**zara** Thursday, 24 March 2011

TQ...so much god bless u.

VOTES:0

**fiyah** Saturday, 09 April 2011

Kept It Straight & Simple Thanx

VOTES:0

**mark** Wednesday, 01 June 2011

Thanks! for posting this it worked. I can install my plugin.

mark

VOTES:0

**Md. Shafiul Alam** Tuesday, 05 July 2011

Thank you so much !!!!!!!!!!!!!!

VOTES:0

**Ken** Thursday, 21 July 2011

Great Tip! Simple but solved my problems especially I am 10,000 miles away trying to figure out joomla problem. Thanks :)

VOTES:0

**bharat** Sunday, 31 July 2011

thankx a ton! it was fast n simple!

VOTES:0

**Raj Keshwani** Friday, 05 August 2011

hey my is also working :cheer:

VOTES:0

**rokim** Monday, 22 August 2011

Matur nuwun sanget/Thank\\'s u very much

VOTES:0

**Pink Panther** Wednesday, 24 August 2011

I have changed the path to var $log\_path = \\'./logs\\'; var $tmp\_path = \\'./tmp\\';

and i still get the error =JFolder::create: Could not create directory Component Install: Failed to create directory.: \\"/usr/local/www/domainname/url/htdocs/components/com\_jce\\" Install Component Error.

help me.:(

VOTES:0

**Sachin Kumar Chauhan** Tuesday, 30 August 2011

sorted the problem. its a very silly mistake we do

VOTES:0

**sadegh** Wednesday, 07 September 2011

tanx so much for yor good solution

VOTES:0

**Ruth** Thursday, 15 September 2011

I was prepared for this to not work as nothing ever seems to first time around. But it DID! so easy. Thanks!

VOTES:0

**Arthur Christopher Lwanga** Wednesday, 05 October 2011

Yo the best, thank you very much

VOTES:0

**Soyeb Rana** Tuesday, 18 October 2011

:lol: Thanks a lot, brother... Thank you.

VOTES:0

**teboho** Wednesday, 09 November 2011

**_thanx_** i woked like a charm :cheer: :kiss: but localhost is a bit slow after that now

VOTES:0

**Mohamed Riyas** Thursday, 10 November 2011

I am serching this for weeks.

At last find the wright solution here

Thanks a Lot. I Works. Very Very Useful

VOTES:0

**nghiem sy toan** Saturday, 12 November 2011

it really great.thank you.too simple :)

VOTES:0

**Dan Gaz** Thursday, 22 December 2011

Thank You!

VOTES:0

**Sheyo** Tuesday, 27 December 2011

Thanks, it works like charm.

VOTES:0

**yogs** Friday, 13 January 2012

It\\'s simply best thanks :woohoo:

VOTES:0

**jpk** Tuesday, 24 January 2012

Thank you very much techportal..... i also faced the same problem.... It works fine now because of this article.......

VOTES:0

**bhaven** Tuesday, 24 January 2012

Nice Commnet its works :lol: :lol: :lol: :lol:

VOTES:0

**Rakesh Rooprai** Friday, 03 February 2012

Thanks Dude,You really saved my lots of time.

VOTES:0

**Anonymous** Thursday, 09 February 2012

Works a treat! Many thanks for saving my time

VOTES:0

**Stephanie** Thursday, 22 March 2012

Thank you loads- what the supporters could not solve- you did...keep up the good work!!!

VOTES:0

**ivan** Thursday, 22 March 2012

This was good.

VOTES:0

**Jose Diaz** Saturday, 31 March 2012

Hey man... works perfect

VOTES:0

**Julie Simpson** Friday, 04 May 2012

Thank you this worked perfectly for me!

VOTES:0

**Captain mutunga** Monday, 10 September 2012

JFolder::create: Could not create directory Warning! Failed to move file.

I have made sure the file permissions are 777 and the log and temp paths are still correct but still i cannot install a new component.

VOTES:0

**dhan** Monday, 24 September 2012

TechPortal wrote:

fax wrote:

When trying to insert an image i get the following error;

Error

\* JFolder::folder: Path is not a folder

Warning: Invalid argument supplied for foreach() in /public\_html/home/administrator/components/com\_media/models/manager.php on line 74

Error

\* JFolder::files: Path is not a folder \* JFolder::folder: Path is not a folder

I read somewhere, i need to create a folder, but don\\'t know which directory it needs to be in? Please help, i\\'m stuck on this and can\\'t continue! ...

Check if a images folder is present in your Joomla! root directory and make sure that it is writable.

I have changed the permissions writable, but not work...., any way out?

VOTES:0

**@dhan** Monday, 24 September 2012

In the Joomla! Backend go to the option Joomla! info and joomla will tell you if all folders are writable that need to be writable. In Joomla 1.5 is under the help menu

VOTES:0
