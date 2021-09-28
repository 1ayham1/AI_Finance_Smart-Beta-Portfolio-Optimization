# Smart Beta Portfolio and Portfolio Optimization


## Objective

- build a smart beta portfolio and compare it to a benchmark index. 
- calculate the tracking error against the index.
- build a portfolio by using quadratic programming to optimize the weights. 
- evaluate the performance: rebalance portfolio and calculate turn over.
- find the optimal rebalancing Frequency. 

## Data
End of day from Quotemedia. Found in data folder

## Overview

### Smart beta

- In practice, `Smart beta fund` refers to using _universe of stocks_ from an _index_, and then applying some _weighting scheme_ other than _market cap weighting_.

- A Smart Beta portfolio generally gives investors exposure or `beta` to one or more types of market characteristics (_or factors_) that are believed to predict prices while giving investors a diversified broad exposure to a particular market. 

- `Smart Beta portfolios` generally target **momentum**, **earnings quality**, **low volatility**, and **dividends** or some combination.

- Smart Beta Portfolios are generally rebalanced infrequently and follow relatively simple rules or algorithms that are passively managed.  Model changes to these types of funds are also rare requiring prospectus filings with US Security and Exchange Commission in the case of US focused mutual funds or ETFs.. Smart Beta portfolios are generally **long-only**, they do not short stocks.

### Alpha fund

- In contrast, a purely alpha-focused quantitative fund may use multiple models or algorithms to create a portfolio. 
- The portfolio manager retains discretion in upgrading or changing the types of models and how often to rebalance the portfolio in attempt to maximize performance in comparison to a stock benchmark.  
- Managers may have discretion to **short** stocks in portfolios.

### Deciding upon portfolio weighting methods

One way to design portfolio is to look at certain accounting measures (_fundamentals_) that, based on past trends, indicate stocks that produce better results. 

> start with a hypothesis that dividend-issuing stocks tend to perform better than stocks that do not. ***Example***:
>>Companies that regularly issue dividends may also be more prudent in allocating their available cash, and may indicate that they are more conscious of prioritizing shareholder interests. _So according to this hypothesis_, dividends may be both a `proxy` for how the company is doing (in terms of earnings and cash flow), but also `a signal` that the company acts in the best interest of its shareholders.

> Another hypothesis, is that one  wishes to design a portfolio that can then be made into an ETF.  Investors may wish to invest in `passive beta funds`, but wish to have less risk exposure (`less volatility`) in their investments.  The goal of having a low volatility fund that still produces returns similar to an index may be appealing to investors who have a ***shorter investment time horizon***, and so are more risk averse.
>> So the objective is to design a portfolio that closely tracks an `index`, while also ***minimizing*** the `portfolio variance`.  Also, if this portfolio can match the returns of the index with less volatility, then it has a higher risk-adjusted return (same return, lower volatility).

Smart Beta ETFs can be designed with both of these two general methods (among others): `alternative weighting` and `minimum volatility` ETF. 

## Packages and Dependencies 

- [Pandas](https://pandas.pydata.org/) and [Numpy](http://www.numpy.org/)
- `helper`, `project_helper`, and `project_tests`. These are custom packages built to help solve the problems.  The `helper` and `project_helper` module contains utility functions and graph functions. The `project_tests` contains the unit tests for all the problems.

For a complete list, check `requirements.txt`


## Portfolio Optimization Strategy

Create a second portfolio that still reuses the market cap weighted index, but it will be independent of the dividend-weighted portfolio that was created in part 1.

>**Objective**:  We want to both minimize the portfolio variance and also want to closely track a market cap weighted index.  In other words, we're trying to minimize the distance between the weights of our portfolio and the weights of the index.

<img src="https://latex.codecogs.com/svg.latex?\Large&space;x=$Minimize \left [ \sigma^2_p + \lambda \sqrt{\sum_{1}^{m}(weight_i - indexWeight_i)^2} \right  ]$" title="\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" />
 where $m$ is the number of stocks in the portfolio, and $\lambda$ is a scaling factor that you can choose.

**Why?**

One way that investors evaluate a fund is by how well it tracks its index. The fund is still expected to deviate from the index within a certain range in order to improve fund performance.  A way for a fund to track the performance of its benchmark is by keeping its asset weights similar to the weights of the index.  We’d expect that if the fund has the same stocks as the benchmark, and also the same weights for each stock as the benchmark, the fund would yield about the same returns as the benchmark. By minimizing a linear combination of both the portfolio risk and distance between portfolio and benchmark weights, we attempt to balance the desire to minimize portfolio variance with the goal of tracking the index.
## Sample Results

- ETF and index cumulative returns

![etf](/graphs/smart_beta_etf.png)



- Optimized ETF vs Index

![optim](/graphs/optim.png)


## Reference, Project Description, Startup code
[Artificial Intelligence for Trading on Udacity](https://www.udacity.com/course/ai-for-trading--nd880)

