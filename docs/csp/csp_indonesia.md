# Indonesia: Product

Mapping the extent of a natural hazard (e.g., assessing areas with a high risk) or disaster is a first step in disaster risk management and emergency response. Subsequently, exposure mapping enables the estimation of the impact of hazards or disasters, for example, regarding the number of affected inhabitants or infrastructure. 

This section describes in detail the methodology and analysis operations required to meet the user requirements of WFP at country or regional level. This is based on extensive search from related journal for impact calculation during the disaster and availability global free data on internet. 

## Consecutive Dry Days

The number of consecutive dry days (CDD) is the largest number of consecutive days with daily precipitation amount less than 1 mm (or depending on the rain days criteria of the country), within a certain time. Usually the process counts the number of days in the past 90 days to measure the drought level.

### How it works

Calculate the number of rain days based on the threshold and calculate the count of the most recent days since a rain day or the most recent consecutive string of days that meet the threshold criteria is summed.

Threshold criteria: 1, 2.5, 5, 10 and 20 milimeters of rainfall

```
IF previousCDD == null THEN previousCDD == 0
ELSEIF todayRAIN > 1 AND previousCDD == 0 THEN previousCDD + 1
```

CDD derived from IMERG data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays daily CDD  |
| Variable  | CDD  |
| Geographic coverage  | Indonesia 7N-12S, 94E-142E |
| Spatial resolution  | 0.1 degree ~ 11.1 km at equator  |
| Temporal resolution  | Daily  |
| Format  | GeoTIFF  |
| Unit  | Number of day  |

#### Symbology

?> The threshold and the symbology for the CDD can follow below color codes and image.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| No Drought  | 0  | `#cccccc` ![#cccccc](https://via.placeholder.com/15/cccccc/000000?text=+)  | rgb(204, 204, 204)  |
| Very Short  | 1 - 5  | `#ffe5d9` ![#ffe5d9](https://via.placeholder.com/15/ffe5d9/000000?text=+)  | rgb(255, 229, 217)  |
| Short  | 6 - 10  | `#fcbba2` ![#fcbba2](https://via.placeholder.com/15/fcbba2/000000?text=+)  | rgb(252, 187, 162)  |
| Moderate  | 11 - 20  | `#fc9272` ![#fc9272](https://via.placeholder.com/15/fc9272/000000?text=+)  | rgb(252, 146, 114)  |
| Long  | 21 - 30  | `#fa6948` ![#fa6948](https://via.placeholder.com/15/fa6948/000000?text=+)  | rgb(250, 105, 72)  |
| Very Long  | 31 - 60  | `#de2c26` ![#de2c26](https://via.placeholder.com/15/de2c26/000000?text=+)  | rgb(222, 44, 38)  |
| Extreme Drought  | +60  | `#a60f14` ![#a60f14](https://via.placeholder.com/15/a60f14/000000?text=+)  | rgb(166, 15, 20)  |


## Consecutive Wet Days

The number of consecutive wet days (CWD) is similar to the above CDD, the largest number of consecutive days with daily precipitation amount more than 1 mm (or depend on the rain days criteria of the country), within a certain time. Usually the process counts the number of days in the past 90 days to measure the wet level.

### How it works

Calculate the number of rain days based on the threshold and calculate the count of the most recent days since a dry day or the most recent consecutive string of days that meet the threshold criteria is summed.

Threshold criteria: 1, 2.5, 5, 10 and 20 milimeters of rainfall

```
IF previousCWD == null THEN previousCWD == 0
ELSEIF todayRAIN < 1 AND previousCWD == 0 THEN previousCWD + 1
```

CWD derived from IMERG data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays daily CWD  |
| Variable  | CWD  |
| Geographic coverage  | Indonesia 7N-12S, 94E-142E |
| Spatial resolution  | 0.1 degree ~ 11.1 km at equator  |
| Temporal resolution  | Daily  |
| Format  | GeoTIFF  |
| Unit  | Number of day  |

#### Symbology

?> The threshold and the symbology for the CWD can follow below color codes and image.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| No Rainfall  | 0  | `#cccccc` ![#cccccc](https://via.placeholder.com/15/cccccc/000000?text=+)  | rgb(204, 204, 204)  |
| Very Short  | 1 - 5  | `#ffffcc` ![#ffffcc](https://via.placeholder.com/15/ffffcc/000000?text=+)  | rgb(255, 255, 204)  |
| Short  | 6 - 10  | `#c6e8b3` ![#c6e8b3](https://via.placeholder.com/15/c6e8b3/000000?text=+)  | rgb(198, 232, 179)  |
| Moderate  | 11 - 20  | `#7eccba` ![#7eccba](https://via.placeholder.com/15/7eccba/000000?text=+)  | rgb(126, 204, 186)  |
| Long  | 21 - 30  | `#41b7c4` ![#41b7c4](https://via.placeholder.com/15/41b7c4/000000?text=+)  | rgb(65, 183, 196)  |
| Very Long  | 31 - 60  | `#2c80b8` ![#2c80b8](https://via.placeholder.com/15/2c80b8/000000?text=+)  | rgb(44, 128, 184)  |
| Extreme Wet  | +60  | `#253494` ![#253494](https://via.placeholder.com/15/253494/000000?text=+)  | rgb(37, 52, 148)  |


## EVI anomaly

The objective is to evaluate the monthly deviation of vegetation over the country. This is achieved through analysis of Anomalies, (i.e. a comparison against a reference). Enhanced Vegetation Index (EVI) is used instead of the Normalized Difference Vegetation Index (NDVI) as it is more sensitive to changes in areas having high biomass, it reduces the influence of atmospheric conditions on vegetation index values, and it corrects for canopy background signals. 

The anomaly is calculated based on percentage of the average

Anomaly (%) = $100$ * $\dfrac{x_i}{x_j}$

where $x_i$ is current EVI and $x_j$ is long-term average of EVI.

EVI anomaly derived from MODIS MOD13Q1 data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays 16-days EVI anomaly data  |
| Variable  | EVI anomaly  |
| Geographic coverage  | Indonesia 7N-12S, 94E-142E  |
| Spatial resolution  | 250m at equator  |
| Temporal resolution  | 16-days.  |
| Format  | GeoTIFF  |
| Unit  | Percent (%)  |

#### Symbology

?> The threshold and the symbology for the `16-days` EVI anomaly can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| 50% and below  | `#6a2b0e` ![#6a2b0e](https://via.placeholder.com/15/6a2b0e/000000?text=+) | rgb(106, 43, 14)  |
| 50 to 70%  | `#e06c2c` ![#e06c2c](https://via.placeholder.com/15/e06c2c/000000?text=+)  | rgb(224, 108, 44)  |
| 70 to 80%  | `#ebb049` ![#ebb049](https://via.placeholder.com/15/ebb049/000000?text=+)  | rgb(235, 176, 73)  |
| 80 to 90%  | `#e5db9e` ![#e5db9e](https://via.placeholder.com/15/e5db9e/000000?text=+)  | rgb(229, 219, 158)  |
| 90 to 110%  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| 110 to 120%  | `#d6fb57` ![#d6fb57](https://via.placeholder.com/15/d6fb57/000000?text=+)  | rgb(214, 251, 87)  |
| 120 to 130%  | `#6fec48` ![#6fec48](https://via.placeholder.com/15/6fec48/000000?text=+)  | rgb(111, 236, 72)  |
| 130 to 150%  | `#3f8b48` ![#3f8b48](https://via.placeholder.com/15/3f8b48/000000?text=+)  | rgb(63, 139, 39)  |
| 150% and above  | `#1e4b10` ![#1e4b10](https://via.placeholder.com/15/1e4b10/000000?text=+)  | rgb(30, 75, 16)  |



## Impact analysis

Over the last decade, more than 16 600 natural disasters occurred in Indonesia, with an average 1700 disasters annually. Hydro-meteorological weather events cause 95 percent of these disasters, with floods, landslides and strong winds occurring most frequently. 

Indonesia’s food systems are frequently disrupted by natural disasters. Apart from causing high human, environmental and economic costs, these extreme weather events can stress food and nutrition security, through adverse effects on food availability and access, and on nutrition situation. Extreme weather and natural disasters destroy assets, land, crops, livestock and food stock. They often make markets and supplies unreachable or unaffordable.

However, despite the importance of assessing the impacts of damages and losses in the aftermath of such events, estimating impacts is timely and challenging. 
By automating data acquisition and processing, the VAMPIRE platform provides immediate estimates of: 
- The priority areas that are likely affected by floods or drought; 
- Number of people that is likely affected by floods and drought, and
- Crops that are likely affected by floods and drought (in hectares). 

The drought estimates are available in near-real time (1 day ago from today); while flood impact estimates are provided 3 days ahead. 

The impact estimates presented in the system use spatial analysis done by overlaying (1) estimated geographic area exposed to dry (drought) or wet (flood) season, with (2) number of people in the affected area or crop area in the affected zone. 

### Dry Season

#### Population

Impact on population shows the number of people living in an area that has been exposed to extreme drought in the past 90 days. The indicator overlays population density with the extreme drought exposure defined by number of days since last rainfall (for extreme drought, it is more than consecutive 60 days without rain). 

Data for the drought exposure is derived from the days since last rain indicator from the Integrated Multi-satellitE Retrievals for GPM (IMERG) dataset. Population density is derived from the Facebook dataset. 

#### Crops

The Crops affected layer refers to a crop area (in hectares) that has been exposed to extreme drought in the past 16 days. The indicator combines the exposure of an area to extreme drought (defined as less than 10 of VHI value) and a crop mask in the exposed area. The identified areas are at a risk of drought impact on crops. 

Data for the drought exposure is derived from the Vegetation Health Index from MODIS dataset. Crop extent uses the MODIS crop mask.

### Wet Season

#### Population

Impact on population shows the number of people living in an area which is forecasted to be affected by extreme rainfall that could trigger a floods in the next 1 to 5 days. The indicator overlays population density with the extreme rainfall triggering flood forecast for all alert categories to calculate the number of people affected by flood. 

Data for extreme rainfall forecast is derived from the NOAA Global Forecast System and NASA GPM IMERG. Population density is derived from the Facebook dataset. 

#### Crops

The layer refers to a crop area (in hectares) which is forecasted to be affected by extreme rainfall that could trigger a floods in the next 1 to 5 days. The indicator overlays population density with the extreme rainfall triggering flood forecast for all alert categories with a crop mask for the area with detected alert in the next 1 to 5 days.  

Data for extreme rainfall is derived from the NOAA Global Forecast System and NASA GPM IMERG. Crop extent uses the MODIS crop mask.

