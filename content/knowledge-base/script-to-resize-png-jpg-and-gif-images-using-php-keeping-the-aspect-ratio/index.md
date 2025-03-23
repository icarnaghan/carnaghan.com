---
author: "icarnaghan"
title: "Script to resize PNG, JPG and GIF images using PHP keeping the aspect ratio"
date: 2018-03-22
---

**How this script works**: What this script does, it resizes any PNG, JPG or GIF image to the given width and height and stores the image to a specified location. If the width is set to 0 it will automatically calculate the width by using the height given by keeping the aspect ratio the same is. The same goes for when the height is set to 0 and the width is given.

**NOTE**: Make sure the GD libraries are enabled in order to use this script.

**Script**: 

```
         /**
        * make_thumb()
        * This function creates a new image in a Thumbnail Format. It also keeps the aspect ratio of images if width or height is set to 0  
        * @params String $img_name This needs to be the source_image name
        * @params String $filename This needs to be the Thumbnail Image Name ("path to the storage location")
        * @params Int $new_w The width of the new image
        * @params Int $new_h The height of the new image
        * @example make_thumb("original_image.jpg","path/resized_image.jpg",10,10);
        * @return resized Image
        */
       function make_thumb($img_name,$filename,$new_w,$new_h){
                $ext = substr(strrchr($img_name, '.'), 1);
 
                if(!strcmp("jpg",$ext) || !strcmp("jpeg",$ext)){
                         $src_img=imagecreatefromjpeg($img_name);
                }
 
                if(!strcmp("png",$ext)){
                         $src_img=imagecreatefrompng($img_name);
                }
                
                if(!strcmp("gif",$ext)){
                         $src_img=imagecreatefromgif($img_name);   
                }
 
                $old_x=imageSX($src_img);
                $old_y=imageSY($src_img);
 
                if($new_h <= 0){
                         // Calculate aspect ratio
                         $wRatio = $new_w / $old_x ;
 
                         $thumb_h = ceil($wRatio * $old_y);
                         $thumb_w = $new_w;
                 }else{
                         $thumb_w = $new_w;
                 }
 
                if($new_w <= 0){
                        // Calculate aspect ratio
                        $hRatio = $new_h / $old_y ;
 
                        $thumb_w = ceil($hRatio * $old_x);
                        $thumb_h = $new_h;
                }else{
                        $thumb_h = $new_h;
                }
 
                $dst_img=ImageCreateTrueColor($thumb_w,$thumb_h);
                imagecopyresampled($dst_img,$src_img,0,0,0,0,$thumb_w,$thumb_h,$old_x,$old_y);
 
                if(!strcmp("gif",$ext)){
                         imagegif($dst_img,$filename);
                }else if(!strcmp("png",$ext)){
                         imagepng($dst_img,$filename);
                }
                else{
                         imagejpeg($dst_img,$filename);
                }
 
               //destroys source and destination images.
               imagedestroy($dst_img);
               imagedestroy($src_img);
       }
```
