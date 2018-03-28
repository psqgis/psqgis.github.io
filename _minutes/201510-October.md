---
layout: post
title: "October '15 Meetup Minutes"
date: 2015-10-18
tags: psqgis-business raster joins learning
---

Covered Topics:
* PSQGIS User's Gruop Business
* Blend Colors Between Two Raster Layers
* How to Join Attribute Tables in QGIS
* QGIS Web Resiurces
* QGIS Tips

The Puget Sound QGIS user's group met Tuesday October 13th at the Richmond Beach Library. We had seven members in attendance and opened the meeting with a discussion of our large membership versus the small attendance, and where we could get our meetings out of Shoreline and closer to members in the south Puget Sound area. The cost of using meetup.com is rising because we crossed the 50 member threshold. We are planning to create a survey about where people would be able to attend meetings and if they are willing to contribute to the cost of meetup.com. Stu Smith covered several, but not all of the topics he listed in the agenda for the meetup:

__Blend Colors Between Two Raster Layers__

Stu demonstrated how to add raster data, create a hillshade, and then blend colors between two layers, using a hillshade as an example.
* Start with a DEM shaded from green through brown to white.
	* Stu used a color ramp named "sda" that he found with help from [Anita Graser](http://anitagraser.com/2011/11/02/more-color-ramps-for-qgis/).
* Create a gray hill shade.
* If you draw a 50% transparent colored DEM over the hillshade, the result is washed out.
* A superior alternative in QGIS - The Multiply Blending Mode
	* [Further reading](https://en.wikipedia.org/wiki/Blend_modes)
	* Style menu -> Color Rendering -> Blending mode -> Multiply
	
__How to Join Attribute Tables in QGIS__

*See Su's Full Notes*
* Stu started with a Washington State Counties layer.
* Added a table of April 2010 unemployment data for Washington state with records for counties and metropolitan statistical areas.
	* Use "Add Vector Layer" to add a *.DBF file.
	* Use "Add Delimited Text Layer" to add a *.CSV file.
	* Export Excel data to create a *.CSV file.
* FIPS code is common between the layer and the table, but with different field names. 
* Open Layer properties for the Washington State Counties layer.
	* Select the Join tab.
		* Add a join with the following:
			* Select the table with unemployment data.
			* Select the join field containing the FIPS code.
			* Select the target field containing the FIPS code.
			* Choose the fields you want to show up in the joined attribute table.
			* The custom field name prefix can be used to shorten or otherwise replace the name of the joined table that ends up in the joined field names.
* A question came up about the "Cache join layer in virtual memory". Does it affect if the result gets refreshed when the joined table is updated.
* By default QGIS joins are an outer join and a selection of the result is required to achieve an inner join.
* A question was raised about the difference between Outer and inner joins.
	* Clifford shared a [good explanation of the difference](http://blog.codinghorror.com/a-visual-explanation-of-sql-joins/)
	* Outer join: will show all of the records from one of the two tables and the matches from the other table
	* Inner join: will show only the records where there is a match between the two tables
* As of version 2.10 you can use a filter on a joined layer. Previously you could not.
	* Issue: When you create a filter on a layer with an open attribute table, the open table view doesn't get updated to match. You can close the attribute table window and re-open it to see the result.
* Wait for a word document from Stu
*Stu began his presentation on relates and how they compare to joins. They can handle one-to-many relationships. The group wandered off track and ran out of time. Paul McCombs agreed to research this and present his results at the next meeting. Stu prepared [notes](#join-and-relate-notes-from-stu) which he provided via e-mail and are included below.
					
__Web Sources for QGIS Help__
* [ieqgis.wordpress.com](https://ieqgis.wordpress.com/)
* [anitagraser.com](http://anitagraser.com/)
* [nyalldawson.net](http://nyalldawson.net/)
* [nathanw.net](http://nathanw.net/)
* [gis.stackexchange.com](http://gis.stackexchange.com/)

__QGIS Tips__
* To pan the map with another tool selected hold down space bar while you click and pan.	
* Gotostreetview plugin
	* Install Plugins->Manage and Install Plugins...
		* You can browse and update all the plugins that are available.
	* After it's installed access under Web menu.
	* Shows the direction that you are viewing on the main map.
	* Switches between Google Street view and Bing Birdseye view.
* As promised Stu presented a special surprise topic.
	* Stu reserved this tip for those attending the meeting, and e-mailed his detailed notes. Thanks Stu!

Stu Smith, John Murphy, and Paul McCombs have volunteered with topics for the next meetup. Stu is looking for meeting space in Tacoma.
