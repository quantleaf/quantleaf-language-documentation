In this example we do portfolio optimization using realtime data from Quandl.com. We fetch data from Quandl by building different urls. Then we calculate the returns, covariance, and model the optimization problem. The goal with the optimization function (f) is to maximize the return and minimize the variance. The weight vector w describes how much of each stock we should hold. If w = [0.5, 0.5], then it means that we should hold an equal amount of the first stock and the second stock.

To run this example you need a Quandl Account, and assign the "quandl api key" variable with your API key.


```
"Set your Quandl API key"
quandl api key = <YOUR API KEY HERE>

"Retrieve data"
stocks = [ADYEN,ALKAL]
prices = []
foreach stock in stocks
	price url = "https://www.quandl.com/api/v3/datasets/EURONEXT/" +  stock  + "/data.json?start_date=2020-11-02&end_date=2021-04-06&api_key=" + quandl api key
	price data = get(price url).dataset_data.data[:,1]'
	prices = prices add price data

"Calculate relative returns"
future =  prices[:,0:length(prices[0])-1]
past =  prices[:,1:]
returns = future  - past
absolute returns = returns
relative returns = absolute returns / past

"Perform portfolio optimization (maximize return and minimize variance)"
R = mean(relative returns')
q = 10
sigma = cov(relative returns')
f(w with shape [length(stocks),1])= R*w -  q*w'*sigma*w  s.t. sum(w) = 1, w > 0
maximize f

```
