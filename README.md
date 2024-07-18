# Equity Data Analyst

I'm Amit Tembhurnikar from Mumbai, India and I work as a Data Analyst at Ambit Capital Pvt. Ltd., Mumbai.

- We Published detailed notes on accounting strategies, such as Accounting forensic and greatness framework, and Fundamental strategies such as the Coffee Can portfolio, the Good and Clean portfolio, and the Momentum portfolio.

- We collect and clean the equity data, historical fundamentals, Accounting data, valuation data, and forward estimate data to analyze the trend and back-test the strategies for price performance.



### Before Ambit Capital, I worked at ET Now and ET Now Swadesh - Times Network

- At Times Network, I covered the Logistics industry for financials, sectoral, Government schemes, and major corporate announcements.

- Also, I reported on conference calls, and investor meetings of major companies, and conducted interviews with representatives of corporates regarding their business outlook and news updates.


#### Few of the Articles for Times Now,

Christopher Woods, Jefferies - Greed & Fear: Focus on Federal Reserve tightening cycle and India story. [Click here](https://www.timesnownews.com/business-economy/companies/article/christopher-woods-jefferies-greed-fear-focus-on-federal-reserve-tightening-cycle-and-india-story/847839)

The good strategy is to invest in beaten-down themes: S Naren [Click here](https://www.timesnownews.com/business-economy/companies/the-good-strategy-is-to-invest-in-beaten-down-themes-s-naren-article-90503955)

'Bull market is perhaps the recognition of Indian economy taking center stage': Ramesh Damani [Click here](https://www.timesnownews.com/business-economy/markets/bull-market-is-perhaps-the-recognition-of-indian-economy-taking-centre-stage-ramesh-damani-article-90405604)

Ukraine isn't going to be a central mover of macro fundamentals or India’s economy: Saurabh Mukherjea [Click here](https://www.timesnownews.com/business-economy/ukraine-isnt-going-to-be-a-central-mover-of-macro-fundamentals-or-indias-economy-saurabh-mukherjea-article-89754744)

Inflation is good for equities and will probably help equities to deliver okay returns: Manish Gunwani [Click here](https://www.timesnownews.com/business-economy/companies/inflation-is-good-for-equities-and-will-probably-help-equities-to-deliver-okay-returns-manish-gunwani-article-90255644)

'India should have double-digit earnings growth': Hugh Young [Click here](https://www.timesnownews.com/business-economy/markets/india-should-have-double-digit-earning-growth-hugh-young-article-90184633)

Equities have become a far more main-line asset class than ever before; Prashant Jain, HDFC AMC [Click here](https://www.timesnownews.com/business-economy/companies/equities-have-become-a-far-more-main-line-asset-class-than-ever-before-prashant-jain-hdfc-amc-article-89862973)



## CQF

I'm pursuing CQF with Fitch Learning.

### CQF Projects

1. 7-steps to model building for your selected ticker using Random Forest Classifier. [Private Repo](https://github.com/amit-tembhurnikar/trend_RCF)

| Steps| Workflow | Remarks|
|:---------|:-----------------|:-------------------|
|Step 1| Ideation | Predict positive up moves (Up trends) above 0.25% (transaction cost)|
|Step 2| Data collection | Download data from Yahoo Finance, store on local drive|
|Step 3| Exploration Data analysis | Study Summary statistics|
|Step 4| Cleaning Dataset | Check for any null values|
|Step 5| Transformation | Perform feature scaling based on EDA|
|Step 6| Modeling | Building and training Random Forest Classifier|
|Step 7| Metrics | Validating the model performance using the score method|


Feature selection
   
| Features| Formula | Description|
|:---------------|:-----------------:|:-------------------| 
|O-C, H-L| Open - Close, High - Low | intraday price range|
|Sign| $sign (rt = ln \frac{P_t}{P_{t-1}})$ | sign of return|
|Past Return| $r_{t-1}, r_{t-2}$ | lagged returns|
|Moving Average| $ SMA_i = \frac{1}{n}\Sigma^{n-1}_{i=0} P_{t-i} $ | simple moving average|
|Momentum| $P_{t} - P_{t-k}$ | price change over k period|


#### Observations
- Test accuracy improved by 4% as compared to the earlier model, also we can see the overfitting decreased significantly.
- Model improved predictor for upside, as we can see the increase in true positive when compared to the downside.


#### Back-testing
We then compare the result of this strategy with the buy and hold and visualize the performance of the RandomForestClassifier Algorithm.


<img width="738" alt="Screenshot 2024-07-19 at 4 33 56 AM" src="https://github.com/user-attachments/assets/9ba3e2f0-5324-43bf-bae2-3c583e209650">


#### Observations of back-test:
- The CAGR return for the out-sample is 23.6%, on the higher side compared to the in-sample.
- The absolute monthly return by this strategy is negative just for 1 month, while there is also a positive return for absolute annual returns.



2. Monte Carlo Simulation for Pricing Asian Options and Lookback Options.

