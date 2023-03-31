# Time Series Analysis for Top 5 Best Zip Codes for Realty Investments

<img width="1337" src=images/ZipCodeHeader.png>

## Authors
[Paul Schulken](https://github.com/pschulk/), [John Nahra](https://github.com/jnahra/), & [Annie Zheng](https://github.com/anniezhengaz/)

## Project Overview

This project utilizes data from Zillow for a Time Series model to determine which zip codes in the United States would be the best to invest in. We aim to forecast and recommend which 5 zip codes would be the best for real-estate investment firm to invest in regards to 5-Year Return on Investment and Down Deviation.

<img width="250" src=images/ZillowLogo.png>


## The Bottom Line

The following are the top 5 zip codes we believe would be the best to invest in:

| Rank | Zipcode | City, State |
| ---- | ------- | ----------- |
|   1  |  80216  | Denver, Colorado |
|   2  |  94601  | Oakland, California |
|   3  |  33705  | St. Petersburg, Florida |
|   4  |  37210  | Nashville, Tennessee |
|   5  |  15201  | Pittsburgh, Pennsylvania |


## Data Overview & Business Goal
As mentioned previously, the data used in this analysis was from [Zillow Research Page](https://www.zillow.com/research/data/). The data provided information such as over zip codes, city names, states, and median housing sales values. The target variable in our analysis was the sales value which laid a foundation for the rest of the analysis and modeling. Our initial dataset consisted of 14,723 zip codes and sales values spanning from April of 1996 to April 2018, however, our modeling focused on data between 2013-2018 as the 2008 Recession brought about a limitation to our dataset that skews the data and modeling. 

Our goal is to identify and recommend the top 5 zip codes would be the best to invest in to maximize profits that minimized risk. 


### Exploratory Data Analysis & Data Cleaning
Taking an initial look into the dataset, there appeared to be some 4-digit zip codes. From some further research, those with only 4 digits were zip codes that begun with 0. Zillow only contains data within the United States which has a strict 5-digit long zip code. The 4-digit long zip codes were addressed by adding back the 0 to the beginning. 

We feature engineered additional columns such as the 5-, 10-, and 15-Year Percent Returns columns to assist us in our search for the top 5 zip codes to invest in. By gathering the top 10 zip codes by highest 5-year percent return from 2013-2018, we filtered many zip codes out. Those top 10 zip codes were soon filtered down to 5 by selecting those with the lowest down devation from 1996-2018. 

This left us with 5 zipcodes spanning across California, Tennessee, Florida, Pennsylvania, and Colorado. In order to model our dataset, we took steps towards making the data stationary through differencing. 


## Modeling & Evaluation

*add modeling info and graphs*


## Conclusion & Recommendations
The top 5 best zip codes to invest in have been identified and ranked in order of recommendations. Denver, Colorado has the highest predicted 5-Year Return on Investment of the 5 zipcodes with a 174% 5-year return on investments. Following closely behind are Oakland, California and St. Petersburg, Florida.

| Rank | Zipcode | City, State |
| ---- | ------- | ----------- |
|   1  |  80216  | Denver, Colorado |
|   2  |  94601  | Oakland, California |
|   3  |  33705  | St. Petersburg, Florida |
|   4  |  37210  | Nashville, Tennessee |
|   5  |  15201  | Pittsburgh, Pennsylvania |


## Future Insights & Next Steps
- Research into mortgage rates
- Analyze cyclical trends such as recession indicators
- Investigate seasonality