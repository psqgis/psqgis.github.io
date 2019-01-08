---
layout: post
title: "November '18 Meetup Minutes"
date: 2018-11-13
tags: street-network routing qneat king-county
---

Covered Topics:
* Street Network Routing
* King County Street Data

The November meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks again for their generous use of their conference room.

### Street Network Routing ###

* John has been studying GIS using ArcGIS and doing some routing analysis of the street network to determine driving time to Master Gardener Clinics.
  * They are interested is using software that is more cost sustainable.
  * Looking into using the Google Map
    * Peter suggested that they may be better off using Mapbox Studio rather than Google Map to make a web map showing where their clinics are.
  * Wondering if there is a solution with QGIS.
    * Check out QNEAT3 Plugin for QGIS 3 https://root676.github.io/index.html
      * Shortest Path (Dijkstra) between two points (pairs of coordinates obtained by using QGIS-GUI)
      * Origin-Destination Matrices Matrix between all points of a layer.
      * ISO-Area Algorithms Algorithms for isochrone area calculation (pointcloud, interpolation-based raster, contours and polygon)

### King County Street Data ###

  * Asked about one-way street data from King County. He couldn't find it.
    * Metro Transportation Network (TNET) in King County / trans network line
    * CAR_FLOW is the field. 0 means bidirectional. 1 or 2 means one-way. It's not explicit in the metadata but one means with the direction of the line feature and the other means against it.
