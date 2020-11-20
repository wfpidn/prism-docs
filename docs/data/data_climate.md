# Climate

The climate are varies by location and by time of year. Dekad rainfall, daily rainfall forecast and monthly temperature are a few of the many datasets found under our climate section.

## Rainfall

Many research institutions are producing global satellite precipitation estimate, and mostly available for public. Most notably products are CHIRPS, GPM IMERG, and NOAA GEFS. 

### CHIRPS

Climate Hazards Group InfraRed Precipitation with Station data (CHIRPS) from Climate Hazard Center (CHC), Department of Geography, University of California Santa Barbara - https://www.chc.ucsb.edu/data/chirps is a 35+ year quasi-global rainfall data set. Spanning 50°S-50°N (and all longitudes) and ranging from 1981 to near-present, CHIRPS incorporates CHC's in-house climatology, CHPclim, 0.05° resolution satellite imagery, and in-situ station data to create gridded rainfall time series for trend analysis and seasonal drought monitoring. 

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays dekad and monthly rainfall data  |
| Variable  | Total rainfall  |
| Geographic coverage  | Global 50N-50S, 180W-180E |
| Spatial resolution  | 0.05 degree ~ 5.6 km at equator  |
| Temporal resolution  | daily, pentad, dekad, monthly, 2-monthly, 3-monthly and annual  |
| Format  | GeoTIFF, BIL and NetCDF  |
| Unit  | Total mm for given time step, mm/pentad, mm/month, etc.  |
| Source  | https://data.chc.ucsb.edu/products/CHIRPS-2.0/  |
| Reference  | https://wiki.chc.ucsb.edu/CHIRPS_FAQ  |

#### Symbology

?> The threshold and the symbology for the `dekad` rainfall in milimeters can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| No Rain  | `#e1e1e1` ![#e1e1e1](https://via.placeholder.com/15/e1e1e1/000000?text=+) | rgb(225, 225, 225)  |
| 1 to 3  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| 3 to 10  | `#f9f3d5` ![#f9f3d5](https://via.placeholder.com/15/f9f3d5/000000?text=+)  | rgb(249, 243, 213)  |
| 10 to 20  | `#dce2a8` ![#dce2a8](https://via.placeholder.com/15/dce2a8/000000?text=+)  | rgb(220, 226, 168)  |
| 20 to 30  | `#a8c58d` ![#a8c58d](https://via.placeholder.com/15/a8c58d/000000?text=+)  | rgb(168, 197, 141)  |
| 30 to 40  | `#77a87d` ![#77a87d](https://via.placeholder.com/15/77a87d/000000?text=+)  | rgb(119, 168, 125)  |
| 40 to 60  | `#ace8f8` ![#ace8f8](https://via.placeholder.com/15/ace8f8/000000?text=+)  | rgb(172, 232, 248)  |
| 60 to 80  | `#4cafd9` ![#4cafd9](https://via.placeholder.com/15/4cafd9/000000?text=+)  | rgb(76, 175, 217)  |
| 80 to 100  | `#1d5ede` ![#1d5ede](https://via.placeholder.com/15/1d5ede/000000?text=+)  | rgb(29, 94, 222)  |
| 100 to 120  | `#001bc0` ![#001bc0](https://via.placeholder.com/15/001bc0/000000?text=+)  | rgb(0, 27, 192)  |
| 120 to 150  | `#9131f1` ![#9131f1](https://via.placeholder.com/15/9131f1/000000?text=+)  | rgb(145, 49, 241)  |
| 150 to 200  | `#e983f3` ![#e983f3](https://via.placeholder.com/15/e983f3/000000?text=+)  | rgb(233, 131, 243)  |
| +200 and above  | `#f6c7ec` ![#f6c7ec](https://via.placeholder.com/15/f6c7ec/000000?text=+)  | rgb(246, 199, 236)  |

?> The threshold and the symbology for the `monthly` rainfall in milimeters can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| No Rain  | `#e1e1e1` ![#e1e1e1](https://via.placeholder.com/15/e1e1e1/000000?text=+) | rgb(225, 225, 225)  |
| 1 to 20  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| 20 to 40  | `#f9f3d5` ![#f9f3d5](https://via.placeholder.com/15/f9f3d5/000000?text=+)  | rgb(249, 243, 213)  |
| 40 to 60  | `#dce2a8` ![#dce2a8](https://via.placeholder.com/15/dce2a8/000000?text=+)  | rgb(220, 226, 168)  |
| 60 to 80  | `#a8c58d` ![#a8c58d](https://via.placeholder.com/15/a8c58d/000000?text=+)  | rgb(168, 197, 141)  |
| 80 to 100  | `#77a87d` ![#77a87d](https://via.placeholder.com/15/77a87d/000000?text=+)  | rgb(119, 168, 125)  |
| 100 to 125  | `#ace8f8` ![#ace8f8](https://via.placeholder.com/15/ace8f8/000000?text=+)  | rgb(172, 232, 248)  |
| 125 to 150  | `#4cafd9` ![#4cafd9](https://via.placeholder.com/15/4cafd9/000000?text=+)  | rgb(76, 175, 217)  |
| 150 to 200  | `#1d5ede` ![#1d5ede](https://via.placeholder.com/15/1d5ede/000000?text=+)  | rgb(29, 94, 222)  |
| 200 to 250  | `#001bc0` ![#001bc0](https://via.placeholder.com/15/001bc0/000000?text=+)  | rgb(0, 27, 192)  |
| 250 to 300  | `#9131f1` ![#9131f1](https://via.placeholder.com/15/9131f1/000000?text=+)  | rgb(145, 49, 241)  |
| 300 to 350  | `#e983f3` ![#e983f3](https://via.placeholder.com/15/e983f3/000000?text=+)  | rgb(233, 131, 243)  |
| +350 and above  | `#f6c7ec` ![#f6c7ec](https://via.placeholder.com/15/f6c7ec/000000?text=+)  | rgb(246, 199, 236)  |

## Land Surface Temperature

Various satellite data provide land surface temperature as one of the product, Landsat, MODIS Terra Aqua and Sentinel are some of them.

### MODIS

The Moderate Resolution Imaging Spectroradiometer MODIS/Terra Land Surface Temperature and Emissivity 8-Day L3 Global 1 km Grid SIN V006 (MOD11A2) dataset provides global land surface temperature data (LST). The MOD11A2 version 6 product provides an average, 8-day, per-pixel LST  in a 1200 x 1200 kilometer grid. Each pixel value in the MOD11A2 is a simple average of all the corresponding MOD11A1 LST pixels collected within that 8 day period. The 8 day compositing period was chosen because twice that period is the exact ground track repeat period of the Terra and Aqua platforms. 

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays 8-days land surface temperature data  |
| Variable  | Day time temperature  |
| Geographic coverage  | Global |
| Spatial resolution  | 1 km  |
| Temporal resolution  | 8-days  |
| Format  | HDF-EOS  |
| Unit  | Kelvin, with scale factor 0.02.  |
| Source  | https://e4ftl01.cr.usgs.gov/MOLT/MOD11A2.006/  |
| Reference  | https://lpdaac.usgs.gov/products/mod11a2v006/  |

#### Symbology

?> The threshold and the symbology for the `8-days` land surface temperature in degree celcius (°C) can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| -40 and below  | `#b2182b` ![#b2182b](https://via.placeholder.com/15/b2182b/000000?text=+) | rgb(178, 24, 43)  |
| -40 to -30  | `#d6604d` ![#d6604d](https://via.placeholder.com/15/d6604d/000000?text=+)  | rgb(214, 96, 77)  |
| -30 to -20  | `#f4a582` ![#f4a582](https://via.placeholder.com/15/f4a582/000000?text=+)  | rgb(244, 165, 130)  |
| -20 to -10  | `#fddbc7` ![#fddbc7](https://via.placeholder.com/15/fddbc7/000000?text=+)  | rgb(253, 219, 199)  |
| -10 to +10  | `#f7f7f7` ![#f7f7f7](https://via.placeholder.com/15/f7f7f7/000000?text=+)  | rgb(247, 247, 247)  |
| +10 to +20  | `#d1e5f0` ![#d1e5f0](https://via.placeholder.com/15/d1e5f0/000000?text=+)  | rgb(209, 229, 240)  |
| +20 to +30  | `#92c5de` ![#92c5de](https://via.placeholder.com/15/92c5de/000000?text=+)  | rgb(146, 197, 222)  |
| +30 to +40  | `#4393c3` ![#4393c3](https://via.placeholder.com/15/4393c3/000000?text=+)  | rgb(67, 147, 195)  |
| +40 and above  | `#2166ac` ![#2166ac](https://via.placeholder.com/15/2166ac/000000?text=+)  | rgb(33, 102, 172)  |
