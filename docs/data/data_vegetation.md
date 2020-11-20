# Vegetation

Various satellite data provide vegetation indices as one of the product, Landsat, MODIS Terra Aqua and Sentinel are some of them.

## Vegetation Indices

Vegetation indices, usually produced on 8 or 16-day and monthly intervals and at multiple spatial resolutions, provide consistent spatial and temporal comparisons of vegetation canopy greenness, a composite property of leaf area, chlorophyll and canopy structure. Two vegetation indices are derived from atmospherically-corrected reflectance in the red, near-infrared, and blue wavebands; the normalized difference vegetation index (NDVI), and the enhanced vegetation index (EVI), which minimizes canopy-soil variations and improves sensitivity over dense vegetation conditions. The two products more effectively characterize the global range of vegetation states and processes.

### MODIS

The MOD13A2 Version 6 product provides Vegetation Index (VI) values at a per pixel basis at 1 kilometer (km) spatial resolution. There are two primary vegetation layers. The first is the Normalized Difference Vegetation Index (NDVI), which is referred to as the continuity index to the existing National Oceanic and Atmospheric Administration-Advanced Very High Resolution Radiometer (NOAA-AVHRR) derived NDVI. The second vegetation layer is the Enhanced Vegetation Index (EVI), which has improved sensitivity over high biomass regions. The algorithm for this product chooses the best available pixel value from all the acquisitions from the 16 day period. The criteria used is low clouds, low view angle and the highest NDVI/EVI value. 

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays 16-days vegetation indices data  |
| Variable  | NDVI  |
| Geographic coverage  | Global |
| Spatial resolution  | 1 km  |
| Temporal resolution  | 16-days  |
| Format  | HDF-EOS  |
| Unit  | n/a, Scale factor 0.0001  |
| Source  | https://e4ftl01.cr.usgs.gov/MOLT/MOD13A2.006/  |
| Reference  | https://lpdaac.usgs.gov/products/mod13a2v006/  |

#### Symbology

?> The threshold and the symbology for the `16-days` NDVI can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| 0 and below  | `#002596` ![#002596](https://via.placeholder.com/15/002596/000000?text=+) | rgb(0, 37, 150)  |
| 0 to 0.05  | `#752a27` ![#752a27](https://via.placeholder.com/15/752a27/000000?text=+)  | rgb(117, 42, 39)  |
| 0.06 to 0.10  | `#b4672a` ![#b4672a](https://via.placeholder.com/15/b4672a/000000?text=+)  | rgb(180, 103, 42)  |
| 0.11 to 0.15  | `#f3a63b` ![#f3a63b](https://via.placeholder.com/15/f3a63b/000000?text=+)  | rgb(243, 166, 59)  |
| 0.16 to 0.25  | `#f6c042` ![#f6c042](https://via.placeholder.com/15/f6c042/000000?text=+)  | rgb(246, 192, 66)  |
| 0.26 to 0.35  | `#fffd54` ![#fffd54](https://via.placeholder.com/15/fffd54/000000?text=+)  | rgb(255, 253, 84)  |
| 0.34 to 0.42  | `#bdfb50` ![#bdfb50](https://via.placeholder.com/15/bdfb50/000000?text=+)  | rgb(189, 251, 80)  |
| 0.43 to 0.50  | `#8af94d` ![#8af94d](https://via.placeholder.com/15/8af94d/000000?text=+)  | rgb(138, 249, 77)  |
| 0.51 to 0.58  | `#64d640` ![#64d640](https://via.placeholder.com/15/64d640/000000?text=+)  | rgb(100, 214, 64)  |
| 0.59 to 0.66  | `#4ba52f` ![#4ba52f](https://via.placeholder.com/15/4ba52f/000000?text=+)  | rgb(75, 165, 47)  |
| 0.67 to 0.74  | `#33741f` ![#33741f](https://via.placeholder.com/15/33741f/000000?text=+)  | rgb(51, 116, 31)  |
| 0.75 to 1  | `#1f4d11` ![#1f4d11](https://via.placeholder.com/15/1f4d11/000000?text=+)  | rgb(31, 77, 17)  |
