---
layout: post
title: "October Meetup Minutes"
date: 2015-10-18
---

The Puget Sound QGIS user's group met Tuesday October 13th at the Richmond Beach Library.

We had seven members in attendance and opened the meeting with a discussion of our large membership versus the small attendence, and where we could get our meetings out of Shoreline and closer to members in the south Puget Sound area. The cost of using meetup.com is rising because we crossed the 50 member threshold. We are plannign to create a survey about where people would be able to attend meetings and if they are willing to contribute to the cost of meetup.com.

Stu covered several, but not all of the topics he listed in the agenda for the meetup:

__Blend Colors Between Two Raster Layers__

Stu demonstrated how to add raster data, create a hillshade, and then blend colors between two layers, using a hillshade as an example.

* Start with a DEM shaded from green through brown to white.
	* Stu used a colorramp named "sda" that he found with help from [Anita Graser](http://anitagraser.com/2011/11/02/more-color-ramps-for-qgis/).
* Create a grey hill shade.
* If you draw a 50% transparent colored DEM over the hillshade, the result is washed out.
* A superior alternative in QGIS - The Multiply Blending Mode
	* [Further reading](https://en.wikipedia.org/wiki/Blend_modes)
	* Style menu
		* Color Rendering
			* Blending mode
				* Multiply
	
__How to join attribute tables in QGIS__

* Washington State Counties layer
* Table with April 2010 unemployment data
	* Use Add Vector layer add dbf files
	* Use Add Delimited Text File
		* Export Excel to CSV 
* FIPS code is common between the layer and the table.
* Open Layer properties for the county layer
	* Join tab
		* Add a join
			* Select table with unemployment data
			* Join field
			* Matching Target field
			* Pick the fields you want to show up in the joined attribute table
			* CustomName prefix can be used to shorten or change the name of the joined table that ends up in the column names.
			* By default it's always an outer join and a selection of the result is required to see a resulting inner join
			* Look into the cache in memory and if the join gets refreshed when the joined table is update*
* Outer join v. inner join
	* Add link from e-mail from Clifford
	* Outer join: will show all of the records from one of the two tables and the matches from the other table
	* Inner join: will show only the records where there is a match between the two tables
* As of version *10 you can use a filter on a joined layer. Previously you could not.
	* Issue: When you create a filter on a layer the shown attribute table doesn't get updated to match. 
	* You can close the attribute window and re-open
* Wait for a word document from Stu
* Relate can handle a one-to-many relationship
	* Add a table showing unemployment rate for several different dates
	* Project
		* Properties
			* Add a relation
				* Referencing Layer (child) - unemployment rates table
	* Result comes up in a weird view switch to tabular view
	* Stu is looking for a way to output the result as a new table.
					
* QGIS Sources
	* https://ieqgis.wordpress.com/
	* http://anitagraser.com/
	* http://nyalldawson.net/
	* http://nathanw.net/
	* http://gis.stackexchange.com/

* To pan the map with another tool selected hold down space bar
	* See the keyboard shortcuts using settings->configure shortcuts
	
* Gotostreetview plugin
	* Installs under Web menu
	* Shows the direction that you are viewing on the main map.
	* Switches between google streetview and bing birdseye view

* Plugins
	* Manage and install plugins
		* You can browse and update all the plugins that are available.
	
* A special surprise topic!
	* Open python console
		* Paste in a line of python including the URL for one of ESRI's base map services and it will be added as a layer.