---
layout: post
title: "January '19 Meetup Minutes"
date: 2019-01-08
tags: hillshade styles rule-based tables map-layout plugin quickmapservices georeference labeling auto-labels projections color-ramp imhof-shading blending-mode page-size page-properties freehandrastergeoreferencer
---

Covered Topics:
* Hillshades
* Rule Based Styling
* Insert Table in Map Layout
* Changing Page Size
* QuickMapServices in QGIS3
* Freehand Raster Georeferencer Plugin
* Automated Label Placement
* Visual Comparison of Geographic Extents

The January meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks again for their generous use of their conference room.

### Hillshades ###
Stu has created a guide to [using color ramps in QGIS 3](/resources.html#Color%20Ramps%20QGIS%203.4).
* The guide  was developed using QGIS version 3.4.3.
* There are prebuilt 590 color ramps available in QGIS 3.
* Stu was looking at rain data from during Hurricane Harvey and set a lower threshold to focus in on just the heavy rain areas.
* Looked Esri hillshade basemap compared to a hillshade Stu created from USGS 10 meter elevation data:
  * Esri data is very high resolution, includes roads, etc.
  * Stu is using [Imhof shading](https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/steal-this-imhof-like-topography-style-please/). He combined a green to white color ramp and the hillshade to get the shaded relief with color by elevation.
  * "sd-A" is the color ramp he chose.
  * Used blending mode (Multiply). This is more vibrant than the default method, which is similar to Esri uses.
    * __*TIP:*__ Be sure to use bi-linear interpolation instead of the default (nearest neighbor).

### Rule Based Styling ##
Stu demonstrated rule based styling.
* His example grayed out the polygons outside of his area of interest and only labeled the polygons of interest.
  * Stu added an attribute to use when defining the rules.
  * Configure by switching from *Single Symbol* to *Rule Based* styling, editing or adding a rule, and clicking on the formula button in filter button next to *Filter*.
  * Create a rule for the features outside the area of interest with black fill and partial transparency to gray them out.
  * __*TIP:*__ Hitting F7 brings up the *Layer Styling* window docked to the side.
  * __*TIP*__ Check the *Live update* option next to apply to see updates to the map as you change  style settings.

### Insert Table in Map Layout ###
Stu has been looking for a way to place a table of polygon attributes on a layout. He had a work around of exporting his project to an image and inserting the table with image editing software. Clifford suggesting asked about using *Print Composer*, which is not referenced as *Layout* on QGIS 3 menus. The group determined that you can add a label with arbitrary text and set the properties to do what Stu needs.

### Changing Page Size ###
Peter followed up by asking about using US page sizes. This is changed by right clicking on the layout and selecting *Page Properties...* from the pop-up menu. You can scroll down past the European page sizes and find Letter and other US page sizes.

### QuickMapServices in QGIS3 ###
Clifford asked if anyone else had experienced [QuickMapServices](https://qms.nextgis.com/about) not showing up on the *Web* menu in QGIS3. His is now under the *Layer -> Add Layer - > QuickmapsServices* at QGIS 3.4.3. Stu still found his under web. Paul subsequently installed QGIS 3.4.4 on MacOS and found his under web. We aren't sure what is going on.

### Freehand Raster Georeferencer Plugin ###
Clifford demonstrated the [Freehand raster georeferencer plugin](http://gvellut.github.io/FreehandRasterGeoreferencer/). Clifford's [demo slides](http://localhost:4000/resources.html#Freehand%20Raster%20Georeferencer) are available on our Reference page.

### Automated Label Placement ###
Clifford demonstrated the *Automated Placement Engine* for labels. Access its settings from the *Layer Properties* *Labels* tab using the button next to the pull down with *Single Labels* showing by default.

### Visual Comparison of Geographic Extents ###
Stu would like to produce a map comparing the area of the Arctic National Wildlife Refuge to the area of the District of Columbia. The map will support a thirty page report Stu is submitting as public input on a proposal for oil and gas drilling. Stu's report considers the visibility of projects as an environmental impact.

The group explored the possibility of using the plugin Clifford demonstrated, but did not have success bringing in the georeferenced TIFF with the plugin. Paul suggested doing it in *Composer/Layout* with two separate maps added and overlapping. Each with an appropriate equal area projection and both with the same scale.
