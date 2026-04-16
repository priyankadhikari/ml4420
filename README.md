# Predicting Avocado Spoilage Risk and Loss Drivers in California 
Priyanka Adhikari, Ruchira Banerjee, Nidhi Bendre - DS4420 Final Project


## Overview
The goal of this project is to explore how climate factors drive food spoilage and ultimately affect economic outcomes. To make the analysis more focused, we concentrate on California, the largest producer of fruits and vegetables in the U.S. We further narrowed our analysis to avocados, as, according to the Climate Hubs of the U.S. Department of Agriculture, California produces over 90% of US-grown avocados, and they are grown year-round, providing a consistent and continuous time series for analysis.

This project applies three machine learning models to predict avocado crop spoilage risk in California using historical crop insurance claims and climate data spanning  2001–2018. The models address the problem from complementary angles: predicting insurance claim magnitude, forecasting monthly loss rate over time, and classifying the climate-driven cause of each loss event.


## Data
We pulled from two sources and joined them on month and year:
- **USDA RMA Cause of Loss archives**: crop insurance claims with indemnity amounts, acres lost, damage cause, county, and growth stage  
- **NOAA Climate at a Glance**: monthly statewide climate summaries for California including temperature, precipitation, degree days, and PDSI 

## Models
- **Bayesian Regression (R)**: predicts log-transformed insurance claim amounts using climate variables and determined acres, with random intercepts for damage cause, county, growth stage, and month
- **ARIMA (Python)**: forecasts monthly avocado loss rate over time, capturing the volatile spike-driven nature of insurance claims
- **MLP (Python, manual NumPy implementation)**: classifies the climate-driven damage cause behind each loss event across 7 categories including heat, freeze, wind, and cold wet weather

## Results
The Bayesian model achieved an R² of 0.31 and RMSE of 1.55, identifying determined acres as the strongest predictor. The ARIMA(20,1,20) model reached a test MAE of 237.99 and RMSE of 289.27, capturing the timing and magnitude of loss spikes reasonably well. The MLP achieved 50.68% test accuracy across 7 damage cause classes with strongest performance on climatically distinct causes like heat (66%), freeze (64%), and cold wet weather (60%).

