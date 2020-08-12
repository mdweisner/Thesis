# Thesis
## Code Overview
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

## Abstract
This study aimed to build on the work of Anthony Heyes, Soodeh Saberian, and Matthew Neidell’s 2016 National Bureau of Economic Research working paper, The Effect of Air Pollution on Investor Behavior: Evidence From the S&P 500 by both recreating the original study using a more recent sample of years and by attempting to use the recreated data to predict the S&P 500 interday percentage returns. The primary aim of the study was to explore the potentially predictive relationship between air pollution and inter-day stock market returns, particularly atmospheric particulate matter of 2.5 micrometers diameter or lower (PM2.5). Heyes, Neidell, and Saberian’s used an Orindary Least Squares (OLS) regression model in their study, which served as a starting point for predictive modeling in this paper. Due to the lack of availability of the original data, the recreated model required several noteworthy adaptations from the study timeframe and data sources. The findings of the study had potential to strengthen or raise questions about the use of the environmental factors – which are not typically considered in economic predictive modeling – which Heyes et al. argued were major influential factors.
After recreating the original model, several predictive models were tested to examine the predictive power of the air pollution and weather metrics described by Heyes et al. The relative predictive power of each model was compared by implementing three models – an OLS
regression model, a Random Forest regression model, and a Long Short Term Memory Recurrent Neural Network model (LSTM) to compare their Root Mean Squared Error (RMSE) scores.
Ultimately, the study was unable to find the same relationships described in the original study by Heyes et al and uncovered several discrepancies with the described origin of some of the environmental data, although these may be corrected by the time the paper undergoes peer review. Despite the lack of similar statistical relationships the relative predictive power of each aforementioned model was still evaluated and compared to examine if more “advanced”
techniques could still result more predictive results. The models’ exhibited similar accuracy as measured by RMSE values yet vastly different predictive values, which may indicate that air pollution and the other included variables provide very little predictive power of inter-day stock return changes in contrast to the significant findings of Heyes, et al.
