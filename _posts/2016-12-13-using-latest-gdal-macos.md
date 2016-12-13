---
layout: post
status: publish
published: true
title: "Using the latest GDAL with R packages on macOS"
author: "Alex Chubaty"
date: 2016-12-13
---

I wanted to play around with the new [`sf`](https://cran.r-project.org/package=sf
) package, which requires the latest GDAL (>= 2.0.0), GEOS (>= 3.3.0), and PROJ.4 (>= 4.8.0).
However, the version of GDAL [installed via `brew`]({% post_url 2014-08-05-installing-rgdal-osx %}) is 1.11.4, so I needed to update to the latest version and reinstall a few R packages in order to get `sf` to work on macOS.

## Update GDAL

```bash
## unlink the previous GDAL version
brew unlink gdal

## update GDAL to the latest version (2.1.2)
brew tap osgeo/osgeos4mac
brew install gdal2
brew link --force gdal2
```

## (Re)install R spatial packages

Next, we need to install a few packages from source in order to use the new GDAL libraries:

```r
## (re)install spatial packages from source
install.packages(c("rgeos", "sf", "sp"), type = "source")

## rgdal requires some additional configuration to build correctly:
##   based on http://stackoverflow.com/a/26836125/1380598
install.packages("rgdal", type = "source",
                 configure.args = c("--with-proj-include=/usr/local/include",
                                    "--with-proj-lib=/usr/local/lib"))
library(rgdal) ## confirm the GDAL version being used
```
