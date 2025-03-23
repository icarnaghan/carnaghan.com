---
author: "icarnaghan"
title: "How to add a Color Picker utility in Komodo Edit"
date: 2018-04-07
---

Follow the steps below in order to add the color picker

**STEP 1**

In **Komodo** click on the Top Toolbar **TOOLBOX**\->**ADD**\->**NEW MACRO**

**STEP 2**

Give your **Macro** a new name eg. **Color Picker**

**STEP 3**

Set the **language** to **JavaScript**

**STEP 4**

**Copy** the following code into the **textarea** below underneath where you set the language

```
/*

 * JavaScript macro to provide a basic color picker for hexadecimal colors.

 * Assign a useful keybinding to this macro and ka-zam, funky color picking!

 *

 * Version: 1.3

 *

 * Authored
```

by:

```
 David Ascher

 * Modified
```

by:

```
 Shane Caraveo

 *              Todd Whiteman

 *              Conor Kerr

 *              Michal Ko?árek

 *

 * [ADDED] 1.3: Color picker parses named colors from selection as well.

 * [ADDED] 1.2: Support for pre-selected
```

colours

```
 without a hash and 3 character

 *
```

colour

```
 codes added.

 */

function system_colorpicker(color) {
    var sysUtils = Components.classes['@activestate.com/koSysUtils;1'].
                    getService(Components.interfaces.koISysUtils);
    if (!color)
        color = "#000000";
    
    // If color is not in hexa format (#XXXXXX, #XXX with/without hash)
    // convert the color to hexa format before passing it to color picker
    if (!/^#?[\da-f]{3}(?:[\da-f]{3})?$/i.test(color)) {
        var span = document.createElement('span');
        span.style.color = color;
        
        var color_rgb = window.getComputedStyle(span, null).color;
        color = rgb2hex(color_rgb);
        delete span;
    }
    
    // Make sure selected colour is in correct format (preceded by hash) before passing to dialog
    var hash_added = false;
    if (color.charAt(0) != '#') {
        color = '#' + color;
        hash_added = true;
    }
   
    // Handle 3 character (shorthand) colour representations
    if (color.length == 4) {
        color = color.substr(0, 2) + color.charAt(1) + color.charAt(2) +
                color.charAt(2) + color.charAt(3) + color.charAt(3);
    }

    newcolor = sysUtils.pickColor(color);
    if (newcolor) {
       var scimoz = ko.views.manager.currentView.scimoz;
       // Remove any hash added to the selection
       if (hash_added) {
           newcolor = newcolor.substr(1, newcolor.length - 1);
       }

       scimoz.replaceSel(newcolor);
       scimoz.anchor = scimoz.currentPos;
    }
}

function colorpicker_onchange(event, cp) {
    var scimoz = ko.views.manager.currentView.scimoz;
    scimoz.insertText(scimoz.currentPos, cp.color);
    // Move cursor position to end of the inserted color
    // Note: currentPos is a byte offset, so we need to corrext the length
    var newCurrentPos = scimoz.currentPos + ko.stringutils.bytelength(cp.color);
    scimoz.currentPos = newCurrentPos;
    // Move the anchor as well, so we don't have a selection
    scimoz.anchor = newCurrentPos;
    // for some reason we get the event twice, removing
    // onselect fixes the problem.  Tried to solve it
    // by canceling the event below, but it went on anyway
    cp.removeAttribute('onselect');
    cp.parentNode.hidePopup();

    event.preventDefault();
    event.stopPropagation();
    event.cancelBubble = true;
    remove_colorpicker();
}

function remove_colorpicker() {
    // remove the popup from the document.  this cleans up so
    // we can change the macro code if needed
    var p = document.getElementById('popup_colorpicker');
    if (p)
        p.parentNode.removeChild(p);
}

function init_colorpicker() {
    remove_colorpicker();
    var p = document.createElement('popup');
    p.setAttribute('id', 'popup_colorpicker');
    var cp = document.createElement('colorpicker');
    cp.colorChanged = colorpicker_onchange;
    cp.setAttribute('onselect', 'this.colorChanged(event, this);');
    p.appendChild(cp);
    document.documentElement.appendChild(p);
}

/**
 * Convert CSS color representation from rgb(...) string
 * to the hexa format with hash on beginning.
 * @param color {String} Color in rgb(...) css format
 * @returns {String} Color in hexa string (#xxxxxx) (Falls back to black color)
 */
function rgb2hex(color) {
    var match = color.match(/rgb\((\d+),\s*(\d+),\s*(\d+)\)/i);
    if (!match)
        return "#000000";
    match.shift();
    
    for(var i = 0; i < match.length; ++i) {
        match[i] = (match[i] < 16 ? '0' : '')
            + parseInt(match[i]).toString(16).toLowerCase();
    }
    
    match = '#' + match.join('');
    return match;
}

var currentView = ko.views.manager.currentView;
if (currentView) {
    currentView.scintilla.focus();
    var os_prefix = window.navigator.platform.substring(0, 3).toLowerCase();
    if ((os_prefix == "win") || (os_prefix == "mac")) {
        var color = null;
        try {
            color = ko.interpolate.interpolate(window, ["%s"], [])[0];
        } catch(ex) {
            // No selection, ignore this error.
        }
        system_colorpicker(color);
    } else {
        init_colorpicker();
        var scimoz = currentView.scimoz;
        var pos = scimoz.currentPos;
        var x = scimoz.pointXFromPosition(pos);
        var y = scimoz.pointYFromPosition(pos);
        var boxObject = currentView.boxObject;
        var cp = document.getElementById('popup_colorpicker');
        cp.showPopup(currentView.scintilla,
                     x + boxObject.x,
                     y + boxObject.y,
                     'colorpicker',"topleft","topleft");
    }
}
```

**STEP 5**

Click on **Key Binding** and select your **Shortcut key combination** that you want to **trigger** the **Color Picker** with. I used **CTRL+ALT+c**

**NOTE**: This has been tested on **Komodo Edit 5** _**(Ubuntu 9.04 Jaunty)**_

**SOURCES**: http://community.activestate.com/forum/color-picker-macro-useful-css
