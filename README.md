# Realty Estate Investment: Top 5 Best Zip Codes to Invest In

<img width="1337" src=images/ZipCodeHeader.png>

## Authors
Paul Schulken, John Nahra, Annie Zheng

## Project Overview

This project utilizes data from Zillow for a Time Series model to determine which zip codes in the United States would be the best to invest in. We aim to forecast and recommend which 5 zip codes would be the best for real-estate investment firm to invest in regards to 5-Year Return on Investment and Down Deviation.

<img width="500" src=images/ZillowLogo.png>


## The Bottom Line

The following are the top 5 zip codes we believe would be the best to invest in:

| Rank | Zipcode | City, State |
| ---- | ------- | ----------- |
|   1  |  33705  | St. Petersburg, Florida |
|   2  |  37207  | Nashville, Tennessee |
|   3  |  80216  | Denver, Colorado |
|   4  |  15201  | Pittsburgh, Pennsylvania |
|   5  |  11216  | New York, New York |


## Data Overview & Business Goal

As mentioned previously, the data used in this analysis was from [Zillow Research Page](https://www.zillow.com/research/data/). The data provided information such as over 14 thousand zip codes, city names, states, and median housing sales values. The target variable in our analysis was the sales value which laid a foundation for the rest of the analysis and modeling. The dataset contain sales values spanning from April of 1996 to April 2018, however, our modeling focused on data between 2013-2018 as the 2008 Recession skews the data and modeling. 

Our goal, is to identify and recommend which top 5 zip codes would be the best to invest in to maximize profits. By gathering the top 10 zip codes by highest 5-year percent return from 2013-2018, we filtered many zip codes out. We then filtered those 10 zip codes down to 5 by selecting those with the lowest down devation from 1996-2018. This left us with 5 zipcodes spanning across New York, Tennessee, Florida, Pennsylvania, and Colorado. 

<img src=images/Top5States.png>

## Modeling & Evaluation

add modeling info and graphs


## Conclusion & Recommendations
The top 5 best zip codes to invest in have been identified and ranked in order of recommendations. St. Petersburg, FL has the highest predicted 5-Year Return on Investment of the 5 zipcodes with a 65% 5-Year return. Following behind are Nashville, TN, and Denver, CO. 

| Rank | Zipcode | City, State |
| ---- | ------- | ----------- |
|   1  |  33705  | St. Petersburg, Florida |
|   2  |  37207  | Nashville, Tennessee |
|   3  |  80216  | Denver, Colorado |
|   4  |  15201  | Pittsburgh, Pennsylvania |
|   5  |  11216  | New York, New York |


## Future Insights & Next Steps
- Research into mortgage rates
- Analyze cyclical trends such as recession indicators
- Investigate seasonality
