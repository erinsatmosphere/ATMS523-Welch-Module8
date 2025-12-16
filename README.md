# ATMS 523 Final Project: Seasonal Variability of Ocean Swell Heights Affecting the Hawaiian Islands (1993–2024)
### Erin Welch

### Data Sources:

- ERA5 Reanalysis – Single-Level Monthly Means
    - Variables: significant wave height (swh), mean wave direction (mwd), mean wave period (mwp)
    - Domain: 30°N–10°N, 170°W–150°W
    - Period: 1993–2024
    - DOI: https://doi.org/10.24381/cds.adbb2d47
    - **This data was obtained through the Copernicus Climate Data Store (cdsapi) but the downloaded data will be provided on Github for convenience**

- NOAA CPC Oceanic Niño Index (ONI)
    - Source: https://www.cpc.ncep.noaa.gov/data/indices/oni.ascii.txt
    - ONI is derived from ERSSTv5 (Huang et al. 2017; DOI: 10.7289/V5T72FNM)

### Requirements & Environment:

This project was developed and tested using **Python 3.13.5**

All required packages listed below are required and compatible with Python ≥3.10:

xarray
numpy
pandas
matplotlib
cartopy
scipy
cdsapi
statsmodels
urllib.request
sklearn

### Objectives:

- Compute seasonal (DJF) wave-height climatology around Hawaiʻi
- Derive ENSO-phase composites of DJF significant wave height using ERA5 and ONI
- Quantify differences in Hs between El Niño and La Niña winters
- Examine a time series of DJF Hs near the North Shore of Oʻahu to identify ENSO-related variability

##### Methods overview:

- Retrieve ERA5 wave fields and compute seasonal means using quarterly resampling
- Download official ONI values, extract DJF seasons, and classify ENSO phases
- Align ERA5 seasonal years with ONI by applying a +1 year shift
- Construct DJF composites for El Niño, La Niña, and composite differences
- Analyze regional climatology and point-based Hs variability