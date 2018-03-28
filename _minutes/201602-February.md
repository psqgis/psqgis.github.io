---
layout: post
title: "February '16 Meetup Minutes"
date: 2016-02-21
tags: openstreetmap paper-map map-series raster ndvi learning plugin scp web-map geopackage
---

Covered Topics:
* Openstreetmap Seattle
* Printing a map series
* Raster Image Classification and  Analysis
* Publishing to Web Maps

Clifford Snow shared what the OpenStreetMap Seattle is up to. Check out their [meetup.com page](http://www.meetup.com/OpenStreetMap-Seattle/).

John Murphy is showed how to print out a series of paper maps.

* Used the OSM base map.
* Created a subdivision point feature layer from polygon building lot features using PostGIS database commands.
* Open a New Print Composer window from the Project menu.
    * Go to the Atlas Generation tab in the Atlas settings.
        * Set the coverage layer to subdivisions layer.
    * Add Map from the Layout menu.
        * In the Item properties for the Map, check Controlled by atlas. This will center an atlas page on each point feature in the subdivisions layer.
        * You can set it to zoom to each feature with a buffer. This was not adequate for especially small subdivisions.
    * Add Label from the Layout menu.
        * Labels can be a formula tied to layer attributes.
        * When writing the query for the labels. The "Insert expression" dialog shows the just query. The box on the Item properties tab has [% %] around the query which is necessary. 
    * Select Preview Atlas from Atlas menu.
    * Use arrows in the tool bar to page through the atlas pages.
* John is trying to figure out how to hide the subdivisions that are not the current subject of an atlas page.

Bob Catherman - Part 2 Using QGIS to Process Raster Images.

* Using the NDVI calculation on Landsat image data.
* Between 2002 and 2014 there was a lot of development in the center of the study area.
* Vegetation increased in the previously developed lots, where landscaping grew in.
* Bob subtracted the 2014 NVDI from 2002 NDVI and applied a color ramp to show the change over time.
    * Bob created three categories: Loss of Vegetation; Gain of vegetation; and Neutral gain/loss.
* Final analysis result is very similar to the University of Maryland outcome. Differences can be attributed to:
    * Start and end points that were 1-2 years off from UMD.
    * UMD had a more clear definition of "forest" and had additional tree height data.
* Bobs slides are available on our [Resources page](http://psqgis.org/resources.html).

Bob Catherman - SCP ([Semi Automatic Classification Plugin](http://fromgistors.blogspot.com/p/semi-automatic-classification-plugin.html))

* Using RGB Landsat 8 image.
* Bob selected an area he was familiar with in central Washington.
* When picking training areas, stay away from land cover edges.
* Bob created training areas with the following known land use:
    * Cemetery
    * Urban area
    * Plowed field
    * Water
* The result was pretty reasonable using only a few training areas, fewer than are recommended.
* The author of SCP issues updates often.
* Satellite data can be downloaded directly from the plugin.
* Bobs slides are available on our [Resources page](http://psqgis.org/resources.html).

Bob Catherman has received feed back on his &quot;Monitoring Health Care Outcomes Using GIS&quot; handbook, which is available on our [Resources page](http://psqgis.org/resources.html). Bob will be working on a raster hand book as well.

Paul McCombs gave a brief demonstration of the PSQGIS web site.

Stu Smith: Free and open web mapping resources available to QGIS

* [qgis2web plugin](https://plugins.qgis.org/plugins/qgis2web/)
    * Creates a web map available on the internet.
    * Installs under web menu in QGIS.
    * Points are styled in QGIS as stars but they render as circles on the web map.
    * Stu's example showed 2015 fire data near Lake Chelan.
    * Stu acquired boundaries of the Lake Chelan Fire Complex from the US Forest Service.
        * Stu will provide the URL on request.
        * It is available as a [GeoPackage (*.gpkg)](http://www.geopackage.org/)
        * Stu located three look out towers and generated point data using lat/lon coordinates.
        * Stu computed view sheds from the towers and elevation in ArcINFO years ago.
        * Stu used the OSM base map.
    * From the plugin, select an output folder that can be copied to any web server you have access to publish on.
    * Stu used the OpenLayers3 option because the Leaflet option resulted in an error.
* [CartoDB plugin](https://plugins.qgis.org/plugins/QgisCartoDB/)
    * Need to have a CartoDB account. Clifford Snow says it's free.

On the agenda for next month:

* Stu will talk about GeoPackages.
* Evan Derickson will talk about QGIS cartography including hill shades, coastal vignettes and things you can't do in ArcMap.
