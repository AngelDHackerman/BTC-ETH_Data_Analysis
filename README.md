<h1>Is there a significant correlation between Bitcoin/Ethereum prices and other economic indicators, such as the S&P 500 or interest rates?</h1>

## Data Analysis for Bitcoin and Ethereum from 2014 to 2024

This data analysis was done using the dataset from Kaggle: [bitcoin_ethereum-2014-2024](https://www.kaggle.com/datasets/kapturovalexander/bitcoin-and-ethereum-prices-from-start-to-2023)


## General Description about the data set: 

The dataset contains the information about __Daily__ prices for Bitcoin (BTC) and Ethereum (ETH) from differente range of dates but it is basically from January 2014 to May 2024

## What questions are we looking to answer with this proyect? 

The intention for this proyect is to answer a very interesting question about: how Bitcoin and Ethereum are correlated to the S&P 500 rates?

By using different techniques of:

* Statistics 
* Analytics
* Finances 
* Story Telling

I'll answer this very interesting question, while showing my skills as Data Analyst. 

### About the .csv files:

The dataset was originally spread in 6 different files 2 of them with the __MarketCap__ for Bitcoin and Ethereum.
The other 4 are 2 for the daily prices for Bitcion and Ethereum with their prices __compared to USD__

This is why I decided to join the files __"Bitcoin USD (01-05.2024)"__ and __"BTC-USD (2014-2024)"__, and the __"ETH-USD (01-05.2024)"__ with __"ETH-USD (2017-2024)"__ in order to create only 2 files, one for BTC and other for ETH making the analysis easier. 

There is also a data set from [yahoo finance](https://finance.yahoo.com/quote/%5EGSPC/history/) in which the historical information can be found. 

## Initial investigation and actions taken:

* Used methods like: `.head()`, `tail()`, `info()`, `describe()`, `isnull().sum()` and `duplicated().sum()` in order to have a better understanding for each CSV file.

* The column `Date` was changed to `datetime64` column type in all the datasets 

* The datasets: __BTC_2023_2024_MarketCap__ & __Bitcoin USD (01-05.2024)__, __ETH-USD (2017-2024)__ & __ETH-USD (01-05.2024)__ where combinded because they were the same data but in different Date ranges.

* Once the main datasets where combined into one (one for BTC and other for ETH), __null values__ and __duplicated values__ where removed because there was not too much data (only 2 rows for the null) and duplicated values wheren less han 15 rows for each dataset. 

* S&P 500 dataset was trim in order to have the same date ranges with Bitcoin and S&P's 500. 

* Matching the BTC and S&P 500 datasets by only using the business days in their entries. The Weekends dates where removed from the BTC dataset. 

  - __Data was filtered:__ Removed Weekends dates from BTC dataset in order to match the dates in both datasets
  - __Dates aligned:__ Idenfied and corrected differences between dates in order to make sure both datasets have same entries.
  - __Reseted Index:__ After filtering and cleaning, index were readjusted.