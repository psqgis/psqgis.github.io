---
layout: post
title: "March Meetup Minutes"
date: 2016-04-11
---
    
* Evan Derickson gave an awesome presentation on [QGIS Cartographic Shortcuts](https://docs.google.com/presentation/d/1ypncU_P_6M84eMQd3pwulVRuvcgj5ZbOrn8p4ft8OUE/edit#slide=id.p).
    * Wanted to recreate ESRI cartography with QGIS
    * Hillshade
        * Old technique: % transparency
        * QGIS:
            * Blend Mode
                * Borrowed from graphics software
                * Doing math from the two layers
                * Multiply: makes the shadows darker, never lighter
                * Contrast Enhancement in the Hillshades Layer Properties-Style - Stretch to Min Max
                    * Set the Max to the peak band in the histogram
                    * This reduces the areas that are darkened. So the areas that would have a little darkening wont have any.
                * Soft-light:  brightens and darkens
        * ESRI now has a Swiss Method that Evan is trying to emulate with multiple angle hill-shades
        * Natural Earth has some great manual hillshades at small scale.
    * Glow Effects
        * Doesn't like to do just line borders on his polygons
        * Polygon layer properties - Style - Draw Effects check-box => Effect properties 
            * Inner Glow
            * Inner Shadow
    * Vignetting
        * You can load and save files from the style button in the Layer Properties - Style
        * Switch from simple fill to shapeburst fill
        * Many settings to adjust
        * Can ignore rings if you don't want islands to affect the vignetting
        * Blurring at almost full strength gave a good effect
    * Inverted Polygons
        * Layer Properties - Inverted Polygons instead of Single Polygons
            * Sub renderer controls how everything outside your selected polygons is symbolized.
    * Inner Borders
        * Allows coincident boundaries of adjacent polygons and symbolizes them according to polygon attributes
        * Outline for polygon is "Outline: Simple line" instead of "Simple line", then draw line only inside polygon
    * Rule Based Labeling & styles
        * Can do different labels on locator map and main map despite them both pointing at the same map.
        * Set scale ranges in the layer properties labels
        * Can control entire layers with scale maxes and mins for the layer
        * Can control symbology by changing single symbol to rule-based in layer properties - style

* Ideas for future meetups
    * Geo Packages - Stu
    * QGIS Map Packages - Stu
    * Time Manager - Stu
    * Web Mapping - group
    * Q Field - Stu