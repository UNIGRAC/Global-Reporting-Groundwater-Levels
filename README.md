# Methodology Report IGRAC
In the 2022 edition of the State of Global Water Resources released by the World Meteorological Organization (WMO), IGRAC was responsible for reporting on the state of groundwater. The 2023 edition of this report incorporates a revised methodology for assessing groundwater status.
For that purpose, one Jupyter notebook 'Groundwater level trend analysis - Updated methodology for selecting the data.ipynb' has been used where it focuses on: 

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

<img src="WMO.jpg" alt="WMO Image" width="300">

