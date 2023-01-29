# Bachelor-Thesis
Klassifikation von Modellbewölkung in einer 1,000-Member Ensemble Simulation

-- .ipynb files to analyse and plot data of ECMWF and SCALE-RM 1000 member ensemble simulation --

-------------------------------------------------------------------------------------------------
Works on srvx1 with 'Enstools v2021.11-3.8' Kernel
SCALE-RM data available on 29.05.2016 12:00 UTC and 01.06.2016 12:00 UTC
ECMWF data available from 27.05.2016 00:00 UTC to 10.06.2016 12:00 UTC
-------------------------------------------------------------------------------------------------

1)  scalerm_cloud_w_phase.ipynb

  - Loads data to analyse clouds, vertical wind and water phase

  - Calculates following variables:
    1. p_cloud: Probability of at least one cloud in a data column over the whole ensemble
    2. ex_cloud: Number of cloudy levels in a data column. Interpreted as the vertical extent of one cloud, since the results of an exact calculation are the same but much slower.
    3. ctl: Level of the cloud top (0-20)
    4. ctp: Cloud Top Pressure level (975hPa-100hPa)
    5. w: Vertical wind data (means over ensemble, levels and both are used)
    6. phase: Cloud water phase (liquid, ice)

  - Classification of variables into following groups:
    1. cloud status: classification of cloud probability (p_cloud)
       thresholds: 5% and 95%
    2. cloud top: classification of cloud top pressure (ctp)
       thresholds: 700hPa and 300hPa
    3. ex_cloud_high/medi/low: classification of cloud extent (ex_cloud)
       thresholds: 2 levels and 10 levels


2)  scalerm_theta_prec.ipynb

  - Loads data to analyse temperature, stability and precipitation

  - Calculates following variables:
    1. stab: Stability, calculated between the level above and below with log in denominator
    2. stab1: Stability, calculated between the level above and below without log in denominator
    3. stab2: Stability, calculated between 350hPa and 750hPa
    4. prec: Precipitation
    5. prec_max: Maximum Precipitation of the whole ensemble at every point in domain
    6. prec_prob: Precipitaion probability, definition of precipitation is 0.1mm/h

  - Classification:
    1. prec_prob_high/medi/low: Classification of precipitation probability


3) scalerm_hist.ipynb

  - Loads data to plot histograms of cloud variables, vertical wind, stability and precipitation     (All variables above)

  - 2-D histograms to analyse relations between different variables

  - 1-D histograms to analyse distributions of different variables


4) ecmwf_plots.ipynb

  - Loads ECMWF data from 27.05.2016 00:00 UTC to 10.06.2016 12:00 UTC

  - Plots following variables:
    1. Geopotential 500hPa
    2. Mean sea level pressure
    3. Horizontal wind 300hPa
    4. Divergence 300hPa
    5. Specific humidity 850hPa
    6. Relative humidity 850hPa
    7. Temperature 850hPa
    8. Equivalentpotential temperature 850hPa

