# Is there a significant correlation between Bitcoin prices and other economic indicators, such as the S&P 500?

## What questions are we looking to answer with this proyect? 

The intention for this proyect is to answer these very interesting questions: 

1. The correlation between Bitcoin and the S&P 500 is higher in periods of economic crisis, is this true?
2. Which Offers Better Returns: Bitcoin's Volatility or the S&P 500's Consistency?
3. Bitcoin shows high volatility compared to the S&P 500, but how volatile is BTC compared to the S&P 500?

By using different techniques such as:

  * Statistics 
  * Analytics
  * Finances 
  * Story Telling
  * Critical thinking

With tools like: 

  * __Python__
  * __Numpy__
  * __Pandas__
  * __Matplotlib__
  * __Seaborn__

I'll answer these very interesting questions, enjoy!

## **Datasets**
### Overview

The datasets include daily prices for Bitcoin and the S&P 500 from **September 2014 to May 2024**.

### Key Preprocessing Steps:

1. **Handling Missing Values**:
   - Removed missing values to ensure data integrity, as they represented less than 1% of the dataset.
2. **Removing Weekend Data**:
   - Aligned Bitcoin's data with the S&P 500, which only trades on business days.
3. **Data Cleaning**:
   - Removed duplicates and ensured temporal alignment between datasets.


## **Project Workflow**

### Step 1 & 2: Initial Investigation
- Performed exploratory analysis using `.head()`, `.info()`, and `.describe()` to understand the datasets.
- Combined relevant files to create unified datasets for Bitcoin and S&P 500 index.
- Ensured high data quality by removing null and duplicate rows.
- Change the data type in columns like 'Date' to `datetime64` for better handling with the datasets.
- By using the Interquartile Range method (IQR) some outliers were found in both datasets, they were keep in order to see market behaviors during extreme events. 
- Data was exported one file for BTC and S&P500 

See the further details in the notebooks for these steps: 
* [Initial Exploration S&P 500](./1_Inital_Exploration_SP_500.ipynb)
* [Initial Exploration BTC](./1_Initial_Exploraion_BTC.ipynb)
* [BTC and S&P Comparation](./2_BTC_SP500_Comparation.ipynb)

### Step 3: Quality Evaluation

- Verified data integrity by checking for **missing values**, **duplicates**, and **logical value ranges**.
- Datasets are temporally, ensuring both had identical date ranges.
- Data is clean and it is consisten and reliable in both datasets.

See the further **observations** and **conclusions** in the notebook:
* [Quality Evaluation for BTC and S&P 500](./3_Quality_Evaluation_BTC_SP500.ipynb)

<a id='temporal-analysis'></a>
### Step 4: Temporal Analysis

- **Objective**: Identify price trends over weekly, monthly, quarterly, and yearly intervals.

- **Findings**:
  - **Price Trends**:
    - Bitcoin shows high short-term variability, while the S&P 500 has stable, consistent growth. **(See [Figure 1](#figure-1))**
    - Long-term trends highlight Bitcoin's exponential growth and volatility. **(See [Figure 2](#figure-2))**
  - **Volume Trends**:
    - Bitcoin's transaction volume correlates with periods de high price volatility, often spiking during market rallies or crashes. 
    - The S&P 500's transaction volume remains relatively stable, aligning with its consistent growth.
    - Significant volume surges in Bitcoin often precede price reversals, suggesting a strong relationship between market sentiment and trading activity. **(See [Figure 3](#figure-3) and [Figure 4](#figure-4))**
  - **Comparative Insights**:
    - Bitcoin's volume is highly responsive to market news and macroeconomic events, amplifying its volatility.
    - S&P 500's trading volume shows resilience and lower sensitivity to short-term news, indicating a mature and stable market structure.
    - In both cases in January 2018 price and volume of bitcoin surpassed S&P's metrics, and has stayed like that since then, for the moment... **(See Figure 1 and 3)** 

- **Simple Words**:
  - Bitcoin 🪙 exhibits high volatility and exponential long-term growth 📈, with transaction volumes spiking significantly during market events 📊, while the S&P 500 remains stable and less sensitive to short-term changes 🛠️📉. **Since 2018, Bitcoin has consistently outperformed the S&P 500 in both price 💸 and volume 🔥**.

See the further **observations** and **conclusions** in the notebook:
* [Temporal Analysis for Bitcoin and S&P 500 Index](/4_Temporal_Analysis.ipynb)


<a id="figure-1"></a>
**Figure 1.** Average Weekly Prices of BTC and S&P 500 (USD). [⬆️ Go back](#temporal-analysis)

![Average Weekly Prices of BTC and S&P 500 (USD)](./images/Fig1_weekly_prices_BTC_SP500.png)

<a id="figure-2"></a>
**Figure 2.** Average Annual Prices of BTC and S&P 500 (USD). [⬆️ Go back](#temporal-analysis)

![Average Annual Prices of BTC and S&P 500 (USD)](/images/Fig2_annual_prices_BTC_SP500.png)

<a id="figure-3"></a>
**Figure 3.** Weekly Volume Transaction of BTC and S&P 500 (per 1 millon units). [⬆️ Go back](#temporal-analysis)

![Weekly Volume Transaction of BTC and S&P 500](/images/Fig3_weekly_volume_BTC_SP500.png)

<a id="figure-4"></a>
**Figure 4.** Annual Volume Transaction of BTC and S&P 500 (per 1 millon units). [⬆️ Go back](#temporal-analysis)

![Weekly Volume Transaction of BTC and S&P 500](/images/Fig4_annual_volume_BTC_SP500.png)


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

## Volatility Analysis: Bitcoin vs S&P 500

### Overview
In this section of the project, we analyzed and compared the monthly and annual volatility of Bitcoin (BTC) and the S&P 500. Volatility was calculated using the standard deviation of daily prices resampled to monthly and yearly intervals. This analysis aimed to highlight how Bitcoin, as a relatively new and speculative asset, behaves differently compared to a traditional, established market index like the S&P 500.

### Key Insights

1. **Consistently Higher Volatility for Bitcoin**:
  - Bitcoin exhibits significantly higher monthly and annual volatility compared to the S&P 500.
  - For example, during the 2020-2021 bull market, Bitcoin's monthly volatility was up to **10x higher than** that of the S&P 500.

2. **Volatility Peaks During Major Events**:
  - **2018**: Following the late 2017 surge to nearly $20,000, Bitcoin underwent a significant correction in early 2018, leading to reduced volatility. This downturn was influenced by stricter regulations and security concerns on trading platforms.
  - **2019**: In the first half of 2019, Bitcoin rebounded, reaching approximately $13,800 in June. This rise was driven by renewed institutional interest, the introduction of Bitcoin futures, and positive expectations regarding cryptocurrency adoption.
  - **Early 2020 (COVID-19)**: In January 2020, Bitcoin's volatility increased due to global economic uncertainties, including early reports of COVID-19. Investors sought alternative assets as a hedge, temporarily boosting Bitcoin's price.
  - **Late 2020 to Early 2021**: At the end of 2020, Bitcoin experienced a sharp rise in both volatility and price, surpassing $20,000 for the first time since 2017. Factors such as adoption by companies like PayPal, significant institutional investments, and a growing perception of Bitcoin as a hedge against inflation contributed to this surge.
  - **Mid-2021 Decline**: In 2021, Bitcoin reached an all-time high of around $64,000 in April, followed by a sharp decline in May, dropping below $30,000. This volatility was due to restrictive measures in China against cryptocurrency mining and trading, as well as environmental concerns related to Bitcoin's energy consumption.
  - **2023 and 2024**: In 2023, Bitcoin exhibited moderate fluctuations, influenced by regulations in various jurisdictions and the evolution of institutional adoption. In 2024, Bitcoin's price has shown an upward trend, reaching new all-time highs. This increase is attributed to favorable political promises towards cryptocurrencies, such as those made by U.S. President Donald Trump, who has expressed his intention to make the country the "crypto capital of the planet" :contentReference[oaicite:0]{index=0}. Additionally, the approval of Bitcoin ETFs and greater institutional adoption have contributed to this rise.

3. **Correlation With Major Economic Events**:
  - Periods of high volatility in Bitcoin align with major global crises, such as the COVID-19 pandemic and the 2023 economic slowdown, suggesting that Bitcoin often behaves like a high-risk asset during these periods.

### Methodology

1. **Data Preparation**:
  - Cleaned and aligned Bitcoin and S&P 500 datasets with daily prices.
  - Resampled data to calculate monthly and annual standard deviations as a measure of volatility.

2. **Visualization**:
  - Created comparative graphs for monthly and annual volatility of Bitcoin and the S&P 500.
  - Annotated key events (e.g., 2018 bubble correction, COVID-19) to provide context for volatility spikes.

### Key Takeaways for Stakeholders

- **Investment Perspective**: Bitcoin's high volatility presents both opportunities and risks, especially during periods of market uncertainty. Understanding these patterns is critical for portfolio diversification.
- **Market Behavior**: Bitcoin's reaction to global crises resembles that of a high-risk asset, aligning with market trends but often amplifying them.
- **Strategic Decision-Making**: This analysis equips stakeholders with data-driven insights to better navigate the risks and rewards of Bitcoin compared to traditional assets like the S&P 500.

### Future Improvements

- Include other economic indicators (e.g., inflation rates, interest rates) to deepen the analysis.
- Explore intraday volatility patterns for shorter timeframes.
- Enhance visualizations with interactive tools like Plotly or Dash.

---

**Files Generated**:
- Monthly and annual volatility comparison graphs.
- Annotated graphs highlighting key economic events.



### About the .csv files:

The dataset was originally spread in 6 different files 2 of them with the __MarketCap__ for Bitcoin and .
The other 4 are 2 for the daily prices for Bitcion and  with their prices __compared to USD__

This is why I decided to join the files __"Bitcoin USD (01-05.2024)"__ and __"BTC-USD (2014-2024)"__, and the __"ETH-USD (01-05.2024)"__ with __"ETH-USD (2017-2024)"__ in order to create only 2 files, one for BTC and other for ETH making the analysis easier. 

There is also a data set from [yahoo finance](https://finance.yahoo.com/quote/%5EGSPC/history/) in which the historical information can be found. 