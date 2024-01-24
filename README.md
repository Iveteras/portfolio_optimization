# Portifolio optimization

## About 

This project consists in find the best match for each stock in a pairing of 50% of each asset in a fake portfolio.

## Technologies
```python
# Data manipulation
import pandas as pd
import numpy as np

# Webscraping
from bs4 import BeautifulSoup as bs
import requests

# Assets data
import yfinance as yf

# Charts
import seaborn as sns
import matplotlib.pyplot as plt 
```
## Phase 1
**File:** [*getting_data.ipynb*](https://github.com/Iveteras/portfolio_optimization/blob/main/scripts/getting_data.ipynb)
- **Step one:** *Get all S&P 500 stock symbols from wikipedia. I did this because i needed the stock symbol to use yfinance api.*
- **Step two:** *Discover the 30 most traded stocks, so I can use them in the study.*
- **Step three:** *Get all the data from yfinance.*


## Phase 2
**File:** [*portfolio_optimization.ipynb*](https://github.com/Iveteras/portfolio_optimization/blob/main/scripts/portfolio_optimization.ipynb)
- **Step one:** *Discover the risk-return of each stock. I used standard deviation of the daily price variation for the risk. For the return i used the daily amount of gains (close price - open price + dividends).*
- **Step two:** *Understand the correlation between assets. For a good diversification, it is good a weak correlation.*
- **Step three:** *Calculate the risk-return of each asset pair. I used a proportion of 50% of each stock and applied the risk-return formula.*
```python
    # w = weight == 0.5
    # r = return of a stock
    # v = volatility
    # corr = correlation between assets

    p_return = (w1 * r1) + (w2 * r2) 
    p_risk = np.sqrt((w1*w1*v1*v1) + (w2*w2*v2*v2) + 2*w1*w2*corr)
```
- **Step four:** *Choose the best pair considering the risk-return. For this i used Sharpe Ratio index.* <br>
  Sharpe Ratio = (average return - risk-free rate) / risk
  
## Conclusion
- The best asset by far was AAL (American Airlines), but that was due a sharpe ratio failure.<br>
- The thing is AAL has the worst average return of all stocks, a negative average return. When it goes in the sharpe ratio formula, that has a 'minus risk free return', the value goes to positive, making a high sharpe ratio.
- Next steps: Find another index to rank correlation between risk-return
