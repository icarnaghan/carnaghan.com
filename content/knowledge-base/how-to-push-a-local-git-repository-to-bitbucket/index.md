---
author: "icarnaghan"
title: "How to push a local GIT repository to Bitbucket"
date: 2018-04-07
---

1. Launch **Bitbucket**
2. Click on **Repositary -> Create Repository**
3. Enter your **Repository name**
4. Set the access level to **This is a private repository**
5. Set **Repository type** to **GIT**
6. Click on **Create Repository**
7. Using **GIT** on the command line, execute the next set of commands:
    
    ```
    cd /path/to/my/repository
    git remote add origin https://username@bitbucket.org/<username>/<repositoryname>.git
    git push -u origin --all # pushes up the repo and its refs for the first time
    git push origin --tags # pushes up tags
    ```
