# Smart Beta Portfolio and Portfolio Optimization

## Objective

- build a smart beta portfolio and compare it to a benchmark index. 
- calculate the tracking error against the index.
- build a portfolio by using quadratic programming to optimize the weights. 
- evaluate the performance: rebalance portfolio and calculate turn over.
- find the optimal rebalancing Frequency. 

## Data
end of day from Quotemedia.

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
