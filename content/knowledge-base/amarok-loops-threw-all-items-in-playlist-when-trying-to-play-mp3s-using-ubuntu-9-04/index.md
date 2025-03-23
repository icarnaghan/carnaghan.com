---
author: "icarnaghan"
title: "Amarok loops threw all items in playlist when trying to play mp3's using Ubuntu 9.04"
date: 2018-09-01
---

When adding new items to **Amarok in Ubuntu 9.04** the items do not want to play and Amarok only loops threw the whole playlist and no sound is heard.

Follow the steps below in order to solve the problem

**STEP 1**

Remove **GStreamer ffmepeg video plugin**, **GStreamer extra plugins** and **Movie Player (GStreamer)** via **Add/Remove**  (Applications ->  Add/Remove)

**STEP 2**

Open a new Terminal session and type in the following command to install **phonon-backend-xine: sudo apt-get install phonon-backend-xine**

**STEP 3**

Enter you're password and hit enter. Now **phonon-backend-xine** should be installed.

**STEP 4**

Open **Amarok** and the mp3 files should play.
