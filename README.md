# Global Reporting on Groundwater Levels
Here a word of explanation about our work with WMO
In the 2022 edition of the State of Global Water Resources released by the World Meteorological Organization (WMO), IGRAC was responsible for reporting on the state of groundwater. The 2023 edition of this report incorporates a revised methodology for assessing groundwater status.
This repository contains the following programs (and associated reports):
1) Global Reporting on Groundwater Levels 2022
- 
2) Updated methodology for Data Selection and Groundwater Level Trend Analysis
By clicking on [Groundwater level trend analysis - Updated methodology for selecting the data.ipynb](https://github.com/UNIGRAC/Global-Reporting-Groundwater-Levels/blob/b3e4c6bccfe4d3b903159db3dad25c6f26054f7e/Groundwater%20level%20trend%20analysis%20-%20Updated%20methodology%20for%20selecting%20the%20data.ipynb) a Jupiter notebook file has been used where it focuses on:

A new data filtering method that utilizes a threshold percentage between specified start and end dates, conducting monthly analysis on well time series data and categorizing it into accepted data and rejected data based on the threshold. Additionally, the repository includes functions for autocorrelation analysis, utilizing Statsmodels to generate autocorrelation plots with lags displayed. The MK_tests function conducts Mann-Kendall tests on time series data, offering flexibility with different test options, and the MK_plot function visualizes the results through informative plots for each well. The final section of the code conducts exploratory data analysis using the [Ogallala_2001_2020.csv](https://github.com/UNIGRAC/Global-Reporting-Groundwater-Levels/blob/e7505cbc2b06735f20f15a3ba332f29aba60c570/Ogallala_2001_2020.csv) file, providing users with a comprehensive visual representation of the results for insightful data exploration.

1) A new filtering method of the data has been used: It filters the data based on a given threshold percentage between specified start and end dates. The function then performs a monthly analysis of each well's time series, identifying and handling missing values. Accepted data (above the threshold) is returned as Final_accepted and rejected data (below the threshold) is returned as Not_accepted. 

2) The Autocorrelation function generates autocorrelation plots for each well's time series data in the given DataFrame (df). It calculates autocorrelation and confidence intervals using Statsmodels, and the occurring lags are displayed on the plot. The number of lags is determined based on the autocorrelation values and confidence intervals.

3) The MK_tests function performs Mann-Kendall tests on time series data using the pykmannkendall package. It allows the user to choose two different Mann-Kendall tests, specified by the num1 and num2 parameters. The available Mann-Kendall tests are:

1: 'mk.original_test'

2: 'mk.hamed_rao_modification_test'

3: 'mk.yue_wang_modification_test'

4: 'mk.trend_free_pre_whitening_modification_test'

5: 'mk.pre_whitening_modification_test'

6: 'mk.seasonal_test'

The results of these tests, along with autocorrelation information, are included in the final output DataFrame for each well.

4) The MK_plot function performs various Mann-Kendall tests on time series data using the MK_tests function and visualizes the results through a series of plots. The function generates individual plots for each well, displaying the time series data along with linear trend lines based on Mann-Kendall test results. The plots include information such as slope, trends, and p-values for both Mann-Kendall tests.

5) The final part of the code involves exploratory data analysis, where you can input the 'Ogallala_2001_2020.csv' file attached to this repository. This analysis provides users with a visual representation of the results, offering insights and an overview of the data.

For any information, please contact info@un-igrac.org



