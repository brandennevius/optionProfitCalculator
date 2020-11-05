# OptionProfitCalculator
The options profit calculator was built in inspiration of the [Options Profit Calculator](https://www.optionsprofitcalculator.com/). I use this tool often when analyzing stock options to trade. There is only one of these available online that allows you to visualize profits and losses, so I decided to build my own, but better. 

# Options Trading Baiscs
**Definition** : 
If you buy or own a stock option contract it gives you the right, but not the obligation, to buy or sell shares of a stock at a set price on or before a give date (time period). After this date, your contract expires and your option ceases to exist. \
**Types of Options** : 
1.  The **call option** gives its buyer the right, but not the obligation, to "buy" shares of a stock at a specified price on or before a given date. You buy a Call option when you think the price of the underlying stock is going to go up.
2. The **put option** gives its buyer the right, but not the obligation, to "sell" shares of a stock at a specified price on or before a given date. You buy a Put option when you think the price of the underlying stock is going to go down.  

# Black Scholes Model
The Black Scholes Model is the model I use to determine to predicted price of the optionat a given time.
![Black Scholes](https://www.gstatic.com/education/formulas/images_long_sheet/en/black_scholes_model.svg)

C = Option Price \
S = Stock Price \
K = Strike Price \
r = Risk Interest Rate \
N = A Normal Distribution \
t = Time to Epiration


**Assumptions**
* Stock prices follow lognormal distributions(a stock price cannot be negative)
* Model assumes Implied Volatility is constant
* Brokerage fees are 0 and not taken into consideration

More information on this model can be found [here](https://en.wikipedia.org/wiki/Black%E2%80%93Scholes_model)

# Project Overview 
* Get stock options data from finance API
* Feed Data to Black Scholes Model
* Build matrix displaying profit/loss

# Walkthrough
* User first selects how many 'legs' they want, which depends on their strategy. They then enter the stock ticker, the price is populated and data from API is retrieved.
![image](StockData.png)
* 

# To-Do:














