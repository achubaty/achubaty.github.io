---
layout: post
status: publish
published: true
title: ! "Installing rgdal on OSX"
author: Alex Chubaty
date: 2014-08-05
---

This is actually really easy to do, but most of the google hits I came across were old (from 2010) or horribly complex (building `gdal` and `proj4` from source then building `rgdal` itself).

First, this assumes you already have `homebrew` installed [^1]. If not, see [http://brew.sh/](http://brew.sh/) for the one-liner terminal install.

Next, install `rgdal`:

```
brew install rgdal
```

Then open `RStudio` (for some reason it didn't work using R in the terminal...) and install the package from source:

```
install.packages("rgdal", type="source")
```

That's it. Seriously easy.

[^1]: If you use `macports` the process is similarly simple. See [here](http://www.janosgyerik.com/installing-rgdal-in-r-on-os-x-mavericks/).
