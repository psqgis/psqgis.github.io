---
layout: post
title: "November '17 Meetup Minutes"
date: 2017-11-18
---

The November meeting was held at [Interim CDA](http://interimicda.org/whatwedo/).

• Stu: QGIS Graphical Modeler
	Graphical Modeler:  How to batch process multiple input layers in one tool:
 
- see http://www.qgistutorials.com/en/docs/batch_processing.html
 
Here’s the gist:
1.  At the time of running your model, instead of selecting any input or output layers, click the “Run as batch process” button, upper right in the tool’s window.  This opens up the Batch Processing” window.  Alternatively, simply right-click the tool and select “Execute as batch process”
2.  By default, three input rows are displayed, with the appropriate input and output columns.  In the far left (input) column, click the three dots […].  Browse to the directory containing the input layers.  Select the input layers of interest and click ok.  The input layers auto-populate the Batch Processing window. 
3.  If one of the columns requires that every row be the same layer (say, you wanted to clip all the input layers with the same identical clip layer:
 -  click […] in the first row, navigate to the layer of interest and select it.  That layer is added to the first row.
-  Now, double-click the column header.  The column is now filled in with duplicate values.
4.  For the output, click […] in the first row of the output column.  Navigate to the output layer’s directory.  In the “Save as” window, enter a filename something like “output_ “.  Click Save.
5.   The “Autofill settings” window appears.  Select “Fill with Parameter values” and “Input layer”. 
6.  Note that the output column is autofilled with output filenames that take the form of:
      - output_inputfilename.  Voila!  Run the program and it will batch through the rows.
 
======================================
	○ Want to build a model to predict snowfall
	○ NWS 6-Hour Forecast
	○ QPF*.shp (Poly) - Precipitation
	○ WX*.shp(Poly) -Temperature & winds
		§ Polygon shape file that creates a grid (1 mile squares)
		§ There is bad Geometry in it
			□ Stu has a layer with corrected geometry
	○ Manual Workflow
		§ Reproject
		§ Create Centroids
		§ Spatial join with the corrected geometry
	○ Wouldn't it be cool to automate this?
		§ But I'm not a Python programmer
		§ Try out the QGIS Graphical Modeler
	○ Open Processing Toolbox
		§ Expand Models
			□ Create new model
			□ Can edit existing models
		§ Purple boxes are input
		§ White boxes are tools(algorithms)
		§ Blue(Cyan) boxes are outputs
	○ You can control the order of execution by editing the "parent algorithms"
	○ When you run the model a form comes up with pull downs for the various inputs.
	○ It allows you to specify a location for the outputs. If you don't they won't be saved permanently
	○ Batch mode can be used to run a model multiple times with different inputs and outputs each time
		§ To fill the whole column with the same value, fill the first row and then double click the column header for that column
		§ For output  enter "_test_"
			□ This will be prepended to the input layer name for that output
			□ Select autofill the parameters to fill it down
• Clifford: Building and Address import for Bellingham Washington
	Slide show is [available](https://docs.google.com/presentation/d/e/2PACX-1vSw5hv6Zy90KQJdZEvWeh5Mxk94Hb3GklKcAoaPVPWjCYCni1gDPgAxlgIt4bAPJNUMrpxNviIBMuYH/pub?start=false&loop=false&delayms=3000)
	○ Want to add building heights
	○ Got Lidar from the puget sound lidar consortium
		§ Data available in e00 files
		§ These work with QGIS (really with GDAL)
	○ Everything must be in the same projection
		§ Don't rely on the project on the fly in QGIS
		§ Used Washington Stateplane north
	○ Using GDAL command line tools
	○ Difference between the highest point and bare earth
	○ Calculate the heights using Zonal Statistics
	○ Running into problems with Trees
		§ Attempting to address this using buffered centroids but still having interference from the trees.


If anyone has corrections or additions they would like to make to these notes please let Paul McCombs know, or submit a pull request on [github](https://github.com/psqgis/psqgis.github.io)