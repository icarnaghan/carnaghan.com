---
author: "icarnaghan"
title: "Windows Live Messenger gives ERROR 81000306 on Windows Vista"
date: 2018-03-24
---

Follow the steps below in order to solve this error

- Click on **Start**
- Above the start button type in **cmd**
- If **cmd.exe** appears under **Applications** right click on it and select **Run As Administrator**
- Type in the following: {codecitation style="brush: bash;"}netsh int tcp set global autotuninglevel=disabled{/codecitation}
- Press **enter**
- **Reboot** your computer and **Windows Live Messenger** should work again
