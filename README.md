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

This section aims to examine the historical trends of atlantic storms as a prerequisite to the following analyses. The study will analyze 30 years of data to examine the number of storms, and the storms' categorization averages to establish change over time. 

<b>Primary Questions</b>
 <ol>
    <li>Has the frequency of storms per season changed over time?</li>
    <li>Has the intensity/severity of storms changed over time?</li>
</ol>

<b>Methodology</b>

Storm data from the NOAA Hurdat2 Database were filtered to capture each individual storm reported by the agency. This data was then aggregated to acertain the occurring year, number of landfalls, maximum recorded windspeed, and maximum category rating for each storm. The storms were then grouped by year of occurrance, and a summary table and box plot for analysis of distribution was conducted. Finally, a line chart and stacked box plot were created to visualize the change over time of the frequency and category ratings for each year studied. 

<b>Visualizations:</b> 
<ul>
    <li><a href='Visualizations/stormsperyearboxplot.png'>storms per year distribution</a></li>
    <li><a href='Visualizations/stormfreq.png'>storms per season</a></li>
    <li><a href='Visualizations/stormcat.png'>category ratings per season</a></li>
</ul>

<b>Conclusions:</b>
When charting each storm over the 30 year period, the number of storms per season was found to follow a normal data distribution with a mean of 16.23 storms per season, a median of 16.0 and a standard deviation of 5.5 storms. There were two outlier seasons identified in the analysis: 2005 and 2020, with 31 reported storms in each year. 

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

<b>Visualizations</b> 
<ul>
    <li><a href='Visualizations/AnomaliesVsStormFrequency.png'>Ocean Temperature/Frequency Regression</a></li>
    <li><a href='Visualizations/AnomaliesVsStormSeverity.png'>Ocean Temperature/Category Regression</a></li>
    <li><a href='Visualizations/LandAnomaliesVsStormFrequency.png'>Land Temperature/Frequency Regression</a></li>
    <li><a href='Visualizations/LandAnomaliesVsStormintensity.png'>Land Temperature/Category Regression</a></li>
    <li><a href='Visualizations/CO2VsStormFrequency.png'>CO2 Concentration/Frequency Regression</a></li>
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
    <li><a href='https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/global/time-series/globe/land_ocean'> NOAA Global Time Series Database</a></li>
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

<b>Visualizations</b> 
<ul>
    <li><a href='Visualizations/landstorm.png'>landfall vs. non-landfall storms</a></li>
    <li><a href='Visualizations/FEMADisasterDeclarationsvsAverage.png'>FEMA disaster declarations</a></li>
</ul>

<b>Conclusions:</b>
The FEMA disaster declarations data was found to have an annual mean of 13.28 per year, median of 10 per year and a standard deviation of 12.65. There was one outlier year in 2005 *(this can be accounted for by this year's unusual number of storms as outlied in previous sections)*. Of the 31 years documented in the data, 8 of the 11 above average years (72.7%) can be found in the last 15 years of the data, indicating an increase in the overall annual disaster declarations over time. 

<b>Data Sources</b>

<ul>
    <li><a href='https://www.nhc.noaa.gov/data/hurdat/hurdat2-1851-2022-050423.txt'>National Hurricane Center Hurdat2 Database</a></li>
    <li><a href="https://www.fema.gov/about/openfema/api">OpenFEMA</a></li>
</ul>

## Section 4: Conclusions

