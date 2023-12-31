# Hurricane Season - A Historical Impact Analysis

## Analysis:
Weather and Climate disasters are among the most costly events for those within their path. With projected annual costs at $165 billion and major climate events averaging 20 per year in the United States[(2002, NOAA Office for Coastal Management)](https://coast.noaa.gov/states/fast-facts/hurricane-costs.html), an understanding of the range and impact of these disasters is of paramount importance. 

This study focuses on historical statistics and impacts of hurricaine season in order to gain a greater understanding of their significance over time. The below sections are designed to answer the following research questions:

<ol>
  <li>What are the historical trends of the frequency, severity, and types of storms?</li>
  <li>Is there a correlation of the frequency, severity, and type of storm to average ocean temperatures, land surface temperatures or atmospheric CO2 concentrations?</li>
  <li>What is the human impact of these storms across time as characterized by landfall percentage and disaster declaration</li>
</ol>

## Study Staff
This study was conducted by the following members:
    <ul>
        <li>Matthew Yackee</li>
        <li>Shawn Woodbury</li>
    </ul>

## Section 1: Historical Trends

This section aims to examine the historical trends of atlantic storms as a prerequisite to the following analyses. The study will analyze 30 years of data to examine the number of storms, and the storms' categorization averages to establish change over time. This period was selected to reflect NOAA's recommendation to maximize data accuracy. The documentation reflected that dates before 1991 may have incomplete data collection and/or questionable accuracy. 

<b>Primary Questions</b>
 <ol>
    <li>Has the frequency of storms per season changed over time?</li>
    <li>Has the intensity/severity of storms changed over time?</li>
</ol>

<b>Methodology</b>

Storm data from the NOAA Hurdat2 Database were filtered to capture each individual storm reported by the agency. This data was then aggregated to acertain the occurring year, number of landfalls, maximum recorded windspeed, and maximum category rating for each storm. The storms were then grouped by year of occurrance, and a summary table and box plot for analysis of distribution was conducted. Finally, a line chart and stacked box plot were created to visualize the change over time of the frequency and category ratings for each year studied. 

<b>Relevant Notebooks:</b>
<ul>
    <li><a href='HurricaneDataFiltering.ipynb'>Hurricane Data Filtering</a></li>
    <li><a href='ScatterPlotsAndRegressions.ipynb'>Storms per Year Distribution</a></li>
    <li><a href='PerfectStorm.ipynb'>Storm Frequency and Categorization</a></li>
</ul>

<b>Visualizations:</b> 
<ul>
    <li><a href='Visualizations/Stormsperyearbox.png'>Storms per Year Distribution</a></li>
    <li><a href='Visualizations/stormfreq.png'>Storms per Season</a></li>
    <li><a href='Visualizations/stormcat.png'>Category Ratings per Season</a></li>
</ul>

<b>Conclusions:</b>

When charting each storm over the 30 year period, the number of storms per season was found to follow a normal data distribution with a mean of 16.23 storms per season, a median of 16.0 and a standard deviation of 5.5 storms. There were two outlier seasons identified in the analysis: 2005 and 2020, with 31 reported storms in each year. The above average years are slightly differently distributed between the first and second half of the dataset with 33.3% of all above average years in the first half of the dataset and 66.7% of all above average years reported in the second half. This would indicate an increase in number of storms year to year across time with a delta of 100% for the second half of the dataset. 

When examining category breakdowns across all seasons, the average number of each category can be broken down in the following bins: 
<ul>
<li>Category 0 (non-hurricane): 55.03%</li> 
<li>Category 1: 17.04%</li>   
<li>Category 2: 8.01%</li> 
<li>Category 3: 7.60%</li> 
<li>Category 4: 9.03%</li> 
<li>Category 5: 3.29%</li> 
</ul>
These category breakdowns are consistent across the dataset with a +/- of 2.3% per category, indicating that there is no difference in the category breakdown of hurricanes by category year to year. 

<b>Data Sources</b>

<ul>
    <li><a href='https://www.nhc.noaa.gov/data/hurdat/hurdat2-1851-2022-050423.txt'>National Hurricane Center Hurdat2 Database</a></li>
</ul>

## Section 2: Climatological Correlation

This section aims to examine correlation between various climatological conditions and storm frequency and intensity/severity:

<b>Primary Questions</b>
 <ol>
    <li>Does the average oceanic water temperature correlate to storm frequency/category?</li>
    <li>Does the average land surface temperature correlate to storm frequency/category?</li>
    <li>Does the atmospheric CO2 concentration correlate to storm frequency/category?</li>
    <li>If correlations exist, what is the significance of these correlations?</li>
</ol>

<b>Methodology:</b>

The annual hurricane data isolated in section 1 was joined with climatological data from NOAA and the globalwarming.org API (which the NPO cited as sourced from NASA satellite data). These data were compared against annual storm frequency and annual average storm maximum category and were analyzed for correlation using a linear regression for each of the following climatological conditions: Annual Ocean Temperature Average (Anomaly above/below century average), Annual Land Temperature Average (Anomaly above/below century average), and atmospheric CO2 concentration (absolute PPM). Each of these correlations and regressions were plotted in the visualizations below. A correlation coefficient (r2) was then calculated to establish significance.

<b>Relevant Notebooks:</b>
<ul>
    <li><a href='ScatterPlotsAndRegressions.ipynb'>Scatter Plots and Regressions</a></li>
</ul>

<b>Visualizations</b> 
<ul>
    <li><a href='Visualizations/AnomaliesVsStormFrequency.png'>Ocean Temperature/Frequency Regression</a></li>
    <li><a href='Visualizations/AnomaliesVsStormSeverity.png'>Ocean Temperature/Category Regression</a></li>
    <li><a href='Visualizations/LandAnomaliesVsStormFrequency.png'>Land Temperature/Frequency Regression</a></li>
    <li><a href='Visualizations/LandAnomaliesVsStormintensity.png'>Land Temperature/Category Regression</a></li>
    <li><a href='Visualizations/CO2vsStormFrequency.png'>CO2 Concentration/Frequency Regression</a></li>
    <li><a href='Visualizations/CO2VsStormintensity.png'>CO2 Concentration/Category Regression</a></li>
</ul>

<b>Conclusions:</b>

When examining various climatological characteristics, it can be seen that they have varying correlations to hurricane characteristics year over year. 

Oceanic temperature was found to be only minorly correlated if at all to either hurricane frequency or severity. With a 7% correlation to frequency and a .49% correlation to average category rating, Annual Oceanic temperature can not be said to be a good correlative measure to hurricane characteristics

Average Annual land temperature was found to have a higher correlation coefficient in both frequency and severity. This showed a 16.3% correlation to frequency and a .54% correlation to severity, making it a much better, albeit still minor, predictor of frequency but still a very ineffective correlative to severity of hurricanes.

Atmospheric CO2 concentration proved to be the most effective correlative measure of any of the three climatological measures studied, with a r2 of 66.8% in storm frequency and 17.1% in average storm category. It is important to mention here, however, that reliable data for Atmospheric CO2 was only available 2013-2023, so this measure is not directly comparable to either of the earlier measures which categorized the years 1991-2020.

While it is outside the scope of this study to assert causality, and the data would not warrant such a claim, it can be seen that each of the three measures of climate are increasing over the measured period, and echoes relative changes in the characteristics of the hurricane season

<b>Data Sources:</b>

<ul>
    <li><a href='https://www.nhc.noaa.gov/data/hurdat/hurdat2-1851-2022-050423.txt'>National Hurricane Center Hurdat2 Database</a></li>
    <li><a href='https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/global/time-series/globe'> NOAA Global Time Series Database</a></li>
    <li><a href="https://global-warming.org/">GlobalWarming.org</a></li>
</ul>

## Section 3: Human Impact Analysis

This section aims to examine the relationship of historical storm trends to overall human impact:

<b>Primary Questions</b>
 <ol>
    <li>Is there a difference over time in the ratio of landfall vs. non-landfall storms?</li>
    <li>Is there a difference over time in the number of disaster declarations as a result of hurricanes?</li>
</ol>

<b>Methodology:</b>

The isolated hurricane data from section 1 was examined for landfall events. Each storm was given a boolean for whether or not it had any landfall events, regardless of the number of events. These storms were then grouped by year and visualized into a stacked bar chart for comparison.

Fema data from OpenFEMA was examined for the number of disaster declarations per year. This data was then filtered to characterize only hurricane related data. A summary table and box plot were created to find overall trends and to identify outliers. This data was then grouped by year and plotted in a line graph for visualization against the average.
*It is important to note that this data was for the entirity of the United States over the 31 year period 1991-2022, and as such is not a direct correlary to the remainder of the data. Additionally, as disaster declarations are handled on the state and/or municipal level, there may be multiple disaster declarations associated with a single storm. This does, however echo the remainder of the data as far as distribution, and as such can be considered an effective comparison for the purposes of this study.)*

<b>Relevant Notebooks:</b>
<ul>
    <li><a href='FEMA Analysis.ipynb'>FEMA Disaster Declarations</a></li>
    <li><a href='PerfectStorm.ipynb'>Landfall vs. Non-Landfall Storms</a></li>
</ul>

<b>Visualizations</b> 
<ul>
    <li><a href='Visualizations/disasterdeclarations.png'>Fema disaster declarations distribution</a></li>
    <li><a href='Visualizations/landstorm.png'>landfall vs. non-landfall storms</a></li>
    <li><a href='Visualizations/FemaDisasterDeclarationsvsAverage.png'>FEMA disaster declarations</a></li>
</ul>

<b>Conclusions:</b>

When examining landfalls, it was observed that the landfall vs. non landfall propotions remained stable over time. On average 44% of storms made landfall year over year, with a standard deviation of 15.7% year over year with a standard error of 2.87%. 

The FEMA disaster declarations data was found to have an annual mean of 13.28 per year, median of 10 per year and a standard deviation of 12.65. There was one outlier year in 2005 *(this can be accounted for by this year's unusual number of storms as outlied in previous sections)*. Of the 31 years documented in the data, 8 of the 11 above average years (72.7%) can be found in the last 15 years of the data, indicating an increase in the overall annual disaster declarations over time. 

<b>Data Sources</b>

<ul>
    <li><a href='https://www.nhc.noaa.gov/data/hurdat/hurdat2-1851-2022-050423.txt'>National Hurricane Center Hurdat2 Database</a></li>
    <li><a href="https://www.fema.gov/about/openfema/api">OpenFEMA</a></li>
</ul>

## Section 4: Conclusions
Overall, the data summarizes that there are some trends observable in the character of hurricane season over time: 

<ol>
  <li>The frequency of hurricanes in the atlantic has almost doubled in the last 15 years when compared to the previous 15 years.</li>
  <li>The intensity and occurrence of landfall of storms remains constant over time as a percentage of overall storms observed.</li>
  <li>Ocean and land temperature averages show little to no correlation to the frequency or severity of hurricanes</li>
  <li>Atmospheric CO2 concentrations show substantial correlations to hurricane frequency and some correlation to hurricane severity</li>
  <li>The number of disaster declarations as a result of hurricanes has risen over time with a substantial spike in the last 15 years (as compared to the previous 15 years)</li>
</ol>

While none of these conclusions are prescriptive, it is important to note that the trends of hurricanes over the last thirty years are worthy of further investigation, and further study of the effect of climatological preconditions could lead to a more causal relationship than could be expressed in this study. 
