# Climate-related Hazard

Mapping the extent of a natural hazard (e.g., assessing areas with a high risk) or disaster is a first step in disaster risk management and emergency response. Subsequently, exposure mapping enables the estimation of the impact of hazards or disasters, for example, regarding the number of affected inhabitants or infrastructure. 

This section describes in detail the methodology and analysis operations required to meet the user requirements of WFP at country or regional level. This is based on extensive search from related journal for impact calculation during the disaster and availability global free data on internet. 




## Rainfall (ratio) anomaly

The objective of rainfall anomaly is to evaluate the quality of monthly rainfall over the country. This is achieved through analysis of anomalies, i.e. a comparison against a reference. The classic reference is the long-term average. 

Rainfall anomaly is generated based on dekad data. The model will calculate the accumulated rainfall and other climate indices of precipitation based on that data during the most recent dekad which has been aggregated from pentad estimates. Every month has three dekads, such that the first two dekads have 10 days (i.e., 1-10, 11-20), and the third is comprised of the remaining days of the month (21-28 or 21-29 or 21-30 or 21-31. Therefore, the length of the third dekad of each month is not consistent and varies from 8-11 days, depending on the length of the month.

The anomaly is calculated based on percentage of the average

Anomaly (%) = $100$ * $\dfrac{x_i}{x_j}$

where $x_i$ is current rainfall and $x_j$ is long-term average of rainfall.

Rainfall anomaly derived from CHIRPS data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays dekad and monthly rainfall anomaly data  |
| Variable  | Rainfall anomaly  |
| Geographic coverage  | Global 50N-50S, 180W-180E |
| Spatial resolution  | 0.05 degree ~ 5.6 km at equator  |
| Temporal resolution  | dekad, 1-month, 3-month, 6-month, 9-month and 12-month, rolling by dekad.  |
| Format  | GeoTIFF  |
| Unit  | Percent (%)  |

#### Symbology

?> The threshold and the symbology for the rainfall anomaly can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| 40% and below  | `#a16622` ![#a16622](https://via.placeholder.com/15/a16622/000000?text=+) | rgb(161, 102, 34)  |
| 40 to 60%  | `#db9835` ![#db9835](https://via.placeholder.com/15/db9835/000000?text=+)  | rgb(219, 152, 53)  |
| 60 to 80%  | `#eec883` ![#eec883](https://via.placeholder.com/15/eec883/000000?text=+)  | rgb(238, 200, 131)  |
| 80 to 90%  | `#fcebb6` ![#fcebb6](https://via.placeholder.com/15/fcebb6/000000?text=+)  | rgb(252, 235, 182)  |
| 90 to 110%  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| 110 to 120%  | `#caf8f9` ![#caf8f9](https://via.placeholder.com/15/caf8f9/000000?text=+)  | rgb(202, 248, 249)  |
| 120 to 140%  | `#91e0ee` ![#91e0ee](https://via.placeholder.com/15/91e0ee/000000?text=+)  | rgb(145, 224, 238)  |
| 140 to 180%  | `#50b7da` ![#50b7da](https://via.placeholder.com/15/50b7da/000000?text=+)  | rgb(80, 183, 218)  |
| 180% and above  | `#3d78cf` ![#3d78cf](https://via.placeholder.com/15/3d78cf/000000?text=+)  | rgb(61, 120, 207)  |




## Standardized Precipitation Index

The Standardized Precipitation Index (SPI) is a normalized index representing the probability of occurrence of an observed rainfall amount when compared with the rainfall climatology over a long-term period. This long-term record is fitted to a probability distribution, which is then transformed into a normal distribution so that the mean SPI for the location and desired period is zero.

Negative SPI values represent rainfall deficit and less than median precipitation (Dry), starts when the SPI value is equal or below -1.0. Whereas positive SPI values indicate rainfall surplus and greater than median precipitation (Wet), starts when the SPI value is equal or above 1.0, and ends when the value becomes negative.

### How it works
- Precipitation is normalized using a probability distribution function so that values of SPI are actually seen as standard deviations from the median.
- A normalized distribution allows for estimation of both dry and wet periods.
- Accumulated values can be used to analyse drought severity (magnitude).
- At least 30 years of continuous monthly precipitation data are needed but longer-term records would be preferable.
- SPI timescale intervals shorter than 1 month and longer than 24 months may be unreliable.
- It is spatially invariant in its interpretation.
- Its probability-based nature (probability of observed precipitation transformed into an index) makes it well suited to risk management and triggers for decision-making.

Python packages [climate-indices](https://pypi.org/project/climate-indices/) developed by [U.S. Drought Portal](https://www.drought.gov/drought/python-climate-indices) used to calculate the index.

SPI derived from CHIRPS data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays SPI-1, SPI-2, SPI-3, SPI-6, SPI-9, SPI-12 and SPI-24  |
| Variable  | SPI  |
| Geographic coverage  | Global 50N-50S, 180W-180E |
| Spatial resolution  | 0.05 degree ~ 5.6 km at equator  |
| Temporal resolution  | 1-month, 3-month, 6-month, 9-month, 12-month and 24-month, rolling by dekad.  |
| Format  | GeoTIFF  |
| Unit  | n/a  |

#### Symbology

?> The threshold and the symbology for the SPI can follow below color codes and image.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| Exceptionally Dry  | -2.00 and below  | `#760005` ![#760005](https://via.placeholder.com/15/760005/000000?text=+)  | rgb(118, 0, 5)  |
| Extremely Dry  | -2.00 to -1.50  | `#ec0013` ![#ec0013](https://via.placeholder.com/15/ec0013/000000?text=+)  | rgb(236, 0, 19)  |
| Severely Dry  | -1.50 to -1.20  | `#ffa938` ![#ffa938](https://via.placeholder.com/15/ffa938/000000?text=+)  | rgb(255, 169, 56)  |
| Moderately Dry  | -1.20 to -0.70  | `#fdd28a` ![#fdd28a](https://via.placeholder.com/15/fdd28a/000000?text=+)  | rgb(253, 210, 138)  |
| Abnormally Dry  | -0.70 to -0.50  | `#fefe53` ![#fefe53](https://via.placeholder.com/15/fefe53/000000?text=+)  | rgb(254, 254, 83)  |
| Near Normal  | -0.50 to +0.50  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| Abnormally Moist  | +0.50 to +0.70  | `#a2fd6e` ![#a2fd6e](https://via.placeholder.com/15/a2fd6e/000000?text=+)  | rgb(162, 253, 110)  |
| Moderately Moist  | +0.70 to +1.20  | `#00b44a` ![#00b44a](https://via.placeholder.com/15/00b44a/000000?text=+)  | rgb(0, 180, 74)  |
| Very Moist  | +1.20 to +1.50  | `#008180` ![#008180](https://via.placeholder.com/15/008180/000000?text=+)  | rgb(0, 129, 128)  |
| Extremely Moist  | +1.50 to +2.00  | `#2a23eb` ![#2a23eb](https://via.placeholder.com/15/2a23eb/000000?text=+)  | rgb(42, 35, 235)  |
| Exceptionally Moist  | +2.00 and above  | `#a21fec` ![#a21fec](https://via.placeholder.com/15/a21fec/000000?text=+)  | rgb(162, 31, 236)  |




## LST (difference) anomaly

The objective is to evaluate the monthly deviation of temperature over the country. This is achieved through analysis of Anomalies, (i.e. a comparison against a reference). 

The anomaly is calculated based on difference of the average.

LST anomaly (°C) = $LST - LSTavg$

where:
- $LST$ is the current value of LST
- $LSTavg$ is the long-term average value of LST.

LST and LST long-term average derived from MODIS data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays 8-days LST anomaly data  |
| Variable  | LST anomaly  |
| Geographic coverage  | Global  |
| Spatial resolution  | 1 km at equator  |
| Temporal resolution  | 8-days.  |
| Format  | GeoTIFF  |
| Unit  | Degrees Celcius (°C)  |

#### Symbology

?> The threshold and the symbology for the `8-days` land surface temperature difference anomaly in degree celcius (°C) can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| -10 and below  | `#b2182b` ![#b2182b](https://via.placeholder.com/15/b2182b/000000?text=+) | rgb(178, 24, 43)  |
| -10 to -5  | `#d6604d` ![#d6604d](https://via.placeholder.com/15/d6604d/000000?text=+)  | rgb(214, 96, 77)  |
| -5 to -2  | `#f4a582` ![#f4a582](https://via.placeholder.com/15/f4a582/000000?text=+)  | rgb(244, 165, 130)  |
| -2 to -1  | `#fddbc7` ![#fddbc7](https://via.placeholder.com/15/fddbc7/000000?text=+)  | rgb(253, 219, 199)  |
| -1 to +1  | `#f7f7f7` ![#f7f7f7](https://via.placeholder.com/15/f7f7f7/000000?text=+)  | rgb(247, 247, 247)  |
| +1 to +2  | `#d1e5f0` ![#d1e5f0](https://via.placeholder.com/15/d1e5f0/000000?text=+)  | rgb(209, 229, 240)  |
| +2 to +5  | `#92c5de` ![#92c5de](https://via.placeholder.com/15/92c5de/000000?text=+)  | rgb(146, 197, 222)  |
| +5 to +10  | `#4393c3` ![#4393c3](https://via.placeholder.com/15/4393c3/000000?text=+)  | rgb(67, 147, 195)  |
| +10 and above  | `#2166ac` ![#2166ac](https://via.placeholder.com/15/2166ac/000000?text=+)  | rgb(33, 102, 172)  |




## Temperature Condition Index

The Temperature Condition Index (VCI) compares the current LST to the range of values observed in the same period in previous years. The TCI is expressed in % and gives an idea where the observed value is situated between the extreme values (minimum and maximum) in the previous years. TCI used to determine stress on vegetation caused by temperatures and excessive wetness. Conditions are estimated relative to the maximum and minimum temperatures and modified to reflect different vegetation responses to temperature.

The TCI is calculated using the equation, 

$TCI$ = $100$ * $\dfrac{LSTmax - LST}{LSTmax - LSTmin}$

where:
- $LST$ is the current value of LST
- $LSTmin$ is the long-term minimum value of LST.
- $LSTmax$ is the long-term maximum value of LST.

LST max and min derived from MODIS data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | a proxy for Vegetation Health Index calculation  |
| Variable  | TCI  |
| Geographic coverage  | Global  |
| Spatial resolution  | 1 km at equator  |
| Temporal resolution  | 16-days.  |
| Format  | GeoTIFF  |
| Unit  | Percent (%)  |




## NDVI anomaly

The objective is to evaluate the monthly deviation of vegetation over the country. This is achieved through analysis of Anomalies, (i.e. a comparison against a reference). 

The anomaly is calculated based on percentage of the average

Anomaly (%) = $100$ * $\dfrac{x_i}{x_j}$

where $x_i$ is current NDVI and $x_j$ is long-term average of NDVI.

NDVI and NDVI long-term average derived from MODIS data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays 16-days NDVI anomaly data  |
| Variable  | NDVI anomaly  |
| Geographic coverage  | Global  |
| Spatial resolution  | 1 km at equator  |
| Temporal resolution  | 16-days.  |
| Format  | GeoTIFF  |
| Unit  | Percent (%)  |

#### Symbology

?> The threshold and the symbology for the NDVI anomaly can follow below colorcodes and image.

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




## Vegetation Condition Index

The Vegetation Condition Index (VCI) compares the current NDVI to the range of values observed in the same period in previous years. The VCI is expressed in % and gives an idea where the observed value is situated between the extreme values (minimum and maximum) in the previous years. Lower and higher values indicate bad and good vegetation state conditions, respectively. The VCI associates with moisture condition of vegetation

The anomaly is calculated based on percentage of the average

$VCI$ = $100$ * $\dfrac{NDVI - NDVImin}{NDVImax - NDVImin}$

where:
- $NDVI$ is the current value of NDVI
- $NDVImin$ is the long-term minimum value of NDVI
- $NDVImax$ is the long-term maximum value of NDVI.

NDVI long-term max and min derived from MODIS data

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | a proxy for Vegetation Health Index calculation  |
| Variable  | VCI  |
| Geographic coverage  | Global  |
| Spatial resolution  | 1 km at equator  |
| Temporal resolution  | 16-days.  |
| Format  | GeoTIFF  |
| Unit  | Percent (%)  |


## Vegetation Health Index

Vegetation Health Index (VHI) is based on a combination of (i) Vegetation Condition Index (VCI): associates with moisture condition of vegetation; and (ii) Temperature Condition Index (VCI): associates with thermal condition of vegetation. 

The VCI is constructed using the NDVI and land surface temperature (LST) for TCI. The VHI is effective enough to be used as proxy data for monitoring vegetation health, drought, moisture, thermal condition, etc.

After computing the VCI and TCI values, the final index for agricultural drought is 
$VHI$ = $0.5 * (TCI + VCI)$

#### About the data

| Characteristic  | Description  |
|---|---|
| Function  | Displays 16-days VHI data  |
| Variable  | VHI  |
| Geographic coverage  | Global  |
| Spatial resolution  | 1 km at equator  |
| Temporal resolution  | 16-days.  |
| Format  | GeoTIFF  |
| Unit  | n/a  |

#### Symbology

?> The threshold and the symbology for the VHI can follow below colorcodes and image.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| No Drought  | 40 and above  | `#b2b2b2` ![#b2b2b2](https://via.placeholder.com/15/b2b2b2/000000?text=+) | rgb(178, 178, 178)  |
| Mild Drought  | 30 to 40  | `#ffe5d9` ![#ffe5d9](https://via.placeholder.com/15/ffe5d9/000000?text=+)  | rgb(255, 229, 217)  |
| Moderate Drought  | 20 to 30  | `#fcaf92` ![#fcaf92](https://via.placeholder.com/15/fcaf92/000000?text=+)  | rgb(252, 175, 146)  |
| Severe Drought  | 10 to 20  | `#fa6948` ![#fa6948](https://via.placeholder.com/15/fa6948/000000?text=+)  | rgb(250, 105, 72)  |
| Extreme Drought  | 10 and below  | `#cc181e` ![#cc181e](https://via.placeholder.com/15/cc181e/000000?text=+)  | rgb(204, 24, 30)  |
