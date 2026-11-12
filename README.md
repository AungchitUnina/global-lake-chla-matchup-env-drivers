# global-lake-chla-matchup-env-drivers
# Dataset for Global Chla Prediction in Inland Lakes: Sentinel-2 Matchups and Environmental Drivers

This repository contains the datasets used in the study: **Estimating Chlorophyll-a across Inland Lakes using Sentinel-2 Spectral Features and Environmental Predictors**. The dataset integrates in-situ Chlorophyll-a (Chla) measurements, Sentinel-2 spectral features, and environmental drivers (meteorology, land cover, and lake geometry) for global inland lakes. It includes both the internal dataset for model training and independent external datasets for transferability testing.

## 📂 Dataset Description

### 1. Internal Data (Training & Cross-Validation)
*   **`Internal_matchup.csv`**: The final, cleaned dataset of matched in-situ Chla and Sentinel-2 observations used for model training.
*   **`Internal_info.csv`**: Metadata for the internal matchups (e.g., seasons, coordinates, dates, lake types, regions).
*   **Scenario Files:** The full feature datasets for all tested scenarios (e.g., `BIF30daysclimate250mbuffer.csv`).
    *   *Naming convention:* `[FeatureSet][MetWindow]climate[LC]buffer.csv`
    *   *Feature sets:* BIF (Band Index Features) or BRF (Band Ratio Features).
    *   *Met windows:* 7Days, 30Days, Delta.
    *   *Buffers:* 250m, 500m, 2km, 5km.

### 2. External Data (Independent Testing)
Independent datasets from Brazil, France, China, and New Zealand.
*   **`External_matchup.csv`**: The independent in-situ Chla observations.
*   **`External_info.csv`**: Metadata for the external samples.
*   **`External_BIF.csv` / `External_BRF.csv`**: Extracted Sentinel-2 spectral features for the external samples.
*   **`External_LC.xlsx`**: Extracted land cover metrics for the external lakes (across different buffer sizes).
*   **`External_Meteorology.xlsx`**: Extracted meteorological variables for the external samples (across different time windows).



## 🌍 Relevant Data Sources

### In-Situ Water Quality Data
Relevant water quality databases include:

| Database | Region | Online Repository | Reference |
| :--- | :--- | :--- | :--- |
| Global Lakes Water Quality Database | Global | [https://github.com/roohollahnoori/AWQDFGL/](https://github.com/roohollahnoori/AWQDFGL/) | Naderian et al., 2024 |
| Global Freshwater Quality Database (GEMStat) | Global | [https://gemstat.org/data-gemstat/](https://gemstat.org/data-gemstat/) | - |
| Water Quality Portal (WQP) | United States | [https://www.waterqualitydata.us/](https://www.waterqualitydata.us/) | - |
| European Environment Agency (EEA) Waterbase | Europe | [https://www.eea.europa.eu/en/](https://www.eea.europa.eu/en/) | - |
| Open Government Portal of Canada | Canada | [https://search.open.canada.ca/opendata/](https://search.open.canada.ca/opendata/) | - |
| Heterogeneous Data Platform for Operational Modeling and Forecasting of Swiss lakes | Switzerland | [https://www.datalakes-eawag.ch/](https://www.datalakes-eawag.ch/) | - |

### Environmental Driver Data

| Driver Category | Variables | Spatial/Temporal Resolution | Online Repository | Reference |
| :--- | :--- | :--- | :--- | :--- |
| **Regional Meteorology** (ERA5-Land reanalysis) | Air temperature, Precipitation, Solar radiation, Wind speed | ~9 km / Hourly | [https://cds.climate.copernicus.eu/](https://cds.climate.copernicus.eu/) | Muñoz-Sabater et al., 2021 |
| **Land Cover** (Dynamic World V1) | Bare, Crops, Grass, Shrub, Snow, Tree, Urban, Water, Wetland | 10 m / Near-Real Time (every 2-5 days) | [https://dynamicworld.app/explore](https://dynamicworld.app/explore) | Brown et al., 2022 |
| **Lake Geometry** (HydroLAKES) | Surface area, Depth, Elevation, Latitude | Lake-specific (Static) | [https://www.hydrosheds.org/products/hydrolakes](https://www.hydrosheds.org/products/hydrolakes) | Messager et al., 2016 |
| **Seasonal Cycle** | Month | Sample-specific (Static) | - | - |
