# Climate-related Hazard

Mapping the extent of a natural hazard (e.g., assessing areas with a high risk) or disaster is a first step in disaster risk management and emergency response. Subsequently, exposure mapping enables the estimation of the impact of hazards or disasters, for example, regarding the number of affected inhabitants or infrastructure. 

This section describes in detail the methodology and analysis operations required to meet the user requirements of WFP at country or regional level. This is based on extensive search from related journal for impact calculation during the disaster and availability global free data on internet. The following practice shows the use of GIS software (ArcGIS or other GIS Open Source Software) to analyze a disaster extent map in combination with auxiliary data such as population or land cover data.

## Rainfall anomaly

The objective of rainfall anomaly is to evaluate the quality of monthly rainfall over the country. This is achieved through analysis of anomalies, i.e. a comparison against a reference. The classic reference is the long-term average. 

Rainfall anomaly is generated for a 10-day period. The model will calculate the accumulated rainfall and other climate indices of precipitation based on that data during the most recent dekad which has been aggregated from pentad estimates. Every month has three dekads, such that the first two dekads have 10 days (i.e., 1-10, 11-20), and the third is comprised of the remaining days of the month (21-28 or 21-29 or 21-30 or 21-31. Therefore, the length of the third dekad of each month is not consistent and varies from 8-11 days, depending on the length of the month.

The anomaly is calculated based on percentage of the average

Anomaly (%) = $100$ * $\dfrac{x_i}{x_j}$

where $x_i$ is current rainfall and $x_j$ is long-term average of rainfall.

?> The threshold and the symbology for the rainfall anomaly can follow below colorcodes and image.

| Class  | Hex  | RGB  |
|---|---|---|
| <40%  | `#a16622` ![#a16622](https://via.placeholder.com/15/a16622/000000?text=+) | 161, 102, 34  |
| 40-60%  | `#db9835` ![#db9835](https://via.placeholder.com/15/db9835/000000?text=+)  | 219, 152, 53  |
| 60-80%  | `#eec883` ![#eec883](https://via.placeholder.com/15/eec883/000000?text=+)  | 238, 200, 131  |
| 80-90%  | `#fcebb6` ![#fcebb6](https://via.placeholder.com/15/fcebb6/000000?text=+)  | 252, 235, 182  |
| 90-110%  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | 255, 255, 255  |
| 110-120%  | `#caf8f9` ![#caf8f9](https://via.placeholder.com/15/caf8f9/000000?text=+)  | 202, 248, 249  |
| 120-140%  | `#91e0ee` ![#91e0ee](https://via.placeholder.com/15/91e0ee/000000?text=+)  | 145, 224, 238  |
| 140-180%  | `#50b7da` ![#50b7da](https://via.placeholder.com/15/50b7da/000000?text=+)  | 80, 183, 218  |
| +180%  | `#3d78cf` ![#3d78cf](https://via.placeholder.com/15/3d78cf/000000?text=+)  | 61, 120, 207  |


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


?> The threshold and the symbology for the SPI can follow below color codes and image.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| Exceptionally Dry  | -2.00 and above  | `#760005` ![#760005](https://via.placeholder.com/15/760005/000000?text=+)  | 118, 0, 5  |
| Extremely Dry  | -1.99 to -1.60  | `#ec0013` ![#ec0013](https://via.placeholder.com/15/ec0013/000000?text=+)  | 236, 0, 19  |
| Severely Dry  | -1.59 to -1.30  | `#ffa938` ![#ffa938](https://via.placeholder.com/15/ffa938/000000?text=+)  | 255, 169, 56  |
| Moderately Dry  | -1.29 to -0.80  | `#fdd28a` ![#fdd28a](https://via.placeholder.com/15/fdd28a/000000?text=+)  | 253, 210, 138  |
| Abnormally Dry  | -0.79 to -0.51  | `#fefe53` ![#fefe53](https://via.placeholder.com/15/fefe53/000000?text=+)  | 254, 254, 83  |
| Near Normal  | -0.50 to +0.50  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | 255, 255, 255  |
| Abnormally Moist  | +0.51 to +0.79  | `#a2fd6e` ![#a2fd6e](https://via.placeholder.com/15/a2fd6e/000000?text=+)  | 162, 253, 110  |
| Moderately Moist  | +0.80 to +1.29  | `#00b44a` ![#00b44a](https://via.placeholder.com/15/00b44a/000000?text=+)  | 0, 180, 74  |
| Very Moist  | +1.30 to +1.59  | `#008180` ![#008180](https://via.placeholder.com/15/008180/000000?text=+)  | 0, 129, 128  |
| Extremely Moist  | +1.60 to +1.99  | `#2a23eb` ![#2a23eb](https://via.placeholder.com/15/2a23eb/000000?text=+)  | 42, 35, 235  |
| Exceptionally Moist  | +2.00 and above  | `#a21fec` ![#a21fec](https://via.placeholder.com/15/a21fec/000000?text=+)  | 162, 31, 236  |
