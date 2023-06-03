# SFC_scripts

# Docker guide

Here are the steps we took to build and run the image, and then modify ipynbs:
1. build the image via the dockerfile inside the SFC_scripts repo: ```docker build -t python39-jupyter .```
2. start a container via: ```docker run -p 8888:8888 -v $(pwd):/notebooks python39-jupyter```
3. After this, a jupyter notebook session should be started. Directories can now be navigated via the notebook and .ipynbs can be modified.

NOTE: Any modifications done via the docker jupyter session should affect the local files as well


# SFC_scripts guide
This repository contains useful scripts for analysis of vehicle sensor data with the use of Morton and Hilbert SFCs

## LaneChange_Scripts folder:
### adjust_sampling_rate.ipynb

This script can be used to reduce the sampling rate of sensor data from a given csv file.

### Algo_analysis.ipynb

This script contains a generated permutation from a permutational algorithm prototype and its related sensor data

### Morton_analysis.ipynb

This script can be used to experiment in generating Morton values (linear, exponential, bell-shaped, etc.)
and to visualize the resulting unpacked sensor data (Steering wheel angle, Y-Acceleration)

### Morton_CSP_individual.ipynb

This notebook contains visualizations of Morton and Hilbert CSPs, SFC-over-time plots and sensor visualizations.
This notebook can be used for visualizations of noise data and lane change data, as well as removing noise from data.

### Morton_LC_manipulation.ipynb

This script can be used to manipulate Morton values from an input maneuver, and to visualize the 
resulting unpacked sensor data.

### Normalization.ipynb

This script contains the Spike and Contour on-top of heatmap density plots based on
the time dimension's normalizaiton. This script also can be used to normalize several 
given maneuvers with regards to the time dimension. For the most up to date normalization files, kindly
refer to the LaneChange_Scripts/Lane_Change_on_TS.ipynb inside the "LaneChnageNormalization_Renyuan" branch.

### Sensor_manipulation.ipynb

This script can be used to manipulate the amplitude of given maneuver sensor data. For example, given a set of maneuvers
with different steering wheel angle values, it can generate maneuvers with increased and decreased amplitude.

### Simulated_LC_Analysis.ipynb

This script can be used to validate if a given maneuver can be considered a lane change.
It uses the location data from the maneuver to check whether the vehicle performed a one-lane lane change.

## SnowFox_Scripts folder:

### Morton_CSP_individual_SnowFox.ipynb

Same as the LaneChange_Scripts/Morton_CSP_indiviudal.ipynb, but tailored to the SnowFox dataset.

## LaneChange_Scripts/data folder:

### LaneChange_Scripts/data/lane_changes and LaneChange_Scripts/data/lane_changes_updated

These folders contain the lane changes that are referred to as Dataset A in the bachelor thesis project of Group 41

### LaneChange_Scripts/data/2022-09-21_LaneChanges

This folder contains the lane changes that are referred to as Dataset B in the bachelor thesis project of Group 41

### LaneChange_Scripts/data/lane_changes_manipulated

This folder contains a lane change (from Dataset B) with manipulated steering wheel angle amplitudes 