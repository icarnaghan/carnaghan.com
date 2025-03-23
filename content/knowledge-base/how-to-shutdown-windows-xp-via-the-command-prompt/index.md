---
author: "icarnaghan"
title: "How to shutdown Windows XP via the Command Prompt"
date: 2018-03-24
---

- First we need to open the **Command Prompt**
    - Press **WINDOWS KEY+R** together to open the Run window and type in the command below and hit OK to open **Command Prompt**. {codecitation type: bash}cmd{/codecitation}
    - Or click on **Start->All Programs->Accessories->Command Prompt** to open the **Command Prompt**.
- Once the **Command Prompt** window has opened we can type in the '**shutdown**' command. The shutdown command has many options, below we will use some examples

1. **Example 1**

- Shutdown PC
    - \-s = Tells the **shutdown** command to shutdown {codecitation type: bash}shutdown -s{/codecitation}

1. **Example 2**

- Shutdown PC within 30 seconds
    - \-s = Tells the shutdown command to shutdown
    - \-t  = Specify time followed by a open space followed by the number of seconds {codecitation type: bash}shutdown -s -t 30{/codecitation}

1. **Example 3**

- Shutdown PC within 30 seconds and displaying a message
    - \-s = Tells the shutdown command to shutdown
    - \-t = Specify time followed by a open space followed by the number of seconds, we add another blank space after the amount of seconds with a message, this message will display when the seconds countdown begins {codecitation type: bash}shutdown -s -t 30 "Ready to shutdown!!! Hurry Up!!!"{/codecitation}

1. **Example 4**

- Canceling the shutdown process (First need to have Command Prompt open)
    - \-a =  Tells shutdown to cancel {codecitation type: bash}shutdown -a{/codecitation}

**NOTE**: In order to view all options for the shutdown command, open the **Command Prompt** and enter the command below {codecitation type: bash}shutdown /?{/codecitation} this will display a list of options on how to use this command.
