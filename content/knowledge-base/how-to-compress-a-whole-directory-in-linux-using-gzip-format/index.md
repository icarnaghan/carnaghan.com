---
author: "icarnaghan"
title: "How to compress a whole directory in Linux using gzip format"
date: 2018-04-07
---

How to **compress** a **whole directory** in **Linux** using **gzip** **format** via the **command line**?

 

This is a perfect way of creating **backups** of your **files** and **folders** or **emailing** **files**to a **friend** or **colleague**. This could also be called a **compressed archive**.

First this **command** **creates** the **archive** and then it **compresses** the **archive**.

 

Lets put it to practice

You have a **directory** called **documents** where all your **important documents** are **stored**. And you would like to **archive** and **compress** this **directory** for **backup**purposes using **GZIP**.

You will execute the following **command** via the **command line**:

tar -zcvf documents.tar.gz /home/your\_name/documents

 

Explanation of command:

1. We create a **compressed archive** of your **documents** **directory** to the **directory**your currently in called **documents.tar.gz**
2. Use the **tar** command to use the **tar archiving utility**
3. With the following options **-zcvf**
    1. **z =**compress the archive through **gzip**
    2. **c =** create a new **archive**
    3. **v =** verbose which means list the progress while creating the archive
    4. **f =** use archive file

 

How to extract the compressed archive

Use this command:

tar -zxvf  documents.tar.gz

 

Explanation of command:

1. Will extract all files in current directory
2. Use the **tar** command to use the **tar archiving utility**
3. With the following options **-zxvf**
    1. **z =**compress the archive through **gzip**
    2. **x =** extract files from an **archive**
    3. **v =** verbose which means list the progress while creating the archive
    4. **f =** use archive file
