# Static vs. Dynamic Portfolios

## Context
This dataset is part of a comprehensive analysis project focused on understanding the performance and risk characteristics of different portfolio models over a 13-year period (2011-2024). The project aims to compare static and dynamically rebalanced portfolios to evaluate their risk-adjusted returns, volatility, and drawdowns.

## Inspiration
A couple of years ago, I began my journey into finances and became interested in investing. I've put considerable thought into how and where to invest. The Swensen model seemed reliable, so I decided to test it out in this first Data Analysis project of mine. I am interested in developing a career in Data Science, particularly in finance.

## Swensen Model
The Swensen model, developed by David Swensen, advocates for a diversified portfolio allocation, typically including domestic and international stocks, emerging markets, real estate investment trusts (REITs), and bonds. This model aims to balance risk and return through strategic asset allocation and periodic rebalancing.

Following Swensen's model, the stock allocation for the portfolio is as follows: 30% U.S. stocks, 15% developed markets, 5% emerging markets, 20% Real Estate (REITs), and 30% bonds.

In this project, I use three different configurations of asset selection:

1. **First Configuration**:
   - **VOO (U.S. stocks)**: 30%
   - **VEA (developed markets)**: 15%
   - **VWO (emerging markets)**: 5%
   - **FUNO11.MX (Real estate)**: 20%
   - **28-day CETES (bonds)**: 30%

2. **Second Configuration**:
   - Substitutes VOO with QQQ (U.S. stocks): 30%

3. **Third Configuration**:
   - Substitutes VOO, VEA, VWO with VT (Global Equity): 50%

In the code, the three configurations are identified with the suffixes _voo, _qqq, and _vt.

## Asset Descriptions

- **VOO (Vanguard S&P 500 ETF)**:
  - **Description**: An exchange-traded fund (ETF) that seeks to track the performance of the S&P 500 Index, which includes 500 of the largest companies in the U.S. stock market.
  - **Sector**: Broad U.S. Equity
  - **Primary Holdings**: Large-cap U.S. stocks

- **VEA (Vanguard FTSE Developed Markets ETF)**:
  - **Description**: An ETF that aims to track the performance of the FTSE Developed All Cap ex U.S. Index, which includes stocks from developed markets outside the U.S., including Canada, Europe, and the Pacific region.
  - **Sector**: International Developed Markets Equity
  - **Primary Holdings**: Large-, mid-, and small-cap stocks from developed markets

- **VWO (Vanguard FTSE Emerging Markets ETF)**:
  - **Description**: An ETF designed to track the performance of the FTSE Emerging Markets All Cap China A Inclusion Index, which covers stocks from emerging markets worldwide.
  - **Sector**: Emerging Markets Equity
  - **Primary Holdings**: Large-, mid-, and small-cap stocks from emerging markets

- **QQQ (Invesco QQQ Trust)**:
  - **Description**: An ETF that tracks the Nasdaq-100 Index, which comprises 100 of the largest non-financial companies listed on the Nasdaq Stock Market.
  - **Sector**: U.S. Technology and Growth
  - **Primary Holdings**: Large-cap technology and growth stocks

- **VT (Vanguard Total World Stock ETF)**:
  - **Description**: An ETF that seeks to track the performance of the FTSE Global All Cap Index, which includes a broad range of stocks from both developed and emerging markets worldwide.
  - **Sector**: Global Equity
  - **Primary Holdings**: Large-, mid-, and small-cap stocks globally

- **FUNO11.MX (Fibra Uno)**:
  - **Description**: A Mexican real estate investment trust (REIT) that invests in and manages a diversified portfolio of commercial real estate properties in Mexico.
  - **Sector**: Real Estate
  - **Primary Holdings**: Commercial properties, including retail, industrial, and office spaces

- **28 Day CETES (Certificados de la Tesorería de la Federación)**:
  - **Description**: Mexican government treasury certificates with a 28-day maturity, often used as a short-term, risk-free investment option.
  - **Sector**: Government Bonds
  - **Primary Holdings**: Short-term Mexican government debt

## Static vs. Dynamic Portfolios
As mentioned in the title, this project analyzes static vs. dynamic portfolios:

- **Static Portfolios**: The percentages remain the same for each of the three configurations during the whole period (2011-2024).
- **Dynamic Portfolios**: The percentages are adjusted according to the 110 rule. Assuming the investment began at 20 years old in 2011, the initial allocations are:
  - **VOO Configuration**: VOO - 35%, VEA - 20%, VWO - 10%, FUNO11.MX - 25%, CETES - 10%
  - **QQQ Configuration**: QQQ - 35%, VEA - 20%, VWO - 10%, FUNO11.MX - 25%, CETES - 10%
  - **VT Configuration**: VT - 65%, FUNO11.MX - 25%, CETES - 10%

Each year, the percentages are adjusted by 1%, taking 1% from the stocks and adding it to bonds.

## The 110 Rule
The 110 rule is a simple heuristic for portfolio allocation that suggests subtracting your age from 110 to determine the percentage of your portfolio that should be invested in stocks, with the remainder in bonds. This rule was applied annually in the dynamic portfolios to adjust the allocations accordingly.

## Files Included
- `portfolio_analysis.ipynb`
- `portfolio_data.xlsx`
- `rolling_volatility.png`
- `annual_returns.png`
- `cumulative_returns.png`
- `drawdown.png`

## Acknowledgements
I acknowledge Yahoo Finance and Banxico for providing the data.

## Personal Note
As a Mexican, I used Mexican bonds for these portfolios, and the other tickers are also available from Mexico.

## Conclusions
The analysis of static and dynamic portfolios over a 13-year period yielded several key insights:

1. **Performance Comparison**:
   - Dynamic portfolios generally showed higher cumulative returns compared to static portfolios. This suggests that periodic rebalancing according to the 110 rule can enhance long-term growth.

2. **Volatility and Risk**:
   - Dynamic portfolios exhibited higher annual volatility than static portfolios. This indicates that while dynamic rebalancing can improve returns, it also introduces greater short-term risk.
   - Maximum drawdowns were slightly higher for dynamic portfolios, highlighting increased exposure to market downturns.

3. **Risk-Adjusted Returns**:
   - Despite higher volatility, dynamic portfolios maintained good risk-adjusted returns, as indicated by Sortino Ratios. This demonstrates effective downside risk management.

4. **Rebalancing Impact**:
   - Annual rebalancing according to the 110 rule gradually shifted more weight into bonds, reducing exposure to equities over time. This aligns with the goal of lowering risk as the investor ages.

5. **Asset Allocation**:
   - The Swensen model's diversified allocation across U.S. stocks, international markets, emerging markets, real estate, and bonds provided a balanced approach to risk and return.
   - Configurations with QQQ and VT showed differing performance dynamics, emphasizing the importance of asset selection in portfolio strategy.

## Recommendations
1. **Dynamic Rebalancing**: Consider dynamic rebalancing strategies for potentially higher returns, but be aware of the increased volatility and drawdown risks.
2. **Long-Term Perspective**: Maintain a long-term investment horizon to mitigate the impact of short-term volatility.
3. **Periodic Review**: Regularly review and adjust portfolio allocations to align with changing risk tolerance and market conditions.

## Future Work
1. **Rebalancing Frequencies**: Explore different rebalancing frequencies (e.g., quarterly, semi-annually) to optimize performance and risk.
2. **More in-depth analysis of rebalancing effects on volatility**.
3. **Individual asset analysis**.

By understanding the performance dynamics of static and dynamic portfolios, investors can make informed decisions that align with their financial goals and risk tolerance. This project also highlights the importance of diversification and strategic asset allocation in managing investment portfolios.
