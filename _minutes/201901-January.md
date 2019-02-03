---
layout: post
title: "January '19 Meetup Minutes"
date: 2019-01-19
tags: hillshade styles rule-based tables map-layout plugin quickmapservices georeference labeling auto-labels projections 
---

Covered Topics:
* Hillshades
* Rule Based Styling
* Insert Table in Map Layout
* QuickMapServices in QGIS3
* Georeferencing
* Automated Label Placement
* Visual Comparision of Geographic Extents

The January meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks again for their generous use of their conference room.

### Hillshades ###
* Stu - Hillshades
  * Has a document - Peter is sending it to me on Slack; Chris B sent it to me in e-mail
  * Using QGIS 3.4.3
  * 590 color ramps available in QGIS
  * Color ramps
    * Looking at rain data for Hurricane Harvey time frame
    * Changed the thresholds to focus in on just the heavy rain areas
  * Looking at Esri hillshade
    * Compared to a hillshade Stu created from USGS 10 meter elevation data
    * Esri data is very high resolution, includes roads, etc.
    * Is using Imhof shading
  * Combined a green to white color ramp combined with the hillshade to get the shaded relief with color by elevation
    * sd-A is the color ramp he chose
    * Using blending mode (Multiply) this is more vibrant than the default (which is like what happens in Esri)
    * Suggests being sure to use bi-linear interpolation instead of the default nearest neighbor

### Rule Based Styling ##
* Stu - Rule Based Styling
  * Example of shading polygons of interest differently than polygons of non-interest differently and then only labeling polygons of interest
  * Added an attribute to use for shading and labeling
    * Hit F7 to bring up Layer styling docked to the side with instant updates to style settings
      * Go to Rule Based tab
        * Click on formula button in filter  and define the criteria for no fill for areas of interest
        * Leave formula blank to pick up everthing else. Make it black with transparency to "grey out" the remaining area

### Insert Table in Map Layout ###
* Stu - Looking for a way to make a table of polygon attributes inserted on the map
  * He ended up exporting his project to an image and adding it in Paint
  * Clifford asked about using composer.
    * Looks like you can add a label with arbitrary text and set the properties to what Stu needs
* Peter - asked about using US page sizes
  * Right click on map and select Page Properties
  * You can scroll down past all the European page sizes and find Letter, etc.

### QuickMapServices in QGIS3 ###
* Clifford - asked about QuickMapServices in QGIS3
  * Stu has it in his but isn't sure how he added it. His is still under Web menu
  * Upgraded to QGIS 3.4.3
    * Quickmap services is now under the layer -> Add Layer - > QuickmapsServices
	
### Georeferencing ###
* Clifford - Geo referencing
  * Freehand Raster GeoReferencer Plugin
  * Clifford has some slides
  * Outputs a PNG with a world file

### Automated Label Placement ###
* Clifford - Automated Placement Engine for labels 
  * Access with button next to "Single Label" choice 

### Visual Comparision of Geographic Extents ###
* Stu - Submitting a 30 page report to the Feds as part of the public input for the oil & gas drilling on the artic refuge
  * Wants them to consider visibility of projects as environmental impact
  * Wants to make a map of the lease area compared to a major city (say Washington DC)
  * Explored using clifford's extention with the group
    * Did not have success initialy bringing in the georeferenced TIFF with the plugin
Paul suggested doing it in composer with two maps in the same equal area projection with the scale set the same for both maps
