---
layout: post
title: "QGIS Joins and Relates"
date: 2015-10-13
---

## JOINS ##

Joins are either 1:1 or Many:1. Same with ArcMap

Joins are made via Layer Properties > Joins

After joining, the target table will display NULL values everywhere when you try to sort any of the fields. Solution: close the output table and then reload, subsequent sorts will be OK. Even subsequent joins will not require a reload.

Prefixes can be added to the output table's join field names, so that they are easily identifiable after the join. This is done in the Add Join dialog box, "Custom field name prefix". ArcMap does not provide for custom prefix names; only the join table name is used as a prefix.

At 2.10 you can edit the join properties, via Layer Properties > Joins > pencil button. The resulting changes are dynamic, reflected immediately in the output table's display. Not available in ArcMap.

A single individual join table can be simultaneously joined to multiple target tables.

Joins cannot be chained (join table joined to target table 1, which in turn is joined to target table 2)

### Outer and Inner joins: ###

#### Outer joins: ####

* QGIS joins are always outer from the target table's perspective; that is, if a target table record does not have a matching record in the join table, the record is still displayed in the output table, with NULL values in the join fields (same with ArcMap). 

#### Inner joins: ####

* To do an inner join, make the initial outer join, then select (see "Selections" below) the output table for target table>join field = join table>join field*. The selected records now represent an inner join.
* QGIS, by default, does not display join table>join field. To override this default, in the Add Join dialog box, click "Choose which fields are joined, and then click the join table>join field. It will now display in the output table, and you can do your select.
* QGIS joins are always inner from the join table's perspective; the output attribute table will not include non-matching records from the join table. Same with ArcMap

### Selections: ###

#### Selections made prior to joining: ####

* Join does not recognize records selected (either in the target table or in the join table) prior to the join. Same with ArcMap 

#### Selections made after joining: ####

* Spatial and/or attribute selections may be made on the output table (either on the target table fields and/or the join table fields) after joining. Same with ArcMap 
* Selections made to the join table after joining are not reflected in the output table

### Filters (aka ArcMap Definition Queries): ###

#### Filters made prior to joining: ####

* Filters made to either the target table or join table prior to the join will be reflected in the output table as long as the target and/or join table is reloaded after the filter and prior to the join (the reload requirement is a known bug).

#### Filters made after joining: ####

* At 2.10, filters can be applied to the output table after joining (note that you have to reload the output table, the effect is not dynamic; this is a known bug). ArcMap: Definition Query results are dynamic; the target table is instantly updated.
* In the output table you can filter on the target table fields, but not on the join table fields (to accomplish this with join fields, apply a filter to the join table before joining). ArcMap: you can Definition Query the output table on either the target table fields or the join table fields.

## RELATES: ##

Relates are 1:Many (same as Arcmap)

### Use the Relations tool ###

See:
* [Using Relations In QGIS](http://fulcrumapp.com/blog/using-relations-in-qgis/)
* [QGIS Relations](https://web.archive.org/web/20160313201132/http://blog.vitu.ch/10112013-1201/qgis-relations)

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
