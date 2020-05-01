---
category: Spatial Weights
path: '/stuff/:id'
title: 'Create Queen Weights'
type: 'v0.0.1'

layout: nil
---


To create a queen contiguity weights, PostGeoDa will use the **geometry** column 
(e.g. **the_geom** or **wkb_geometry**) and feature id column  (e.g. **gid** or **ogc_fid**)
from a spatial data table. 

Reference: [Loading GIS (Vector) Data using PostGIS](https://postgis.net/docs/manual-2.1/using_postgis_dbmanagement.html#shp2pgsql_usage)

**The SQL function is:**

`geoda_weights_queen(
        fid integer, 
        geom bytea|geometry, 
        order integer default 1, 
        inc_lower boolean default FALSE
)`

**The input parameters are:**

* fid integer: the feature id of geometry, e.g. **gid** or **ogc_fid**
* geom geometry|bytea: the geometry, e.g. **the_geom** or **wkb_geometry**
* order integer default 1: order of contiguity
* inc_lower boolean default FALSE: if include lower order neighbors

**Return:**

* bytea: the weights is returned in Postgresql's binary data type

**Example:**

To create a Queen contiguity weights using feature id "ogc_fid" and geometry 
"wkb_geometry" with default "order of contiguity" value 1 from a spatial data table 
[natregimes](https://geodacenter.github.io/data-and-lab/natregimes/):

```test=# SELECT geoda_weights_queen(ogc_fid, wkb_geometry) 
       FROM natregimes; 
(Output)
        geoda_weights_queen
---------------------------------------------
 \x610d0c0000010000000300170000001f00000029...
```