---
layout: post
title: "January Meetup Minutes"
date: 2016-01-24
---

The Puget Sound QGIS user's group met Tuesday January 12th at the Lake Forest Park Town Center.

We had a crowded room including several members who had not previously been to a meeting.

Stu Smith covered some group business. We now have 66 members. Meetup.com will be asking members to pay $1.50 per month to continue with the group after introductory period.

Stu gave brief history of QGIS for the new members attending which inspired some discussion including the following:

* Importing ESRI file based Geodatabase data type.
    * There is a [way to read and write using ESRI provided code](http://www.gdal.org/drv_filegdb.html). No one claimed to have done it.
    * ESRI created data can be read with the [OpenFileGDB](http://www.gdal.org/drv_openfilegdb.html) option included in QGIS.
* [Boundless](http://boundlessgeo.com/) offers [commercial support options](http://boundlessgeo.com/support/) if needed.
* [GIS Stack Exchange](http://gis.stackexchange.com/) is a good source of help for QGIS.
* You can always look through the minutes of our meetings at the [Puget Sound QGIS User Group web site](http://psqgis.org/).

Clifford Snow a leader of the [OpenStreetMap Seattle meetup group](http://www.meetup.com/OpenStreetMap-Seattle/) discussed a bid to host the annual State of the Map conference in Seattle this year. They are working with Microsoft for sponsorship. 

Clifford has been talking to developers about how Washington State Plane projections defined in ESRI generated shape files are not being detected properly from by QGIS. You can use the [Prj2EPSG](http://prj2epsg.org/search) web site to paste in the contents of a .prj file and get the EPSG code that QGIS uses to specify the projection.

Bob Catherman presented his experiment to use QGIS to process raster images.

* Trying to replicate the University of Maryland's [Global Forest Change 2000-2013](http://www.earthenginepartners.appspot.com/science-2013-global-forest) analysis for a small study area.
* Using Landsat data from USGS
    * 30 meter resolution
    * Captures same portion of earth every 16 days
    * Landsat 8 images: 100 miles square, 12 bands, 1GB+
    * Study area is a portion of Redmond, known to undergo housing development during the study period.
    * Using red and near infrared bands for analysis
* Crop rasters to study area:
    * Load vector layer of study area boundary
    * Load landsat data
        * 2003 day 149 (Landsat 7)
    * Clip landsat data to study area
        * Raster->extraction->clipper
        * Locate and name output file
* Use [NDVI formula](https://en.wikipedia.org/wiki/Normalized_Difference_Vegetation_Index) to determine forestation:
    * Use raster->raster calculator
    * Implement NDVI calculation multiply first value by 1.0 to get result as a floating point. Analysis will not work otherwise.
* Apply color ramp to calculator result
    * Bob ground truthed to develop his color ramp to classify land covers.

Next time Bob will demonstrate the [scp](http://fromgistors.blogspot.com/p/semi-automatic-classification-plugin.html) classification tool. Stu also asked Bob to demonstrate his color ramp development at a future time.

Stu gave a demonstration of editing vector data in QGIS.

* QGIS is a single user editing environment.
* Stu uses the quickmapservices plugin, in preference over the openlayers plugin for background imagery because it allows different projections.
    * Using bing satelite imagery
* Create a layer for new features:
    * Layer-.createlayer->new shapefile layer
    * Select type (point)
    * Select coordinate system (epsg:2927)
    * Add attributes that you want in your layer beyond the default (unique id).
    * Resulting layer gets added to the map.
* You can add the advanced edit toolbar.
* Start editing using pencil tool on the edit toolbar.
* Other edit toolbar tools:
    * Save edits
    * Move features
    * Current edits button has menu for rollbacks. Options to save selected layers or all layers.
    * To edit an existing line layer, use node tool.
* You can add and delete field while editing.
* Stu wants to look into virtual fields
* Using the Autotrace plugin:
    * Adds a tool to edit toolbar
    * Snapping settings in options
    * Start new feature:
        * Snap to one vertex on another feature.
        * Hold shift down and follow roughly existing feature, it will snap to all vertices along the way.
        * Left click to stop tracing.

In February John Murphy will demonstrate printing paper atlases and Bob Catherman will give the second part of his raster experiment.