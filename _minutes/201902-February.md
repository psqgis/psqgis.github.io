---
layout: post
title: "Febuary '19 Meetup Minutes"
date: 2019-08-08
tags: install qgis-3 open-data lidar raster learning print-map
---

Covered Topics:
* MacOS installation of QGIS 3
* Practical QGIS Project
* Semi-Automatic Classification Plugin
* Creating a Paper Trail Map

The February meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks again for their generous use of their conference room.

## Just Raw Notes for Now ##

* Installation of latest version of QGIS 3.x in Mac/Win/Linux for any members.
  * Peter successfully installed QGIS 3.4 on Mac
  * Had to install the specific version of Python 3.6
  * Had to set up some variables according to the instructions
		
* We will start series of practical exercises in QGIS to support our host InterIM's business need.
  * This month we'll import building footprints for International District.
    * Look at city of Seattle vs the OSM building data
    * OSMDownloader plugin failed to run successfully for Peter and Paul in MacOS
    * City of Seattle data from data.seattle.gov
      * Go to Land Base
        * Search for building: find 2015 Building Outlines
          * Download shapefile
    * King County open data site: download parcel address
  * Peter had to start a new project in QGIS 3 instead of his old QGIS 2 project in order to get the on the fly project to work
		
* Michael Patrick
  * King County collected LIDAR in 2016
  * Getting them from a State web site
  * Difference between the DTM and the DSM
  * Also can get density of laser points which is informative as to how much you can get out of the layer.
  * Also can get the point cloud
  * Looked at product called CloudCompare
    * Use to extract "garbage"
    * Uses the intensity of the response to distiguish between what he wants
  * Looked at a product called Mesh Lab
    * Use on the content coming out of Mesh Lab

* Bob Catherman will share his experience in teaching QGIS at Vietnamese University and how he is developing GIS curriculum for the school using QGIS. He'll also present on workflow and results using QGIS SCP (Semi-automatic classification).
  * Medrix
  * Teaches in English with simultaneous Vietnamese translation
  * 7 computers and 23 students
  * First 2 volumes are available and in use now.
  * Finished rough draft of Volume 4 of his Environmental Science curriculum
    * UW Geographic students critique his curriculum before he takes it to the Vietnamese students.
    * Using SCP (Semi-automatic Classification Plugin)
      * The plugin does it's own atmospheric correction on level 1 data. Which is not as good as the level 2 data from the Feds but that has to be ordered and comes in days not minutes
	
* Allie M - Public Health Professional, working on Autonomous vehicles at Lyft.
  * Working on Miller bay, a small area near the Suquamish reservation
  * Working on a print Trail map
  * Wants to add hill shade or lidar imagery.
