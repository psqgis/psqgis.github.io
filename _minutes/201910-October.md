---
layout: post
title: "October '19 Meetup Minutes"
date: 2019-10-10
tags: grass fuzzy-match joins learning arcscene esri-alternative lidar point-cloud snohomish-county geopackage photography facebook machine-learning computational-linguistics 3D quickmapservices qgis2threejs structure-from-motion augmented-reality sqlite spatialite well-known-text well-known-binary mapilary openstreetcam importphotos artificial intelligence rapidid
---

Covered Topics:
* Troubles Using Grass Tools
* Fuzzy Table Joins
* Recomendations for Learning QGIS
* QGIS alternative to ArcScene
* Augmented Reality
* GeoPackages
* Street Level Photographs
* Facebook & Machine Learning

The October meeting was held at [Interim CDA](http://interimicda.org/whatwedo/). Thanks as always for their generous use of their conference room. We had a good crowd with seven people attending, including three first timers.

### Troubles Using [GRASS](https://grass.osgeo.org/) Tools
Clifford says the last time he upgraded QGIS on MacOS, the GRASS tools stopped working. Paul checked his MacOS installation and discoved that while there were no errors raised, the GRASS tool he tested ran and ran for several minutes on a small set of data and did not return a result.

### Fuzzy Table Joins
Stu sent in an interesting article on [fuzzy table joins](https://spatialthoughts.com/2019/09/26/fuzzy-table-joins-in-qgis/) to share with the group:
> I came across this QGIS article today. It looked way cool; I haven't tried it yet, but I can visualize cases where I might.
> Please forward it to the group.

The article describes using computational linguistics to match words and names that are similar but not identical.

### Recomendations for Learning QGIS
1. Peter reccomended the [book](https://locatepress.com/dq3) that he shared in [August 2019](/minutes/201908-August).

2. Fred reccomended checking out Safari Books Online in Seattle library. He doesn't generally reccomend Packt because the quality is highly variable, but this book he reccomends. Anita Grazer is a QGIS developer.
   + On Seattle Public Library site: [spl.org](https://www.spl.org/)
   + Click on Online Resource -> A-Z online resources
   + Scroll down to Safari Books Online, click and log in using your Seattle Public Library Credentials.
   + Search for *Learn QGIS - Fouth Edition* by Anita Grazer

### QGIS alternative to ArcScene! Everything done in QGIS.
Stu sent provided this awesome example of an [interactive 3D visualization](http://truenorthgis.org/qgis_examples/3d_boreholes/index.html):

> The location is in Alaska, just NW of the village of Iliamna.
> 
> DEM data from ArcticDEM, BING satellite overlay via the [QGIS Quick Map Services plugin](https://qms.nextgis.com/about). Borehole point vector data from a project I worked on years ago, stored in a Geopackage.
> 
> Visualization and html creation via the [Qgis2threejs plugin](https://qgis2threejs.readthedocs.io/en/docs/). *VERY* easy to work with.
> 
> Use your mouse to rotate the scene in 3D
> 
> http://truenorthgis.org/qgis_examples/3d_boreholes/index.html

> Yay open source!

### Augmented Reality
Nat explained his current interest in [augmented reality](https://en.wikipedia.org/wiki/Augmented_reality) which led to a discussion of several related topics:
1. Nat is looking for a way to obtain the Lidar Point Cloud data for Souther Snohomish County. The problem is successfully downloading the 24GB file for all of southern Snowhomish County from [Washington DNR LIDAR Portal](https://lidarportal.dnr.wa.gov/).
2. Clifford suggested he contact Mike Rosen who has demonstrated feature detection from LIDAR at a [CUGOS Meeting](https://cugos.org/meetings/2018-03-21/).
3. Peter offered to provide a link about using mobile phones to do structure from motion.
4. Nat has been using [Reality Capture](https://www.capturingreality.com/) and [Meshroom](https://meshroom-manual.readthedocs.io/en/latest/) (which is much slower).
5. Peter has used [WebODM](https://www.opendronemap.org/webodm/) with photos captured by a camera on a pole.
6. The use of laser scanners, which can be rented from survey equipment companies.

### GeoPackages
Fred shared his use and understanding of GeoPackages. 
- [GeoPackages](https://www.geopackage.org/) area a GIS Data format built ontop of [SqLite](https://www.sqlite.org/index.html).
  - SqLite is a file based database where the database logic is embedded in the applications that access the database.
- QGIS lets you run [SpatiaLite functions](https://www.gaia-gis.it/fossil/libspatialite/index) on data in the GeoPackage.
  - To do that you must tell SqLite that it is dealing with GeoPackage geometry.
- GeoPackages are better than just using SpatiaLite because the data type is closer to the [well-known text and well-known binary](https://en.wikipedia.org/wiki/Well-known_text_representation_of_geometry) data formats, and you can store raster data as well as vector.

### Street Level Photographs
Clifford has been running a dashcam and submitting to [Mapilary](https://www.mapillary.com/) and [OpenStreetCam](https://openstreetcam.org/map/). He wrote a shell script to create the geolocated photos using the video and GPS tracks created by the dashcam. Code is available on Clifford's [GitHub account](https://github.com/cliffordsnow/roav2geojpeg). He found the QGIS plugin [ImportPhotos](https://plugins.qgis.org/plugins/ImportPhotos/) which allows him to display his geolocated photos symbolized with an image icon on the map. You can make a shapefile (or GeoPackage) which contains pointers to the local images that you select using the plugin. 

### Facebook & Machine Learning
Casey shared news that Facebook has an artificial intelligence/machine learning project [RapidID](https://mapwith.ai) to assist people in adding roads to [OpenStreetMap](https://www.openstreetmap.org).

### Future Topic
Fred plans to share his method to make custom SVG symbols at a future meeting..
 
