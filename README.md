# Stock analysis
## Idea:
The idea of this project was to analyze how the stock of the biggest companies in the world behave when there is a day, week, or month that has a big price change. 
My claim is that if the price changes two times the mean price change of the stock for a time interval, then for the next time interval the price change will go in the opposite direction.

Note: The stock goes either up or down, positive or negative price change, and this is what I mean when I am referring to the direction of the price movement. 

## Approach:
1. Find the dates (intervals) where there was a price change of two times or more than the mean price change. 
2. Analyze the price change of the next interval, including the price change and the direction of the price change.  
3. Calculate the average price change for the next interval, for both when it follows the idea of the initial claim and when it does the opposite. 
4. Calculate the expected value, if we would make an investment based on the initial claim. 

## Data:
I downloaded the data from using the 'pandas_datareader' library, and the data comes from Yahoo Finance.

## Information collected from the analysis:
For this part I will use the company Apple (ticker: AAPL) as an example, but in the actual Python Notebook, I did the analysis on 7 companies with a considerable weight in the S&P 500 (according to https://www.slickcharts.com/sp500), which are: Apple Inc (AAPL), Microsoft Corp (MSFT), Amazon.com Inc (AMZN), Nvidia Corp (NVDA), Alphabet Inc Cl A (GOOGL), Meta Platforms Inc Class A (META), and Tesla Inc (TSLA).
For simplicity I will also consider the interval to be daily, but the program can analyze the daily, weekly and monthly intervals. 

- Mean price change: 1.429564
- Distribution of days where we had considerable price change over the years: ![apple_dist1](https://github.com/thimura/stock_analysis/assets/49618034/5ad0fa1a-e080-410c-824b-76c69a336f39)

- Probability that the initial claim works: 0.5490196078431373
- Distribution including the number of intervals where the initial claim holds: ![apple_dist2](https://github.com/thimura/stock_analysis/assets/49618034/9edd1268-63c5-46e1-ba3a-54ef9fcfa06f)

- Average gain: 2.4108924321910163
- Average loss: 2.9349994826673242
- Expected value: 2.220446049250313e-16

## Results:
Below we have a table with the expected value for all companies and for all intervals:
| Interval |    AAPL     |     MSFT    |    AMZN     |    NVDA     |    GOOGL    |    META     |    TSLA     | 
| -------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | 
|  Daily   | 2.2204e-16  | 0.0         | -2.2204e-16 | -4.4409e-16 | 2.2204e-16  | 2.2204e-16  | 2.2204e-16  | 
|  Weekly  | 0.0         | -4.4409e-16 | 4.4409e-16  | -4.4409e-16 | 0.0         | -4.4409e-16 | 0.0         |
|  Monthly | -8.8818e-16 | 8.8818e-16  | 0.0         | -8.8818e-16 | -4.4409e-16 | 0.0         | 0.0         |
