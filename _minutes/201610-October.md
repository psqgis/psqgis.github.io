---
layout: post
title: "October '16 Meetup Minutes"
date: 2016-11-12
tags: esri plugin raster serval qfield data-entry osgeo4w learning
---

Covered topics:
* ArcMap - QGIS function cross reference.
* Plugins: Serval, qfieldsync
* Custom Data Entry Forms
* Discover QGIS

* Stu Smith has started a document that cross references features in Esri ArcMap with how that same function can be accomplished in QGIS. Stu will send his document to Paul McCombs who will create a Google doc and link it from the web site.
* Stu has found a plugin [Serval](https://plugins.qgis.org/plugins/Serval/) that can be used to update values for individual raster grid cells or rectangles.
* Stu also found an interesting [plugin](https://plugins.qgis.org/plugins/qfieldsync/) for [Qfield](http://planet.qgis.org/planet/tag/qfield/)
* Andrew has developed a number of QGIS custom data entry forms.
    * Several types of input are available.
    * You can build custom forms using QT widgets.
        * You need to install development tools, which are included in [OSGeo4w](http://trac.osgeo.org/osgeo4w/).
        * It has a drag and drop graphic interface.
        * You need to rename the widgets to match the data fields that you associate them with.
    * Andrew had an example form with 4 tabs.
        * One tab has pictures that you can move through and see them right in the form, which uses web views.
    * Custom forms make it easier for data entry and viewing.
    * You can use python to validate values and alter the text formatting based on that validation.
    
* Peter Keum has started looking at Discover QGIS, a curriculum for teaching GIS with QGIS.
    * It's [available online](https://locatepress.com/dqw) from [Locate Press](https://locatepress.com/books).
