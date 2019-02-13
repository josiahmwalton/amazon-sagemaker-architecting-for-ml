# Bright Idea
Predict the total daily incoming solar energy at 98 Oklahoma Mesonet solar sites, using numerical weather
simulation data, historical measurements of the total daily incoming solar energy at the solar sites, and
attributes of the solar sites themselves.  

# Team Members
- Kwaps
- Simon F.
- Greg P.
- Josiah W.

# Datasets
- train.csv: total daily incoming solar energy in (J m-2) at each solar site that have been in continuous operation since January 1, 1994, measured by a pyranometer every 5 minutes and summed from sunrise to 23:55 UTC of the date listed in each column.
- station_info.csv: data on each solar site, including:
    - latitude
    - longitudes
    - elevation (meters)
- NOAA/ESRL Global Ensemble Forecast System (GEFS) Reforecast Version 2 numerical weather modeling predictions:
    - gefs_elevations.nc: netCDF4 file containing the model elevations of the GEFS grid points
    - gefs_train.zip: all of the GEFS training data for all the GEFS grid points for the time span 1994-01-01 to 2007-12-31. This data include the following files
      - apcp_sfc_latlon_subset_19940101_20071231.nc
          - Variable: apcp_sfc
          - Description: 3-Hour accumulated precipitation at the surface	[kg m^2]
      - dlwrf_sfc_latlon_subset_19940101_20071231.nc
          - Variable: dlwrf_sfc
          - Description: Downward long-wave radiative flux average at the surface	[W m^2]
      - dswrf_sfc_latlon_subset_19940101_20071231.nc
          - Variable: dswrf_sfc
          - Description: Downward short-wave radiative flux average at the surface	[W m^2]
      - pres_msl_latlon_subset_19940101_20071231.nc
          - Variable: pres_msl
          - Description: Air pressure at mean sea level	[Pa]
      - pwat_eatm_latlon_subset_19940101_20071231.nc
          - Variable: pwat_eatm
          - Description: Precipitable Water over the entire depth of the atmosphere	[kg m^2]
      - spfh_2m_latlon_subset_19940101_20071231.nc
          - Variable: spfh_2m
          - Description: Specific Humidity at 2 m above ground	[kg kg-1]
      - tcdc_eatm_latlon_subset_19940101_20071231.nc
          - Variable: tcdc_eatm
          - Description: Total cloud cover over the entire depth of the atmosphere	[%]
      - tcolc_eatm_latlon_subset_19940101_20071231.nc
          - Variable: tcolc_eatm
          - Description: Total column-integrated condensate over the entire atmos.	[kg m^2]
      - tmax_2m_latlon_subset_19940101_20071231.nc
          - Variable: tmax_2m	 
          - Description: Maximum Temperature over the past 3 hours at 2 m above the ground	 [K]
      - tmin_2m_latlon_subset_19940101_20071231.nc
          - Variable: tmin_2m	 
          - Description: Minimum Temperature over the past 3 hours at 2 m above the ground	 [K]
      - tmp_2m_latlon_subset_19940101_20071231.nc
          - Variable: tmp_2m	 
          - Description: Current temperature at 2 m above the ground	 [K]
      - tmp_sfc_latlon_subset_19940101_20071231.nc
          - Variable: tmp_sfc	 
          - Description: Temperature of the surface	 [K]
      - ulwrf_sfc_latlon_subset_19940101_20071231.nc
          - Variable: ulwrf_sfc	 
          - Description: Upward long-wave radiation at the surface	 [W m^2]
      - ulwrf_tatm_latlon_subset_19940101_20071231.nc
          - Variable: ulwrf_tatm	 
          - Description: Upward long-wave radiation at the top of the atmosphere	 [W m^2]
      - uswrf_sfc_latlon_subset_19940101_20071231.nc
          - Variable: uswrf_sfc
          - Description: Upward short-wave radiation at the surface	 [W m^2]
    - gefs_test.zip: all of the GEFS test data for all the GEFS grid points for the time span 2008-01-01 to 2012-11-30. This data include the following files:
        - apcp_sfc_latlon_subset_20080101_20121130.nc
            - Variable: apcp_sfc
            - Description: 3-Hour accumulated precipitation at the surface	[kg m^2]
        - dlwrf_sfc_latlon_subset_20080101_20121130.nc
            - Variable: dlwrf_sfc
            - Description: Downward long-wave radiative flux average at the surface	[W m^2]
        - dswrf_sfc_latlon_subset_20080101_20121130.nc
            - Variable: dswrf_sfc
            - Description: Downward short-wave radiative flux average at the surface	[W m^2]
        - pres_msl_latlon_subset_20080101_20121130.nc
            - Variable: pres_msl
            - Description: Air pressure at mean sea level	[Pa]
        - pwat_eatm_latlon_subset_20080101_20121130.nc
            - Variable: pwat_eatm
            - Description: Precipitable Water over the entire depth of the atmosphere	[kg m^2]
        - spfh_2m_latlon_subset_20080101_20121130.nc
            - Variable: spfh_2m
            - Description: Specific Humidity at 2 m above ground	[kg kg-1]
        - tcdc_eatm_latlon_subset_20080101_20121130.nc
            - Variable: tcdc_eatm
            - Description: Total cloud cover over the entire depth of the atmosphere	[%]
        - tcolc_eatm_latlon_subset_20080101_20121130.nc
            - Variable: tcolc_eatm
            - Description: Total column-integrated condensate over the entire atmos.	[kg m^2]
        - tmax_2m_latlon_subset_20080101_20121130.nc
            - Variable: tmax_2m	 
            - Description: Maximum Temperature over the past 3 hours at 2 m above the ground	[K]
        - tmin_2m_latlon_subset_20080101_20121130.nc
            - Variable: tmin_2m	 
            - Description: Minimum Temperature over the past 3 hours at 2 m above the ground	 [K]
        - tmp_2m_latlon_subset_20080101_20121130..nc
            - Variable: tmp_2m	 
            - Description: Current temperature at 2 m above the ground [K]
        - tmp_sfc_latlon_subset_20080101_20121130..nc
            - Variable: tmp_sfc	 
            - Description: Temperature of the surface	[K]
        - ulwrf_sfc_latlon_subset_20080101_20121130..nc
            - Variable: ulwrf_sfc	 
            - Description: Upward long-wave radiation at the surface	[W m^2]
        - ulwrf_tatm_latlon_subset_20080101_20121130..nc
            - Variable: ulwrf_tatm	 
            - Description: Upward long-wave radiation at the top of the atmosphere	[W m^2]
        - uswrf_sfc_latlon_subset_20080101_20121130..nc
            - Variable: uswrf_sfc
            - Description: Upward short-wave radiation at the surface [W m^2]

# Modeling Strategy
- (Possible) Map each solar site to the close GEFS grid point, using the latitute, longitude, and elevation. Could instead include elevation as a feature.
- Link the historical solar energy measurements with the training GEFS numerical data.
- Use a DeepAR algorithm to forecast the daily solar energy at each Mesonet solar site.
- For model selection and validation, use the test GEFS data and validate the predicted total daily solar energy against the actual values from the same time period.


# Additional Ideas
- Do we need an individual model for each site? DeepAR might let us train these models for each site all in one step.
- Explore/compare DeepAR performance against other modeling approaches for time series analysis techniques like ARIMA, XGBoost, RandomForest, etc. These may perform well on an individual solar site level.
- Take care when creating the train/test data to not perform standard random sampling; we need to preserve correlations in the time series data.

# End Goal
- For a given solar site, predict what the total daily incoming solar energy will be in the short term. "Short term" here will be some number of days into the future, with the total number of days being dependent on the modeling approach used and uncertainties in the predictions.
