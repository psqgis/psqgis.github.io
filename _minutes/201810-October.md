---
layout: post
title: "October '18 Meetup Minutes"
date: 2018-10-25
tags: hillshade raster labeling blendng-mode qgis-3 processing-modeler raster-calculus bug vertex editing learning
---

Covered Topics:
* Hill Shading and Label Positioning
* Raster Calculus with Processing Modeler
* QGIS 3.2.3 MacOS Display Bug
* QGIS 3 Vertex Editting Issues
* _Map Design-Second Edition_ by Anita Graser and Gretchen Peterson

The October meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks again for their generous use of their conference room.

### Hill Shading and Label Positioning ###

Taylor Rulien who works for [Aspect Consulting](https://www.aspectconsulting.com/), shared tips and tricks for hillshading and labeling. He has been looking into using open source tools to cut back on Esri licensing expense.
* Hillshading with blending modes:
    * Used [King County aerial image service](http://gismaps.kingcounty.gov/arcgis/rest/services/BaseMaps/KingCo_Aerial_2017/MapServer) and a hillshade of Mercer Island from the [Washington Lidar Portal](http://lidarportal.dnr.wa.gov/).
    * With Esri software you can make one of the layers semi-transparent, which washes out the image below.
    * In QGIS you draw the hillshade on top and use the darken or multiply blending mode. Then adjust the contrast to make the lighter portion of the hillshade transparrent. This makes the image full intensity color, but you can see the shading well.
* _Move Label_ is built into QGIS 3 and allows you to arrange the label for a feature, but still keep it "live", such that the label is still tied to the layer styling. 
    * You want to set the scale of your final map first so that the labels don't move when they are  drawn at a different scales.
    * The lock next to the scale at the bottom of the main QGIS window will lock the scale of the symbology and labeling. You can still pan and zoom the map.

###  Using Raster Calculus with Processing Modeler ###

Bob Catherman showed us how he is using *Processing Modeler* for vegetation analysis as part of a QGIS curriculum he's developing for use at [Hue University of Sciences in Vietnam](http://www.husc.edu.vn/en/news.php).

Bob created a model using the following tools and techniques:
* Raster Layer (GDAL)
* Clip Raster by Mask Layer (GDAL)
    * Assign 0 to no data cells
* Raster Calculus: Raster Difference (SAGA)
    * Was not able to get Raster Calculator working
    * Used three steps instead
* Raster Calculus: Raster Sum (SAGA)
* Raster Calculus: Raster Divide (SAGA)
    * This is tricky. Bob had troublr durring the demonstration
* Set it all up with no layer references
* Only name the output from the last step
* Specify the raster that you want to use when you run it.

### QGIS 3.2.3 MacOS Display Bug ###

Clifford Snow shared a known bug in 3.2.3 on MacOS. The map view doesn't fill in the whole portion of the window devoted to it. During the meeting Stephen Mangum installed QGIS on his Mac for the first time and experienced this bug. 

Clifford was able to demonstrate the work arround:
* Adjust the edges between various panels in the window and it will begin to fill the pannel as expected. 

### QGIS 3 Vertex Editting Issues ###

* Clifford Snow shared some odd behavior when editing vertices in QGIS 3 as explained in the second question on [this StackExchange](//gis.stackexchange.com/questions/278217/how-does-the-qgis3-vertex-editor-work). We could not duplicate it on MacOS. It may be a Linux only issue.

### _Map Design-Second Edition_ by Anita Graser and Gretchen Peterson ###

* Peter Keum has recently purchased latest QGIS 3.2+ Map Design-Second Edition by Anita Graser and Gretchen Peterson. Will talk about this new Beta version of QGIS how-to-book of 200+pages of valuable QGIS knowledge.
	* Peter got a preview release for a good price
	* Interestingly references it is 3.4 which is not yet released.
	* Exercises take longer than she says.
