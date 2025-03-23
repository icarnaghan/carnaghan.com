---
author: "icarnaghan"
title: "How to resize a Batch of Images in Linux all at once"
date: 2018-04-07
---

**NOTE**: Tried and tested in **Ubuntu 11.04 Natty Narwhal**

 

To resize a batch of images we need to use a command line tool **_mogrify_** this tool forms part of the **ImageMagick Libraries**

To use the **_mogrify_** command line tool we will need to install **ImageMagick**

```
sudo apt-get install imagemagick
```

After the install locate the folder via the command line where the images are that need to be resized

```
cd /home/name/myPhotosResized
```

Type in the following command to resize the images in the myPhotosResized folder to 1280px in width and maintaining the original aspect ratio

```
mogrify -resize 1280 *.jpg
```

To force the images to resize to 1280x800 without keeping the aspect ratio use the following command

```
mogrify -resize 1280×800! *.jpg
```
