---
layout: post
title: "April Meetup Minutes"
date: 2016-04-26
---
* Organizational Issues
    * Peter Keum suggested we discontinue dues on Meetup.com but collect money in person.
    * Peter also suggested we set aside time to discuss topics for meetings.

* Web Mapping - The Group
    * Stu Smith lead a group exploration of the [qgis2web](https://plugins.qgis.org/plugins/qgis2web/) plugin.
        * His map had a Google terrain basemap and a point layer of orca whale sitings.
        * The plugin can publish as [OpenLayers 3](http://openlayers.org/) or [Leaflet](http://leafletjs.com/)
            * Evan Derickson explained:
                * The OpenLayers framework came first and has tons of features.
                * The Leaflet framework came later and is designed to get most of the features while using fewer resources. Leaflet feels snappier.
        * Run the Plugin from the Web menu.
            * Select the layers that you want to include.
            * It Doesn't seem like the Google basemap will work as it doesn't show up in the preview window.
            * There are other basemaps to choose from. You can select multiple basemaps and the web page will let the user choose among them.
            * Select an output folder.
            * "Mapping library location":
                * Choose local if you want to have the library locally or choose CDN if you want to get the library from the project web site.
                * CDN may result in a faster loading page, due to superior web host qualities and if the user is using the same library from multiple sites it may be pre-cached.
            * There are lots of map elements to choose from.
            * Leaflet has a always displayed legend and OpenLayers 3 has a rollover pop-up legend.
            * Export sends the files needed to host your map to the directory you've selected.
            * Leaflet has a bug, and requires the use of a transparent border for rendering polygons without visible borders. Not drawing the border at all prevents the map files from being created.
            * Creates the data as a javascript snipit not exactly a geojson file
    * Other plugins
        * QGIS Cloud Plugin's [website](http://qgiscloud.com/) acts as your host. 65 Euros/month
        * [Lizmap](http://www.3liz.com/en/lizmap.html)'s pricing is in French. It might start at 45 Euros.
* PSQGIS's Plans for the future:
    * Document an entire work flow from OSM data to a finished product.
    * Create a translation guide from ESRI ArcMap to QGIS.
    * Reach out to students and non-profits.
* Suggestions for next month:
    * Clifford Snow will go through different ways to extract OSM data.
        * Use [Overpass](http://wiki.openstreetmap.org/wiki/Overpass_API) to get real time data for specific tags.
    * Stu Smith will demo [Time Manager Plugin](https://plugins.qgis.org/plugins/timemanager/)