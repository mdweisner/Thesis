# Thesis

The final draft of the thesis can be found at http://www.columbia.edu/~mw2931/thesis.pdf

This directory contains the code to recreate the models and graphs of my thesis: THE PREDICTIVE POWER OF PARTICULATE MATTER: EXAMINING PREDICTIVE RELATIONSHIPS OF NEW YORK CITY AIR POLLUTION, WEATHER, AND THE S&P 500 RETURNS.

The order in which they should be run is as follows:

1. Manhattan API Data Collection - Final.Rmd
-- This file collects data on air pollution from Manhattan, primarily PM2.5, Ozone, and Carbon Monoxide.
-- This file also collects weather data from Laguardia Airport

2. Queens Data API Collection - Final.Rmd
-- This file collects on air pollution from Queens to fill in missing data for Ozone and Carbon Monoxide.

3. Inter Intra Day Data Prep with Queens Data.Rmd
-- This file organizes all of the data and calculates the appropriate aggregated values and variables, following the original study.

4. Inter Intra Joined data Time Series Tests.Rmd
-- This data runs the majority of analysis, creating tables and graphs for the final thesis as well as the recreated OLS model, the predictive OLS model, and the Random Forest model.

5. LSTM Single Step Final Code.ipynb (this is within the LSTM folder and was run via an Anaconda Jupyter Notebook rather than R)
-- This python notebook creates and trains the LSTM model and outputs the predicted values into a csv file.

6. LSTM Graph.Rmd
-- For clarity this was separated from the Inter Intra Joined data Time Series Tests.Rmd as it must be run after the LSTM python code is run. It loads in predicted values and creates a similar ggplot to compare with the other models.

Warning: The raw data will take up approximately 25 GB before the hourly data is aggregated.
