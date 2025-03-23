---
author: "icarnaghan"
title: "Screensaver Freezes in Ubuntu 11.04"
date: 2018-04-07
---

I've recently updated from Ubuntu 10.10 to 11.04 and found that whenever my screensaver activates the whole computer Freezes, I managed to solved the problem as discribed below.

 

Open a new **Terminal Window** and uninstall **Gnome Screensaver** by using the command below

```
sudo apt-get remove gnome-screensaver
```

 

Then we need to kill the **Gnome Screensaver process**, once again in the command line type in the following code to find the **Gnome Screensaver's** **process id**

```
pgrep gnome-screen
```

this command will show the **process id** for **Gnome Screensaver**

Now we will need to kill the process using the **kill** command

```
kill 3312
```

Replace 3312 with the **Gnome Screensaver process id**

 

Now we will need to install **xscreensaver** by using the following command

```
sudo apt-get install xscreensaver rss-glx xscreensaver-gl xscreensaver-data xscreensaver-gl-extra xscreensaver-data-extra
```

 

Now the final step is to Open the **Screensaver Preferences** under **_System->Preferences->Screensaver_**

If asked to launch the **XScreenSaver** **daemon** press **OK**, slect your screensaver and no more Freezing
