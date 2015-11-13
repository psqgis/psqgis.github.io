---
layout: post
title: "November Meetup Minutes"
date: 2015-11-12
---

The Puget Sound QGIS user's group met Tuesday November 10th at the Lakewood Library.

We had five members in attendance and opened the meeting with a discussion of business Topics.

* We have 62 members but get 5 to 8 people at meetings.
* Holding the meeting further south did not increase attendance like we hoped.
* We discussed moving to a location with food and drink, perhaps attracting more people to the meetings.
* With more than 50 members, Meetup.com costs $15/month.
* Stu Smith will charge a small amount of money to each member.
	* $12/year
	* This will cover the cost of meetup.com and may generate enough money to rent a room occasionally for the meetups.
* Christie Heaton of [MaptimeSEA](http://maptimesea.github.io/) wants to do a QGIS series for Maptime and is looking for Volunteers to teach QGIS.
		* John Murphy is interested in doing a lesson on geocoding.
* Riley Love from Amazon let us know they are hiring a [Sr. Geo Data Engineer](https://us-amazon.icims.com/jobs/355672/sr.-geo-data-engineer/job?mobile=false&width=747&height=1200&bga=true&needsRedirect=false&jan1offset=-480&jun1offset=-420).

First time attendee Will Thomas asked for an orientation to QGIS. Stu filled him in with a brief history of GIS software and how QGIS came to be. Stu also mentioned that [GIS Stack Exchange](http://gis.stackexchange.com/) was a great place to ask questions and browse for interesting ideas on how to use QGIS.

Paul McCombs gave a presentation: [Exploring Relations in QGIS](http://www.lazym8.com/datawrangler/qgis_relations).

* Paul used data available from the King County Washington GIS data portal for the presentation.
* Paul still had some questions unanswered that we were able to figure out in the meeting. The presentation slides have been updated to include that information.
* John Murphy was interested in finding out more about using the expression window that is available in the Relation widget on the Attribute form, and may give us an update at a future meetup.

John showed us how to use the Print Composer to produce a paper or digital output map. He used a handbook written by PSQGIS member Bob Catherman as a resource for his demonstration. That [handbook](/downloads/HealthCare-GIS-Handbook-E-3-6.doc) is available on the PSQGIS [Resource](/resources.html) page.

* From the Project menu, select New Print Composer.
* First thing to do:
	* From the Layout menu, select Add Map
	* Draw rectangle to place map on page
* You can add:
	* Titles
	* North Arrow/Compass Rose
	* Text
	* Legend
	* Table
* For text adjust: Fonts, text alignment, etc.
* John will send a link to a compass rose tutorial he found online.
* If you need a rotated compass rose, you can use Add arrow, which is a simple graphic arrow, but can be rotated.
* Add HTML places a screen shot of a web page as a graphic object on the map.
* For objects on the map you can group objects and adjust their draw order.
* Use commands on the Atlas menu to make a page for each feature in a layer.
* Export the map as an image, PDF, or SVG.

Stu lead a discussion of EPSG codes that are used to specify map projections in QGIS.

* EPSG stands for European Petroleum Standards Group.
* Check out the projections documented on [SpatialReference.org](http://spatialreference.org/)
	* Search for "Washington" to see the options in our area.
* Data downloaded from Pierce and King County provides meta data that specifies the projection, but QGIS doesn't recognize it. So you have to select the correct projection manually. Clifford Snow thinks there is a way to improve QGIS's recognition of projections.
* Pierce County uses NAD83(HARN)/Washington South (ftUS) - EPSG:2927
* King County uses NAD83(HARN)/Washington South (ftUS) - EPSG:2927

Clifford demonstrated how to convert a layer.

* Bring the layer in to QGIS and specify the correct projection for it's initial state.
* Select all the features of the layer.
* Go to Layer Menu -> Save As…
	* Select the Format you want it saved in.
	* Name it in the Save as field.
	* Click on the button to the right of the CRS pull down list to browse projections not on the pull down list.
	* Pick the projection you want it to be in (WGS84 for the demonstration)
	* Click OK to reproject and save the layer.

Agenda for the next meetup:

* Clifford: How to get QGIS to recognize County stateplane projections, if he can figure it out.
* Clifford: Open Street Map question and answer session. Stu has questions.
* All: QGIS question and answer session.