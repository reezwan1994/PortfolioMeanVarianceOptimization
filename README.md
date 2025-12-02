## Portfolio Optimization using Mean-Variance Approach (Modern Portfolio Theory)
This project implements the classic Mean-Variance Optimization framework, pioneered by Harry Markowitz, to determine the optimal asset allocation that maximizes the Sharpe Ratio for a portfolio of diverse Exchange Traded Funds (ETFs).
The core goal is to find the "Tangency Portfolio" on the efficient frontier, balancing the trade-off between expected return and risk (volatility).
### Goal
To calculate the optimal weights for a diversified portfolio of ETFs, yielding the highest possible risk-adjusted return (Sharpe Ratio) based on historical price data.
### Methodology: Modern Portfolio Theory (MPT)
The notebook utilizes the following steps and mathematical principles:
**Data Acquisition**: Fetches 5 years of historical daily closing prices for the selected tickers using the yfinance library.

**Return Calculation**: Computes daily log returns to normalize asset performance.

**Annualized Covariance Matrix**: Calculates the annualized covariance matrix from the daily log returns, crucial for measuring the portfolio's overall risk.

**Sharpe Ratio Maximization**: Defines the portfolio's expected return, volatility, and Sharpe Ratio functions. The scipy.optimize.minimize function is then used to find the asset weights that maximize the Sharpe Ratio (by minimizing its negative value), subject to the following constraints:

__The sum of all asset weights must equal 1 (fully invested).
Individual asset weights are constrained between 10% and 40% (defined as (0.1, 0.4)).__
### Portfolio Assets
The portfolio consists of five widely-traded ETFs, representing different asset classes:
| Ticker | Description           | Asset Class |
| :---   | :---   | :--- |
| SPY    |SPDR S&P 500 ETF Trust | Broad Market Equity (Large Cap)|
| BND | Vanguard Total Bond Market ETF | Fixed Income (Bonds) |
| GLD | SPDR Gold Shares | Commodities (Gold)|
| QQQ | Invesco QQQ Trust | Growth Equity (Tech-Heavy)|
| VTI| Vanguard Total Stock Market ETF| Total Market Equity|

### Optimization Results (Maximum Sharpe Portfolio)
The optimization process identified the following optimal weights for the portfolio, providing the best return per unit of risk:
| Asset | Optimal Weight |
| :---   | :---   |
| SPY | 10.00% |
| BND | 40.00% |
| GLD | 10.00% |
| QQQ | 30.00% |
| VTI | 10.00% |

### Key Portfolio Metrics
| Metric | Value |
| :---   | :---   |
| Expected Annual Return | 13.34% |
| Expected Volatility (Risk) | 11.80% |
| Maximum Sharpe Ratio | 0.7067 |

### Setup and Requirements
To run this notebook, you will need a Python environment with the following dependencies installed:

**pip install pandas numpy yfinance scipy matplotlib**



### Running the Notebook
Clone this repository:
1. git clone https://github.com/reezwan1994/PortfolioMeanVarianceOptimization.git



2. Navigate to the project directory.
3. Open and run the Jupyter Notebook:
 PortfolioOptimizationUsingMeanVarianceApproach.ipynb

The notebook will automatically download the necessary historical data and execute the optimization.
