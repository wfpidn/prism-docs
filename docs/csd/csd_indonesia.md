# Indonesia: Data

## Rainfall

Indonesia used GPM IMERG data to provide near-real time information on extreme rainfall in daily basis and NOAA GEFS for daily rainfall forecast that could trigger a flood. 

### GPM IMERG

The GPM is next-generation of the Tropical Rainfall Measuring Mission (TRMM - https://pmm.nasa.gov/TRMM). Like the TRMM, the GPM mission aims at providing uniformly calibrated precipitation estimates at a quasi-global scale by merging the measurements from its constellation of microwave and IR satellites. All GPM data sets including measurements obtained from each platform (Level 2) are available on the PMM site (https://pmm.nasa.gov/data-access). Among many GPM products, the Multi-satellitE Retrievals for GPM (IMERG) is most interesting to the users since it delivers the ‘best’ precipitation estimates by combining data obtained from all available microwave and infrared (IR) platforms of the GPM satellite constellation. 

| Characteristic  | Description  |
|---|---|
| Function  | Displays 6-hour and daily precipitation data  |
| Variable  | Total precipitation  |
| Geographic coverage  | Global 60N-60S, 180W-180E |
| Spatial resolution  | 0.1 degree ~ 11.1 km at equator  |
| Temporal resolution  | 30 minutes and daily  |
| Format  | NetCDF  |
| Unit  | Total mm for given time step, mm/hour, mm/day, etc.  |
| Source  | 30-minutes https://disc.gsfc.nasa.gov/datasets/GPM_3IMERGHH_06/summary and Daily: https://disc.gsfc.nasa.gov/datasets/GPM_3IMERGDF_06/summary  |
| Reference  | https://pmm.gsfc.nasa.gov/GPM  |

### NOAA GEFS

The Global Ensemble Forecast System (GEFS), previously known as the GFS Global ENSemble (GENS), is a weather forecast model made up of 21 separate forecasts, or ensemble members. The National Centers for Environmental Prediction ([NCEP](https://www.ncep.noaa.gov)) of NOAA started the GEFS to address the nature of uncertainty in weather observations, which is used to initialize weather forecast models. The GEFS attempts to quantify the amount of uncertainty in a forecast by generating an ensemble of multiple forecasts, each minutely different, or perturbed, from the original observations.

| Characteristic  | Description  |
|---|---|
| Function  | Displays 6-hour and daily precipitation forecast  |
| Variable  | Total precipitation forecast  |
| Geographic coverage  | Global |
| Spatial resolution  | 0.25 degree ~ 27.5 km at equator  |
| Temporal resolution  | Every 6-hour, up to 16-days ahead  |
| Format  | GRIB2  |
| Unit  | Total mm/6-hour.  |
| Source  | https://nomads.ncep.noaa.gov/cgi-bin/filter_gefs_atmos_0p25s.pl  |
| Reference  | https://www.ncdc.noaa.gov/data-access/model-data/model-datasets/global-ensemble-forecast-system-gefs  |

## Vegetation Indices

Vegetation indices, usually produced on 8 or 16-day and monthly intervals and at multiple spatial resolutions, provide consistent spatial and temporal comparisons of vegetation canopy greenness, a composite property of leaf area, chlorophyll and canopy structure. Two vegetation indices are derived from atmospherically-corrected reflectance in the red, near-infrared, and blue wavebands; the normalized difference vegetation index (NDVI), and the enhanced vegetation index (EVI), which minimizes canopy-soil variations and improves sensitivity over dense vegetation conditions. The two products more effectively characterize the global range of vegetation states and processes.

### MODIS

The MOD13Q1 Version 6 product provides Vegetation Index (VI) values at a per pixel basis at 250 meter spatial resolution. There are two primary vegetation layers. The first is the Normalized Difference Vegetation Index (NDVI), which is referred to as the continuity index to the existing National Oceanic and Atmospheric Administration-Advanced Very High Resolution Radiometer (NOAA-AVHRR) derived NDVI. The second vegetation layer is the Enhanced Vegetation Index (EVI), which has improved sensitivity over high biomass regions. The algorithm for this product chooses the best available pixel value from all the acquisitions from the 16 day period. The criteria used is low clouds, low view angle and the highest NDVI/EVI value. 

| Characteristic  | Description  |
|---|---|
| Function  | Displays 16-days vegetation indices data  |
| Variable  | EVI  |
| Geographic coverage  | Global |
| Spatial resolution  | 250 meter  |
| Temporal resolution  | 16-days  |
| Format  | HDF-EOS  |
| Unit  | n/a  |
| Source  | https://e4ftl01.cr.usgs.gov/MOLT/MOD13Q1.006/  |
| Reference  | https://lpdaac.usgs.gov/products/mod13q1v006/  |
