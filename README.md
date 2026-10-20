# Bollinger Band Mean Reversion: Backtest and Portfolio Optimisation

Python analysis testing whether a Bollinger Band mean-reversion strategy outperforms buy-and-hold across a sector-diversified portfolio of ten US large-cap stocks between 2020 and 2025, followed by the construction and comparison of optimised portfolios built from the results.

## Portfolio

MSFT, JPM, JNJ, PFE, XOM, NKE, KO, PYPL, INTC and BA, spanning technology, financials, healthcare, energy, consumer discretionary, consumer staples and industrials. The selection pairs established large caps with sustained uptrends, which provide a baseline for buy-and-hold, with stocks whose volatile or range-bound price histories make them plausible candidates for mean reversion.

## Method

1. Retrieve daily price data for 2 January 2020 to 31 December 2025 using yfinance.
2. Calculate Bollinger Bands from a 20-day simple moving average, with upper and lower bands two standard deviations from the mean.
3. Generate signals: enter long when the price closes below the lower band, enter short when it closes above the upper band, and exit once the price returns to the middle band.
4. Compare the cumulative return of the strategy with buy-and-hold for each stock.
5. Combine the higher-returning approach for each stock into a single returns series, then compare equal-weighted, maximum-Sharpe and risk-parity portfolios on annualised return, volatility and Sharpe ratio.

## Key findings

- The strategy outperformed buy-and-hold on three of ten stocks (INTC, PYPL and NKE), each of which experienced a prolonged and choppy decline. INTC returned 209.7% under the strategy against −31.2% for buy-and-hold; PYPL returned 2.7% against −47.2%.
- Buy-and-hold outperformed on stocks with sustained directional trends, such as KO (52.8% against 6.2%) and MSFT, where the strategy repeatedly shorted a rising price.
- The equal-weighted portfolio delivered an annualised return of 9.46% with annualised volatility of 22.02%.
- Maximum-Sharpe optimisation concentrated weight in the strongest historical performers, which reduced diversification and increased exposure to stock-specific risk.

## Limitations

All results are in-sample and therefore subject to backtest overfitting (Bailey et al., 2014). They indicate how the strategy behaved under 2020–2025 market conditions and should not be read as a forecast of future performance.

## Tools

Python, pandas, NumPy, yfinance, matplotlib, Jupyter
