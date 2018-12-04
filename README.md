# QuantTrading_Decal

This is a repo for the Fall 2018 Quantitative Trading Decal at UC Berkeley.

The objective of the project is the test whether sentiment of content in Youtube videos would be a sufficiently accurate indicator of future stock success.

## General Results
Category | Return | Max Drawdown
--- | --- | --- |
Top 15 Prevalence in Youtube Videos | Return rate -0.00097 | Drawdown -10000
Top 10 Prevalence in Youtube Videos | Return rate 0.01975| Drawdown -3000
Top 5 Prevalence in Youtube Videos | Return rate -0.00718| Drawdown -3000
Tech Stocks | Return rate 0.0| Drawdown -3000
Food & Beverage Stocks | Return rate 0.03010100000000006| Drawdown -3000
Transportation Stocks | Return rate 0.03010100000000006| Drawdown -3000
Nontech Stocks |  Return rate 0.0 | Drawdown -3000

Market average 2%

company_list=[
"Apple",
"Netflix",
"McDonald's",
"Facebook,",
"CBS",
"eBay",
"Starbucks",
"Microsoft",
"Ford",
"Nvidia",
"HP",
"FedEx",
"Lockheed",
"Nike",
"Verizon"]

index Ticker Model
0	Apple	SVR(C=1.0, cache_size=200, coef0=0.0, degree=3...
1	Netflix	LinearRegression(copy_X=True, fit_intercept=Tr...
2	McDonald's	LinearRegression(copy_X=True, fit_intercept=Tr...
3	Facebook,	LinearRegression(copy_X=True, fit_intercept=Tr...
4	CBS	LinearRegression(copy_X=True, fit_intercept=Tr...
5	eBay	LinearRegression(copy_X=True, fit_intercept=Tr...
6	Starbucks	TheilSenRegressor(copy_X=True, fit_intercept=T...
7	Microsoft	LinearRegression(copy_X=True, fit_intercept=Tr...
8	Ford	TheilSenRegressor(copy_X=True, fit_intercept=T...
9	Nvidia	TheilSenRegressor(copy_X=True, fit_intercept=T...
10	HP	SVR(C=1.0, cache_size=200, coef0=0.0, degree=3...
11	FedEx	TheilSenRegressor(copy_X=True, fit_intercept=T...
12	Lockheed	TheilSenRegressor(copy_X=True, fit_intercept=T...
13	Nike	SVR(C=1.0, cache_size=200, coef0=0.0, degree=3...
14	Verizon	TheilSenRegressor(copy_X=True, fit_intercept=T...

Sample transaction log:
Stock:  Apple
Bought at 170.15
Bought at 169.98
Sold at 173.07
Profit 292.0
Profit 309.0
Bought at 171.05
Bought at 169.37
Sold at 173.03
Profit 198.0
Profit 366.0
Sold at 175.0
Sold at 177.09
Sold at 174.22
Bought at 159.54
Profit 1546.0
Profit 1755.0
Profit 1468.0
Sold at 176.21
Bought at 168.34
Stock:  Netflix
Sold at 185.2
Sold at 221.23
Sold at 261.279
Sold at 278.52
Sold at 278.52
Sold at 291.38
Sold at 290.39
Profit -10519.0
Profit -6916.0
Profit -2911.0999999999985
Profit -1187.0
Profit -1187.0
Profit 99.0
Profit 0.0
Stock:  McDonald's
Sold at 174.06
Sold at 173.57
Sold at 178.36
Bought at 163.9
Profit 1016.0
Profit 967.0
Profit 1446.0
Bought at 157.04
Profit 0.0
Stock:  Facebook,
Sold at 178.39
Sold at 187.87
Profit 103.0
Profit 1051.0
Stock:  CBS
Bought at 57.43
Bought at 57.2
Bought at 58.13
Bought at 60.08
Bought at 60.0
Bought at 50.95
Profit -648.0
Profit -625.0
Profit -718.0
Profit -913.0
Profit -905.0
Profit 0.0
Stock:  eBay
Bought at 35.2
Bought at 38.37
Bought at 37.92
Bought at 38.02
Bought at 38.02
Bought at 43.81
Bought at 43.81
Profit 860.9999999999995
Profit 544.0000000000005
Profit 589.0
Profit 578.9999999999995
Profit 578.9999999999995
Profit 0.0
Profit 0.0
Stock:  Starbucks
Bought at 58.01
Bought at 57.58
Bought at 61.09
Bought at 55.38
Profit -263.0
Profit -220.0
Profit -571.0
Profit 0.0
Stock:  Microsoft
Bought at 82.4
Bought at 83.11
Bought at 84.88
Bought at 88.28
Bought at 92.74
Bought at 90.81
Bought at 92.72
Bought at 96.54
Profit 1414.0
Profit 1343.0
Profit 1166.0
Profit 826.0
Profit 380.0
Profit 573.0
Profit 382.0
Profit 0.0
Stock:  Ford
Bought at 12.02
Bought at 12.63
Bought at 11.96
Bought at 10.24
Bought at 10.61
Bought at 10.58
Profit -144.0
Profit -205.0
Profit -138.0
Profit 34.0
Profit -3.0
Profit 0.0
Stock:  Nvidia
Sold at 225.58
Sold at 245.33
Profit -1975.0
Profit 0.0
Stock:  HP
Bought at 22.92
Bought at 22.92
Profit 0.0
Profit 0.0
Stock:  FedEx
Sold at 248.5
Sold at 240.82
Sold at 241.31
Profit 719.0
Profit -49.0
Profit 0.0
Stock:  Lockheed
Sold at 313.74
Sold at 336.25
Sold at 341.78
Profit -2804.0
Profit -553.0
Profit 0.0
Stock:  Nike
Bought at 68.29
Profit 0.0
Stock:  Verizon
Bought at 52.83
Bought at 51.86
Profit -97.0
Profit 0.0
Capital left 99903.0
Return rate -0.00097

## Documentation

1. Loaded subtitle data from 14.11.17 to 14.6.18
2. Sentiment analysis on content to obtain sentiment feature
3. Took a list of all NYSE stocks and ran their split names through the subtitles content to check for prevlance.
4. Returned table of frequency of company names in videos, picked top 5-15 companines mentioned in the subtitle data (list of all companies that have mentions/occurrences in more than 0.000315 of Youtube Videos) -> plotted patterns of sentiment per ticker
5. Loaded stock ticker data in time range
6. Plotted sentiment against Close price (FedEx and Verizon had -100% correlation)
7. Trained on machine learning models and automatically selected most accurate model for each stock ticker (variables: 'sentiment', 'views', 'likes', 'dislikes', 'comment_count') - used 20% of dataset for training, 80% for strategy evaluation.
8. Set capital of 100,000, transaction quantity as 100 shares and initial trading parameters: we compare current price at each time step to a predicted price (using the respective model) and when buycounter hits 3 or great change in price, then we execute a buy trade (likewise for sell); if there are any outstanding trades on last day, we close the trades.
9. Calculate profit through orderbook mechanism (Display profit per trade as graph). 

Main parameters to optimize model: buy/sell trigger, statistical model, dataset, stock portfolio selection
