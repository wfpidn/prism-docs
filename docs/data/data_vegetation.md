# Vegetation

Various satellite data provide vegetation indices as one of the product, Landsat, MODIS Terra Aqua and Sentinel are some of them.

## Vegetation Indices

Vegetation indices, usually produced on 8 or 16-day and monthly intervals and at multiple spatial resolutions, provide consistent spatial and temporal comparisons of vegetation canopy greenness, a composite property of leaf area, chlorophyll and canopy structure. Two vegetation indices are derived from atmospherically-corrected reflectance in the red, near-infrared, and blue wavebands; the normalized difference vegetation index (NDVI), and the enhanced vegetation index (EVI), which minimizes canopy-soil variations and improves sensitivity over dense vegetation conditions. The two products more effectively characterize the global range of vegetation states and processes.

### MODIS

The MOD13A2 Version 6 product provides Vegetation Index (VI) values at a per pixel basis at 1 kilometer (km) spatial resolution. There are two primary vegetation layers. The first is the Normalized Difference Vegetation Index (NDVI), which is referred to as the continuity index to the existing National Oceanic and Atmospheric Administration-Advanced Very High Resolution Radiometer (NOAA-AVHRR) derived NDVI. The second vegetation layer is the Enhanced Vegetation Index (EVI), which has improved sensitivity over high biomass regions. The algorithm for this product chooses the best available pixel value from all the acquisitions from the 16 day period. The criteria used is low clouds, low view angle and the highest NDVI/EVI value. 

| Characteristic  | Description  |
|---|---|
| Function  | Displays 16-days vegetation indices data  |
| Variable  | NDVI  |
| Geographic coverage  | Global |
| Spatial resolution  | 1 km  |
| Temporal resolution  | 16-days  |
| Format  | HDF-EOS  |
| Unit  | n/a  |
| Source  | https://e4ftl01.cr.usgs.gov/MOLT/MOD13A2.006/  |
| Reference  | https://lpdaac.usgs.gov/products/mod13a2v006/  |