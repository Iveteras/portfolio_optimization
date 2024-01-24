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
-
-

## Conclusion
