---
layout: post
title: "February '18 Meetup Minutes"
date: 2018-03-03
---

The February meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks again for their generous use of their conference room.

* Paul showed how the Census Bureau is using customized versions of QGIS known as [GUPS](https://www.census.gov/programs-surveys/bas/technical-documentation/gups-instructions.html)  for boundary and address data update by local governments in preparation for the 2020 US Census.
	* [Video](http://www.sandag.org/resources/demographics_and_other_data/demographics/census/LUCATrainingWorkshop2017/GUPS_Demo.mp4) hosed by the [San Diego Association of Governments](http://www.sandag.org/index.asp?fuseaction=about.home).

* Peter and Evan explored Templates for Map Composer.
	* The computer used for demonstration was running QGIS v2.18.14.
	* From a setup map composition in the Composer window, save as template.
	* Positioning of the various objects in Composer is saved in the template.
	* There is a Composer folder that is used by default: _.qgis2/composer_templates_
	* Within one project you can't use a template to save a given map extent/scale.
		* Alternatively, Bookmarks are available in the main QGIS window. They are saved globaly to your computer, available from all qgis documents.
		
# Continue Editing from Here 

* Evan discussed that Version 3.0 will be released in 10 day
	* Still a lot of plugins that are missing. Like most of them.
	* Selective Masking. No one has figured out how to get to it yet.
* Stu:
	* https://nyalldawson.net/2017/04/about-label-halos/
	* QGIS Live Layer Effects: http://nyalldawson.net/2015/04/introducing-qgis-live-layer-effects/
		* Does not work in composer
		* Draw Effects
	* Time manager of commercial marine vessel traffic in the Salish Sea
		* Data: https://marinecadastre.gov/ais/
			* 2009 - 2014 are available
		* Created tails for his points
			* Got this from Anita Grazer
			* Large Magenta dot
			* Small Green dot
			* First fades out
			* Second fades in
			* Set a data defined overide on the fill & size attributes for the symbol
					* Copy and paste a bit of code from Anita Grazer's blog
					* Look at scale_exp in the expression builder
		* Layer has to have a text field in it that conforms to the Time format string: http://strftime.org/
		* Uses Sony Movie Studio Platinum to assemble the output PNG into a video
* Joel: Get QGIS to work right with Hi Res. Screens on Windows 10
	* He found Stu's Answer in Stack Exchange
		* Stu says this works not just with QGIS but with any software
	* Joel sent me a link in my e-mail
* Evan: AutoSaver extension
	* Will save on a periodic basis
* Stu: fast way to add tiled basemaps
	* In Browser Panel: TileServer (XYZ) - add Connections
	* Evan: Turn on the "Use Native Render" checkbox in Quick Map Services extention may accomplish the same thing.
* Joel: Configuring default field values when adding features
	* Using GeoPackage
	* Lines, Points, Polygons, attribute only tables/layers
	* Basically building a "domain"
		* Attribute table has a type field and a attribute_schema
			* Attribute_schema is a text field with JSON schema code in it
		* Type field is also in the geometry layers
		* Fields have default values, etc defined in the layer properties, Fields tab, Edit Widget
		* Fields Tab: Python Init Function and Function name
			* This uses the JSON schema to populate the fields
	* To share this you need the GeoPackage, QGIS file, and the scripts in the correct directories

---------

If anyone has corrections or additions they would like to make to these notes please let Paul McCombs know, or submit a pull request on [github](https://github.com/psqgis/psqgis.github.io)
