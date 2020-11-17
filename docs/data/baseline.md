# Baseline

An effective disaster management system requires collection of baseline data that is comprehensive, accurate, timely, and accessible. Without these characteristics, an effective, economical, and task- oriented disaster management system cannot be achieved. This section focuses on baseline data collection and impact calculation for specific disasters, which can be defined as the scope and nature of the overall informational resources needed to prepare for and respond to a variety of disasters. What is presently required is a clear understanding of the characteristics of current information resources, their functional capabilities, and their use for disaster management.

## Population

Global mapping of population is rapidly growing in recent years. They are available at detailed spatial scales. The analysis is based on satellite or other geospatial data layers. Population data are necessary for the analysis of impacts of population growth, monitor population changes, and intervention planning.

### Landscan

The LandScan Global Population Database is developed at the Department of Energy's [Oak Ridge National Laboratory](https://landscan.ornl.gov). The data represents finest resolution global population distribution database available. LandScan is known as a highly practical application in humanitarian affairs because it provides most reliable population distribution model.

| Characteristic  | Description  |
|---|---|
| Function  | Visualized population density on the dashboard  |
| Variable  | Total population  |
| Geographic coverage  | Global  |
| Spatial resolution  | The 30 arc-second cell, or 0.008333333 decimal degrees, represents approximately 1 km2 near the equator  |
| Temporal resolution  | Annual  |
| Format  | ESRI grid format and an ESRI binary raster format  |
| Unit  | The values of the cells are integer population counts representing an average, or ambient, population distribution  |
| Source  | https://landscan.ornl.gov/landscan-datasets  |
| Reference  | https://landscan.ornl.gov/documentation  |

### Facebook

To create high-resolution population maps, Facebook use machine learning techniques to identify buildings from commercially available satellite images. Then work with partners at Columbia University to overlay general population estimates based on publicly available census data and other population statistics. The resulting maps are the most detailed and actionable tools available for aid and research organizations.

| Characteristic  | Description  |
|---|---|
| Function  | a proxy for impact analysis  |
| Variable  | Total population, Men, Women, Under 5, Youth 15-24, Women of reproductive ages 15-49, Elderly 60+  |
| Geographic coverage  | Global  |
| Spatial resolution  | 30 meter/pixel  |
| Temporal resolution  | n/a (Year estimation is 2019)  |
| Format  | GeoTIFF  |
| Unit  | Population counts at 30m resolution  |
| Source  | https://data.humdata.org/organization/facebook  |
| Reference  | https://dataforgood.fb.com/docs/high-resolution-population-density-maps-demographic-estimates-documentation/  |


## Croplands

Land cover maps represent spatial information on different types (classes) of physical coverage of the Earth's surface, e.g. forests, grasslands, croplands, lakes, wetlands. Cropland includes areas used for the production of adapted crops for harvest. Two subcategories of cropland are recognized: cultivated and non-cultivated. Cultivated cropland comprises land in row crops or close-grown crops and also other cultivated cropland, for example, hay land or pasture land that is in a rotation with row or close-grown crops. Non-cultivated cropland includes permanent hay land and horticultural cropland.

### GFSAD30

The [GFSAD30](https://geography.wr.usgs.gov/science/croplands/index.html) is a NASA-funded project to provide high-resolution global cropland data and their water use that contributes towards global food security in the twenty-first century. The GFSAD30 products are derived through multi-sensor remote sensing data (e.g., Landsat, MODIS, AVHRR), secondary data, and field-plot data and aims at documenting cropland dynamics from 1990 to 2017.

| Characteristic  | Description  |
|---|---|
| Function  | a proxy for impact analysis  |
| Variable  | Crop extent  |
| Geographic coverage  | Global  |
| Spatial resolution  | 30 meter/pixel  |
| Temporal resolution  | n/a (Year estimation is 2015)  |
| Format  | GeoTIFF  |
| Unit  | n/a  |
| Source  | [Southeast and Northeast Asia](https://lpdaac.usgs.gov/products/gfsad30seacev001/)  |
| Reference  | https://lpdaac.usgs.gov/documents/168/GFSAD30SEACE_User_Guide_V1.pdf  |
