---
layout: post
title: "October Meetup Minutes"
date: 2015-10-18
---

The Puget Sound QGIS user's group met Tuesday October 13th at the Richmond Beach Library.

We had seven members in attendance and opened the meeting with a discussion of our large membership versus the small attendance, and where we could get our meetings out of Shoreline and closer to members in the south Puget Sound area. The cost of using meetup.com is rising because we crossed the 50 member threshold. We are planning to create a survey about where people would be able to attend meetings and if they are willing to contribute to the cost of meetup.com.

Stu Smith covered several, but not all of the topics he listed in the agenda for the meetup:

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

## Join and Relate Notes from Stu

___QGIS Joins and Relates___

PSQGIS meeting, October 13, 2015


JOINS

Joins are either 1:1 or Many:1. Same with ArcMap

Joins are made via Layer Properties > Joins

After joining, the target table will display NULL values everywhere when you try to sort any of the fields. Solution: close the output table and then reload, subsequent sorts will be OK. Even subsequent joins will not require a reload.

Prefixes can be added to the output table's join field names, so that they are easily identifiable after the join. This is done in the Add Join dialog box, "Custom field name prefix". ArcMap does not provide for custom prefix names; only the join table name is used as a prefix.

At 2.10 you can edit the join properties, via Layer Properties > Joins > pencil button. The resulting changes are dynamic, reflected immediately in the output table's display. Not available in ArcMap.

A single individual join table can be simultaneously joined to multiple target tables.

Joins cannot be chained (join table joined to target table 1, which in turn is joined to target table 2)

Outer and Inner joins:

Outer joins:

* QGIS joins are always outer from the target table's perspective; that is, if a target table record does not have a matching record in the join table, the record is still displayed in the output table, with NULL values in the join fields (same with ArcMap). 

Inner joins:

* To do an inner join, make the initial outer join, then select (see "Selections" below) the output table for target table>join field = join table>join field*. The selected records now represent an inner join.
* QGIS, by default, does not display join table>join field. To override this default, in the Add Join dialog box, click "Choose which fields are joined, and then click the join table>join field. It will now display in the output table, and you can do your select.
* QGIS joins are always inner from the join table's perspective; the output attribute table will not include non-matching records from the join table. Same with ArcMap

Selections:

Selections made prior to joining:

* Join does not recognize records selected (either in the target table or in the join table) prior to the join. Same with ArcMap 

Selections made after joining:

* Spatial and/or attribute selections may be made on the output table (either on the target table fields and/or the join table fields) after joining. Same with ArcMap 
* Selections made to the join table after joining are not reflected in the output table

Filters (aka ArcMap Definition Queries):

Filters made prior to joining:

* Filters made to either the target table or join table prior to the join will be reflected in the output table as long as the target and/or join table is reloaded after the filter and prior to the join (the reload requirement is a known bug).

Filters made after joining:

* At 2.10, filters can be applied to the output table after joining (note that you have to reload the output table, the effect is not dynamic; this is a known bug). ArcMap: Definition Query results are dynamic; the target table is instantly updated.
* In the output table you can filter on the target table fields, but not on the join table fields (to accomplish this with join fields, apply a filter to the join table before joining). ArcMap: you can Definition Query the output table on either the target table fields or the join table fields.

RELATES:

Relates are 1:Many (same as Arcmap)

Use the Relations tool 

* see:
* fulcrumapp.com/blog/using-relations-in-qgis/
* http://blog.vitu.ch/10112013-1201/qgis-relations

a) Create the relation:

- Project Properties > Relations > Add
- referencing layer = the table with the "many" records
- referencing field = the referencing layer's relate field
- referenced layer = the table with the "one" record
- referenced field = the referenced layer's relate field
- id = typically leave blank

b) Then use the QGIS Identify tool. ArcMap uses either the geometry select or attribute select. 

- Make sure that the layer of interest is highlighted in the TOC
- After selecting a feature, a Feature Attributes window will pop up. You get a separate window for each feature selected, and you have to close this window to turn off the id color on the map. Not sure how to export the window's contents.
- I prefer the window's appearance when I click the button to the right that looks like a table.
- I'm stumped by fulcrumapp's descripton of id'ing via the related table "...open the feature form of a maintenance". Didn't work for me...