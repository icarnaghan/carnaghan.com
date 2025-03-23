---
author: "icarnaghan"
title: "How to add a Google Map to your mobile website"
date: 2018-03-22
---

- First of all we can only use a static map, since **Google Maps** uses **Javascript** to zoom etc and most phones on the market do not support **Javascript**, so the only solution is to use static maps.
- Before we can use the **Google Maps API** we need to apply for an **Application Key** by visiting this URL http://code.google.com/apis/maps/signup.html
- Now use the following code within an **HTML img** **tag**
    
    ```
    <img src="http://maps.google.com/maps/api/staticmap?center=ADDRESS&zoom=14&size=150x150&sensor=false&markers=color:blue|ADDRESS&maptype=roadmap&mobile=true&key=APPLICATION_KEY" alt="Google Map" />
    ```
    
    Replace **ADDRESS** with you address Replace **APPLICATION\_KEY** with your **application key**, obtained from  http://code.google.com/apis/maps/signup.html
    
    Remember to **URL encode** the address entered
- For the complete **Static Google Maps API** visit  http://code.google.com/apis/maps/documentation/staticmaps/
