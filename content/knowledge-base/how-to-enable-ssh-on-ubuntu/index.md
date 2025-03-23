---
author: "icarnaghan"
title: "How to enable SSH on Ubuntu"
date: 2018-04-07
---

This could come in handy if your Desktop machine is at a Remote Location and you need to gain access to it.

**NOTE**: SSH = Secure Shell

Open a new **Terminal Window** (CLI) and type in the following command to install **SSH**

{codecitation class="brush: bash;"}sudo apt-get install ssh{/codecitation}

After installation you can test it to **SSH** to your **localhost** _(use your standard username and password)_

Example

{codecitation class="brush: bash;"}ssh localhost{/codecitation}

You'll see the following

{codecitation class="brush: bash;"}The authenticity of host 'localhost (::1)' can't be established. RSA key fingerprint is af:f0:36:84:26:48:50:03:14:d5:51:6f:95:e7:dc:a7. Are you sure you want to continue connecting (yes/no)?{/codecitation}

select yes and enter your password and your in!!
