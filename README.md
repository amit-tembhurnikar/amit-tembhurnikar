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

1. ### 7-steps to model building for your selected ticker using Random Forest Classifier. [Private Repo](https://github.com/amit-tembhurnikar/trend_RCF)

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



2. ### Monte Carlo Simulation for Pricing Asian Options and Lookback Options.


Use the Euler-Maruyama Scheme for Simulating the under-stock price for option prices of two Exotic options, Asian Options and Lookback Options

Options Type: Asian Options and Lookback Options

There are two types of Asian options: Fixed Asian option, where the strike price is fixed and the average price of underline is considered.

There are two types of Lookback options: Fixed Lookback option, where the strike price is fixed. Float Lookback option, where the average price is used in place of the strike price.

#### Step for Monte Carlo simulation,
1. Simulate the risk-neutral random walk starting at the time, t, for the value of the asset, $S_0$ over the time horizon, T. This gives one realization of the underlying price path.
2. Calculate the payoffs for the number of random walks, under the risk-neutral density $\mathbb{Q}$, 
3. Perform many more such realizations over the time horizon.
4. Calculate the average of all payoffs.
5. The option value is the present value of the average payoff.


Random walk simulation for the Monte Carlo scheme

For simulating the entire path, price paths are simulated using a discrete version of the stochastic differential equation for S, also called the Euler-Maruyama scheme,

$$ \delta S = rS\delta t + \delta S \sqrt{\delta t} \phi $$

where r is risk free interest rate and $\phi$ is from a standardized Normal distribution,

This method has an error of O($\delta t\$).


Use the expected value of the discounted payoff under the risk-neutral density $\mathbb{Q}$,

$$ V(S,t) = e^{-r(T-t)}\mathbb{E}^{\mathbb{Q}}[Payoff { (S_T)]}$$


#### Payoff for different options types

|Option type|Payoff|
|------------------------|-----------|
|European Call option |max(S-E,0)|
|European Put option |max(E-S,0)|
|Fixed Asian Call option |max(A-E,0)|
|Fixed Asian Put option |max(E-A,0)|
|Float Asian Call option |max(A-$S_T$,0)|
|Float Asian Put option |max($S_T$-A,0)|
|Fixed Lookback Call option |max(M-E,0)|
|Fixed Lookback Put option |max(E-m,0)|
|Float Lookback Call option |max(M-$S_T$,0)|
|Float Lookback Put option |max($S_T$-m,0)|

Sample Data for Initial Problem,<br>

|Parameter|Data|
|------------------------|-----------|
|Today's stock price, $S_0$|100|
|Strike, E|100|
|Time to expiry, (T-t)|1 year|
|volatility, $\sigma$|20%|
|constant risk-free interest rate, r|5%|

#### Calculated the option pricing

|Option type|Call option values|Put option values|
|---------------------------|--------------------|-------------------|
|European Option Value|10.3968|5.5939|
|Fixed Asian Option Value|5.7359|3.3372|
|Float Asian Option Value|3.4285|5.8327|
|Fixed Lookback Option Value |18.31|11.7697|
|Float Lookback Option Value|13.5071|16.5726|


## Simulated the option prices, for various inputs in data and analyzed the effects on the option price

### Calculate the Exotic Option based on the Simulated Price Path for different periods (Daily, weekly, monthly)

![newplot-4](https://github.com/user-attachments/assets/f7908517-c160-49ca-958b-fab3d71d42d5)


### Calculate the Exotic Option based on the Simulated Price Path for different stock prices $S_0$

![newplot-3](https://github.com/user-attachments/assets/307d61aa-0c0f-4027-a0c1-1ac7fcb87ce8)


### Calculate the Exotic Option based on the Simulated Price Path for the different strike prices, E

![newplot-2](https://github.com/user-attachments/assets/266037c2-0f97-4361-84a5-1916d37f3217)


### Calculate the Exotic Option based on the Simulated Price Path for different volatility, $\sigma$

![newplot](https://github.com/user-attachments/assets/145e4f88-51dd-40e5-8b7f-db87da741138)


## Conclusion 

We observe that as the Asian option payoffs are a function of the mean of the price path, the option values are always lower, as the mean is less volatile. Whereas, as the Lookback option payoffs are function min and max of price path, Option values are always higher.

Then we calculate options prices by sampling the data for different periods. As the sampling period increases the mean reduces to the final price and the payoff of the Fixed Asian option is the same as European options, i.e. for the fixed Asian option, option value increases with an increase in the sampling period. Whereas it decreases for fixed Lookback options.

As we change the underline price $S_0$, the option payoff increases with an increase in the underline price, for all the options types. Gemma for the float options is near zero.

As we change the strike price, the payoff of the Fixed Lookback option increases the most.<br>
The Delta increased significantly for the Lookback options as they tend to In-the-money.

As we change volatility, for Fixed Lookback call options, Vega is more than the Float Lookback call option. However, the opposite is true for Lookback put options.
Whereas, for Asian options, Fixed Asian options have less Vega compared to Float options.<br>
For in-the-money Fixed Asian call options and out-of-the-money Fixed Asian put options, the Vega is near zero.
