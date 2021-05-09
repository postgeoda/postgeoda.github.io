---
description: 'Xun Li (@lixun910), Luc Anselin'
---

# PostGeoDa

_**Run spatial data analysis simply using SQL in your PostgreSQL database!!  🚀**_

## Introduction

PostGeoDa is a PostgreSQL extension for spatial data analysis. PostGeoDa is developed using C/C++ based on the [libgeoda](https://github.com/geodacenter/libgeoda) library. By utilizing and the database architecture of PostgreSQL and the spatial index in PostGIS, PostGeoDa has the ability to handle real big spatial data.

```sql
-- Create Queen contiguity weights
SELECT queen_weights(gid, the_geom) OVER() FROM natregimes;

-- Apply local Moran statistics
SELECT local_moran(hr60, queen_weights) OVER() FROM natregimes;

-- Apply spatial regionalization SKATER
SELECT skater(ARRAY[hr60, dv60, ue60], queen_weights) OVER() FROM natregimes;
```

{% hint style="success" %}
 PostGeoDa is a free and open-sourced library. It is released under the GNU General Public License \(GPLv2 or later\). PostGeoDa is developed by [Xun Li ](https://lixun910.github.io)and Luc Anselin. 
{% endhint %}

## Why PostGeoDa? 🤔

* PostGeoDa is the first spatial data analysis extension of PostgreSQL to power spatial data services for cloud mapping platforms.
* PostGeoDa offers many features of spatial data analysis that run efficiently in PostgreSQL, so there is no need to spend extra time transferring geometries over the network.
* PostGeoDa has no dependencies. But it is designed to work with PostGIS to handle big spatial data.

{% hint style="info" %}
If you prefer running spatial data analysis in browser, please check out [jsgeoda](https://www.npmjs.com/package/jsgeoda).  
If you prefer running spatial data analysis in Python, please check out [pygeoda](https://geodacenter.github.io/pygeoda).  
If you prefer running spatial data analysis in R, please check out [rgeoda](https://geodacenter.github.io/rgeoda). 
{% endhint %}

## Contents

* **Installation** 
* **1 Map Classification** 
  * Basic Mapping
  * Rate Mapping
  * Spatial Rate Mapping
* **2 Spatial Weights** 
  * Contiguity-Based Weights
  * Distance-Based Weights
  * Kernel Weights
* **3 Local Spatial Autocorrelation** 
  * Local Moran
  * Local Geary
  * Local Getis-Ord G
  * Local Join Count
  * Quantile LISA
* **4 Local Spatial Autocorrelation - Multivariate**
  * Local Neighbor Match Test
  * Multivariate Local Geary
  * Bivariate Local Join Count
  * Multivariate  Local Join Count
  * Multivariate Quantile LISA
* **5 Spatial Clustering** 
  * SKATER
  * REDCAP
* **6 Cluster Analysis** 
  * HDBSCAN
  * Fast K-Medoids

### 

