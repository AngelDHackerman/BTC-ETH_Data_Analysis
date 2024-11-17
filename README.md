<h1>Is there a significant correlation between Bitcoin/Ethereum prices and other economic indicators, such as the S&P 500?</h1>

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

## Initial investigation and actions taken (Steps 1 & 2):

* Used methods like: `.head()`, `tail()`, `info()`, `describe()`, `isnull().sum()` and `duplicated().sum()` in order to have a better understanding for each CSV file.

* The column `Date` was changed to `datetime64` column type in all the datasets 

* The datasets: __BTC_2023_2024_MarketCap__ & __Bitcoin USD (01-05.2024)__, __ETH-USD (2017-2024)__ & __ETH-USD (01-05.2024)__ where combinded because they were the same data but in different Date ranges.

* Once the main datasets where combined into one (one for BTC and other for ETH), __null values__ and __duplicated values__ where removed because there was not too much data (only 2 rows for the null) and duplicated values wheren less han 15 rows for each dataset. 

* S&P 500 dataset was trim in order to have the same date ranges with Bitcoin and S&P's 500. 

* Matching the BTC and S&P 500 datasets by only using the business days in their entries. The Weekends dates where removed from the BTC dataset. 

  - __Data was filtered:__ Removed Weekends dates from BTC dataset in order to match the dates in both datasets
  - __Dates aligned:__ Idenfied and corrected differences between dates in order to make sure both datasets have same entries.
  - __Reseted Index:__ After filtering and cleaning, index were readjusted.
  - __Objetive:__ This will warranty that data is ready and has high quality for the analysis, this process can be found in the file `2_BTC_SP500_comparation.ipynb`



## Quality Evaluation of the data (Step 3):

  In order to ensure that our datasets are clean, complete, and ready for analysis, a thorough **Quality Evaluation** was conducted. The following steps were taken:

1. **Check for Missing Values and Null Counts**:
   - Used `.isnull().sum()` to verify if any columns had missing values in either dataset (`btc_data` and `sp500_data`).
   - **Result**: No missing values were found in any of the columns, indicating complete data coverage.

2. **Check for Duplicates**:
   - Applied `.duplicated().sum()` to identify if there were any duplicate rows in either dataset.
   - **Result**: No duplicates were found, confirming the uniqueness of each data entry.

3. **Consistency of Value Ranges**:
   - Ran `.describe()` on both datasets to assess the minimum, maximum, mean, and standard deviation for each column.
   - Verified that:
     - Prices (`Open`, `High`, `Low`, `Close`) and `Volume` values were within expected ranges for both Bitcoin and the S&P 500.
     - Bitcoin data displayed higher volatility (high standard deviation) compared to the S&P 500, as expected.
   - **Result**: All values were within logical and expected ranges, with no outliers or unexpected anomalies.

4. **Temporal Integrity Check**:
   - Ensured the integrity of the date sequences by checking the frequency of date differences using `.diff().dt.days.value_counts()`.
   - Results showed consistent patterns:
     - 1-day gaps between consecutive entries represent standard business days.
     - 3-day gaps indicate weekends (Friday to Monday).
     - 4-day gaps likely represent long weekends with additional holidays.
     - No unexpected gaps were found, indicating complete and aligned date sequences in both datasets.

These steps confirm that the datasets are reliable, consistent, and suitable for comparative analysis between Bitcoin and the S&P 500 over time.


## Temporal Analysis Summary (Step 4):

### Objective
The objective of this analysis was to explore and understand the temporal patterns in the prices of Bitcoin and the S&P 500 from 2014 to 2024. This includes identifying trends, seasonality, and changes over different time intervals (weekly, monthly, quarterly, and annual).

---

### Steps Taken:

### 1. Data Resampling
We resampled the data to calculate average prices across different time intervals:
- **Weekly Averages:** Captured short-term trends in the data.
- **Monthly Averages:** Identified mid-term trends and smoother patterns.
- **Quarterly Averages:** Highlighted broader patterns and trends over three-month periods.
- **Annual Averages:** Summarized long-term behavior over each year.

### 2. Visualization
For each time interval, clear and informative visualizations were generated:
- **Weekly Trends:** Line plots showing weekly average prices for Bitcoin and the S&P 500.
- **Monthly Trends:** A broader look at the month-to-month price behavior.
- **Quarterly and Annual Trends:** Long-term visualizations to capture macroeconomic patterns.

### 3. Key Insights
- Bitcoin prices show higher variability over shorter intervals (e.g., weekly).
- S&P 500 demonstrates more stable trends with less pronounced fluctuations compared to Bitcoin.
- Long-term trends indicate Bitcoin's significant growth since 2014, albeit with substantial volatility.

---

### Outcomes
The temporal analysis provided a foundational understanding of how Bitcoin and S&P 500 prices behave over time. It also set the stage for more advanced analyses, such as evaluating volatility and uncovering deeper correlations.

This analysis is documented through code and visualizations, ensuring reproducibility and clarity for stakeholders.

---

### Next Steps
With the temporal analysis complete, the next step is to dive into specific insights, such as analyzing price **volatility**, **correlations** during significant events, and comparing **risk/return** profiles.


## Insights Analysis (Step 5):

### Objective

The objective of this analysis was to explore the correlation between Bitcoin (BTC) and the S&P 500 Index during the COVID-19 crisis (March 2020 to December 2021), energy and supplies crisis (2021-2022), financial crisis (2023-2024)

### Steps Taken

### 1. Data Preparation

- Merged daily closing prices of Bitcoin and the S&P 500.

- Filtered the data for the period of interest: March 2020 to December 2021, 2021-2022, 2023 and 2024

### 2. Analysis

- Calculated Pearson's correlation coefficient to measure the linear relationship.

- Created visualizations to explore trends and correlations:

  - __Time Series Plot:__ Compared daily prices of Bitcoin and the S&P 500.

  - __Scatter Plot with Regression Line:__ Highlighted the correlation visually.