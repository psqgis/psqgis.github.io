---
layout: post
title: "February '18 Meetup Minutes"
date: 2018-03-05
---

The February meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks again for their generous use of their conference room.

* Paul showed how the Census Bureau is using customized versions of QGIS known as [GUPS](https://www.census.gov/programs-surveys/bas/technical-documentation/gups-instructions.html)  for boundary and address data update by local governments in preparation for the 2020 US Census.
    * [Video](http://www.sandag.org/resources/demographics_and_other_data/demographics/census/LUCATrainingWorkshop2017/GUPS_Demo.mp4) hosed by the [San Diego Association of Governments](http://www.sandag.org/index.asp?fuseaction=about.home).

* Peter and Evan explored templates for *Map Composer*.
    * The computer used for demonstration was running QGIS v2.18.14.
    * From a configured map composition in the *Map Composer* window, save as template.
    * Positioning of the various objects in *Map Composer* is saved in the template.
    * There is a *Map Composer* folder that is used by default: _.qgis2/composer_templates_
    * Within one project you can't use a template to save a given map extent/scale.
        * Alternatively, bookmarks are available in the main QGIS window. They are saved globally to your computer, available from all QGIS documents.
* Evan mentioned that QGIS 3.0 will be released in 10 days.
    * There are still many plugins that people rely on missing for version 3.
    * Selective masking is a promising new feature.
* Stu demonstrated an interesting technique using *Time Manager* to animate commercial marine vessel movement in the Salish Sea with tails trailing behind the points as they move across the map.
    * Stu used two techniques from [Nyall Dawson](https://nyalldawson.net/):
        * [Label halos](https://nyalldawson.net/2017/04/about-label-halos/)
        * [QGIS live layer effects](http://nyalldawson.net/2015/04/introducing-qgis-live-layer-effects/)
            * It doesn't work in *Map Composer*.
            * It uses the *Draw Effects* settings.
    * Commercial marine vessel traffic [data](https://marinecadastre.gov/ais/) from MarineCadaster.gov.
        * Data available from 2009 to 2014.
    * Created tails for his points using [Trajectory animations with fadeout effects](https://anitagraser.com/2015/05/08/trajectory-animations-with-fadeout-effect/) from Anita Grazer.
        * Starts with a large magenta dot that fades out over time and a small green dot that fades in over time.
        * Sets a data defined overide on the fill, and size attributes for the symbol.
            * Copied the code provided on Anita Grazer's blog.
            * For more information look at *scale_exp* usage in the *Expression Builder*.
            * The layer being symbolized has to have a text field in it that conforms to the [time format string](http://strftime.org/).
        * Stan uses Sony Movie Studio Platinum to assemble the the PNG files produced by *Time Manager* into a video.
* Joel shared a tip to get QGIS to work right with high resolution screens with Windows 10.
    * It turns out he found an [answer](https://gis.stackexchange.com/questions/132491/qgis-on-uhd-screen) that Stu had provided in Stack Exchange.
    * Stu said this works not just with QGIS but with any software in Windows.
* Evan shared a tip to install and use the  [autoSaver](https://plugins.qgis.org/plugins/autoSaver/) plugin to keep from losing work if you have trouble with QGIS crashing as it will save your document on a periodic basis.
* Stu shared a fast way to add tiled basemaps.
    * In the Browser Panel select  _TileServer (XYZ) - add Connections_.
    * Evan said that turning on the _Use Native Render_ checkbox in the _Quick Map Services_ plugin may accomplish the same thing, by enabling the improved tile indexing code.
* Joel explained how to configuring default field values when adding features using data in GeoPackage format.
    * Works with lines, points, polygons, and attributes only with tables.
    * Similar to building "domains" in ArcMap.
        * Attribute table has a *type* field and an *attribute_schema*.
            * *attribute_schema* is a text field with JSON schema code in it.
        * *type* field is only in the geometry layers.
        * Fields have default values, etc defined in the *Layer Properties*, *Fields* tab, *Edit* widget.
            * *Fields* tab: *Python Init Function* and *Function Name*
            * Uses the JSON schema to populate the fields.
    * To share this you need to include: the GeoPackage, the QGIS file, and the scripts, all in the correct directories.

---------

If anyone has corrections or additions they would like to make to these notes please let Paul McCombs know, or submit a pull request on [github](https://github.com/psqgis/psqgis.github.io)
