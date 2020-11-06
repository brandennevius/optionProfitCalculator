# Contents
[Overview](#OptionProfitCalculator) \
[Options Trading Basics](#Options-Trading-Basics) \
[Goals](#Goals) \
[Challenges/Takeaways](#challengestakeaways) \
[Black Scholes Model](#black-scholes-model) \
[Project Overview](#Project-Overview) \
[Walkthrough](#Walkthrough) \
[To-Do](#To-Do) \
[Images](#Images)




# OptionProfitCalculator
The options profit calculator was built in inspiration of the [Options Profit Calculator](https://www.optionsprofitcalculator.com/). I use this tool often when analyzing stock options to trade. There is only one of these available online that allows you to visualize profits and losses, so I decided to build my own.

# Options Trading Basics
**Definition** : 
If you buy or own a stock option contract it gives you the right, but not the obligation, to buy or sell shares of a stock at a set price on or before a given date (time period). After this date, your contract expires and your option ceases to exist. 

**Types of Options** : 
1.  The **call option** gives its buyer the right to "buy" shares of a stock at a specified price on or before a given date. You buy a call option when you think the price of the underlying stock is going to go up.
2. The **put option** gives its buyer the right to "sell" shares of a stock at a specified price on or before a given date. You buy a put option when you think the price of the underlying stock is going to go down.  

# Goals
* Be the #1 used option profit calculator on the internet.
* Take a widely used tool by the trading community, make it more efficient and provide new features for the user.
* Understand the mathematics behind options trading.
* Strengthen my programming skills and pick up a new language. (JavaScript)

# Challenges/Takeaways
* A major challenge with this project was finding a low cost API source with the data points needed. Options data itself is hard to come by, so to get free options data *in real time* is even more challenging. I ended up using the yahoo-finance-low-latency API, through RapidAPIs platform, but was limited to 100 requests per day. For a single API request, I could only return data for a single expiration date, and for every stock there are many expirations. In order to get all of the data for each stock, I would have to make as many API requests for as many expirations, which is very costly. As you can see, this only allows for 6-7 tests/uses per day. This was a huge burden for testing purposes as I could only test a few times per day before running out of requests. One solution I thought of was to only make a request when the user selects a certain expiration date. The problem with this is, when myself and many other users are using this tool, they tend to click back and forth between expirations when trying to choose an option with the best risk/reward ratio. This would quickly outnumber the amount of requests vs loading all of the data upfront. This was the best solution because we kept the number of requests constant for each use and there was no time delay when switching between expiration dates, as all of the data needed for the model was pre-loaded.  
* In retrospect, this forced me to think deeply about problems, making sure my code was thoroughly planned out before running tests, since API calls were so limited.
* I became very familiar with APIs and parsing JSON data.

# Black Scholes Model
The Black Scholes Model is a widely used mathematical model for pricing an options contract. \
![Black Scholes](https://www.gstatic.com/education/formulas/images_long_sheet/en/black_scholes_model.svg)

C = Option Price \
S = Stock Price \
K = Strike Price \
r = Risk Interest Rate \
N = A Normal Distribution \
t = Time to Expiration


**Assumptions**
* Stock prices follow lognormal distributions (stock price cannot be negative)
* Implied Volatility is constant (impossible to predict future volatility)
* Brokerage fees are $0.00 and not taken into consideration

More information on this model can be found [here](https://en.wikipedia.org/wiki/Black%E2%80%93Scholes_model)

# Project Overview 
* User enters stock ticker
* Fetch from a low latency API with real time options data
* Feed data to the Black Scholes Model
* Build matrix displaying profit/loss
* Provide calculations for overview of potential trade

# Walkthrough
* User first selects the strategy they want. They then enter the stock ticker, the price is populated and all data needed from API is retrieved.
* User will then press select option button which will display all of the expiration dates for the current stock options. Once user selects an expiration, a list of all strike prices and options prices will be shown.
* Once user selects the option they want, all necessary fields are populated and they can finally click calculate which will display the grid.
* The grid shows the user the profit or loss at each date until expiration. The y-axis represent the range of potential stock prices and the x-axis shows the dates until expiration.

# To-Do
* Add standard deviations for each option, this will show the user the probability of a stock being in a certain price range.
* Add comparisons between two trades
* Make it more visually appealing
* Add it to my website for use. [BNC Stocks](www.bncstocks.com)

# Images
[Images](/images)





