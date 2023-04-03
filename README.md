# Time Series Analysis for Top 5 Best Zip Codes for Realty Investments

<img width="1337" src=images/ZipCodeHeader.png>

## Authors
[Paul Schulken](https://github.com/pschulk/), [John Nahra](https://github.com/jnahra/), & [Annie Zheng](https://github.com/anniezhengaz/)

## Project Overview

This project utilizes data from Zillow for a Time Series model to determine which zip codes in the United States would be the best to invest in. We aim to forecast and recommend which 5 zip codes would be the best for the real-estate investment firm to invest in regards to 5-Year Return on Investment and Down Deviation.

<img width="250" src=images/ZillowLogo.png>


## The Bottom Line

The following are the top 5 zip codes we believe would be the best to invest in:

| Rank | Zipcode | City, State |
| ---- | ------- | ----------- |
|   1  |  37207  | Nashville, Tennessee |
|   2  |  33705  | St. Petersburg, Florida |
|   3  |  94601  | Oakland, California |
|   4  |  80216  | Denver, Colorado |
|   5  |  15201  | Pittsburgh, Pennsylvania |


## Data Overview & Business Goal
As mentioned previously, the data used in this analysis was from [Zillow Research Page](https://www.zillow.com/research/data/). The data provided information such as over zip codes, city names, states, and median housing sales values. The target variable in our analysis was the sales value which laid a foundation for the rest of the analysis and modeling. Our initial dataset consisted of 14,723 zip codes and sales values spanning from April of 1996 to April 2018, however, our modeling focused on data between 2013-2018 as the 2008 Recession brought about a limitation to our dataset that skews the data and modeling. 

Our goal is to identify and recommend the top 5 zip codes would be the best to invest in to maximize profits that minimized risk. 


### Data Cleaning & Preparation
Taking an initial look into the dataset, there appeared to be some 4-digit zip codes. From some further research, those with only 4 digits were zip codes that begun with 0. Zillow only contains data within the United States which has a strict 5-digit long zip code. The 4-digit long zip codes were addressed by adding back the 0 to the beginning. 

We feature engineered additional columns such as the 5-year percent returns column to assist us in our search for the top 5 zip codes to invest in. By gathering the top 10 zip codes by highest 5-year percent return from 2013-2018, we filtered many zip codes out. Those top 10 zip codes were soon filtered down to 5 by selecting those with the lowest down devation from 1996-2018. This left us with 5 zipcodes spanning across California, Tennessee, Florida, Pennsylvania, and Colorado as seen below. Home prices have generally rise over time, but the 2008 financial crisis did create a major reversal of home prices for a time. Yet all these top performers resumed their uptrend and hit new highs as of 2018.

<img width="650" src=images/top5_zipcodes_over_time.png>

The chart below focuses on zip code 37210 in Nashville, TN specifically. Any month where Nashville’s 5-year % return was below that for the national average was included in the down deviation calculation. For Nashville, one of our top zipcodes, this was about 150% (as you can see by the last data point of the blue line). To quantify downside risk, we used the down deviation measure, which is essentially a standard deviation calculation that focuses only on downside volatility. We defined downside for these zipcodes as their 5-year % return underperforming the national average for any given month. So on the chart, any month where Nashville’s 5-year % return was below that for the national average was included in the down deviation calculation.

<img width="650" src=images/Nashville_5YrReturn.png>

The following are the top five cities by highest 5-year % return and lowest down deviation that we modeled. Denver didn’t have data before 2013 so we couldn’t calculate its down deviation, but we included it anyway because it had the highest 5-year return. We also excluded a New York City zipcode that would have qualified. We just had a sinking feeling that its expensive home prices could take a hit if a global pandemic were to occur and lead to the rise of remote work.

| Zip Code | City, State | 5-Year ROI | Down Deviation |
| -------- | ----------- | -----------| -------------- |
|  80216  | Denver, Colorado |  174%  |  N/A  |
|  94601  | Oakland, California |  168%  |  21%  |
|  33705  | St. Petersburg, Florida |  159%  |  20%  |
|  37210  | Nashville, Tennessee |  156%  |  16%  |
|  15201  | Pittsburgh, Pennsylvania |  148%  |  10%  |

## Modeling & Evaluation

To begin the modeling process, we split our data into train and test sets. Since our dataset focused on the years 2013-2018, the train set was 2013 to 2017 and the test set was 2017 to 2018. We ran five ARIMA models, one for each of the top zipcodes. Each model used second order differencing to make the data stationary.

The following graph is our model for Nashville. Our test predictions were off by about $15,000 dollars on average.

<img width="650" src=images/nashville_train_test.png>


Following the train/test split, we used our model to make a home price prediction for the next five years to determine which of the top five zipcodes represents the best investment. Here we are again showing a Nashville chart, which includes its actual home prices along with our 5 year forecast. Nashville had the highest predicted 5 year return of our top zipcodes. The model has an implicit assumption that there will not be a housing recession in the next five years.

<img width="650" src=images/nashville_home_price.png>


After the top 5 zip codes were selected for modeling and predictions made based off of those models, the return on investments at various intervals were calculated. The analysis included 1-, 3-, and 5-year returns, as shown in the following graph. It is clear that Nashville has the highest predicted returns for each time interval, most notably a 144% five year return! St. Petersburg and Oakland were strong performers as well.

<img  width="650" src=images/top5_zipcodes_roi.png>


## Conclusion & Recommendations
The top 5 best zip codes to invest in have been identified and ranked in order of recommendations. With the highest returns across all three time intervals, our first recommendation is to explore acquiring property in Nashville, Tennessee. We also found St. Petersburg, Oakland, and Denver produce hefty returns. Lastly, although Pittsburgh didn’t perform as well as the others, it rounds out our Top 5 in terms of maximum return and minimum risk. With a variety of geographic features including beaches, mountains, and more dense urban areas, your investment may also depend on personal preference and lifestyle.


| Rank | Zipcode | City, State |
| ---- | ------- | ----------- |
|   1  |  37207  | Nashville, Tennessee |
|   2  |  33705  | St. Petersburg, Florida |
|   3  |  94601  | Oakland, California |
|   4  |  80216  | Denver, Colorado |
|   5  |  15201  | Pittsburgh, Pennsylvania |


## Future Insights & Next Steps
Future models could be made more comprehensive by including extra variables like mortgage rates and analyzing any cyclical trends like recession indicators. In addition, we could investigate seasonality to determine if a certain time of year was the best time to buy or sell.

## For More Information

Please review our full analysis in [our Jupyter Notebook](./Phase_4_Final_Notebook.ipynb) or our [presentation](./Presentation.pdf).

## Repository Structure

```
├── exploratory_files                   <- Jupyter notebooks for data exploration and testing
├── images                              <- Both sourced externally and generated from code
├── data                                <- Data files used in analysis
├── .gitignore                          <- Code to avoid uploading specified files
├── Phase_4_Final_Notebook.ipynb        <- Narrative documentation of analysis in Jupyter notebook
├── README.md                           <- The top-level README for reviewers of this project
├── Presentation.pdf                    <- PDF version of project presentation
```