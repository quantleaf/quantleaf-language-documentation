In this example we do portfolio optimization using realtime data from Quandl.com. We fetch data from Quandl by building different urls. Then we calculate the returns, covariance, and model the optimization problem. The goal with the optimization function *f* is to maximize the return and minimize the variance. The weight vector w describes how much of each stock we should hold. If w = [0.5, 0.5], then it means that we should hold an equal amount of the first stock and the second stock.

To run this example you need a Quandl Account, and assign the "quandl api key" variable with your API key.

[Run this example](https://quantleaf.com/?q=%22Set%20your%20Quandl%20API%20key%22%0Aquandl%20api%20key%20%3D%20%3CYOUR%20API%20KEY%20HERE%3E%0A%0A%22Retrieve%20data%22%0Astocks%20%3D%20%5BADYEN,ALKAL%5D%0Aprices%20%3D%20%5B%5D%0Aforeach%20stock%20in%20stocks%0A%09price%20url%20%3D%20%22https:%2F%2Fwww.quandl.com%2Fapi%2Fv3%2Fdatasets%2FEURONEXT%2F%22%20%2B%20%20stock%20%20%2B%20%22%2Fdata.json%3Fstart_date%3D2020-11-02%26end_date%3D2021-04-06%26api_key%3D%22%20%2B%20quandl%20api%20key%0A%09price%20data%20%3D%20get(price%20url).dataset_data.data%5B:,1%5D%27%0A%09prices%20%3D%20prices%20add%20price%20data%0A%0A%22Calculate%20relative%20returns%22%0Afuture%20%3D%20%20prices%5B:,0:length(prices%5B0%5D)-1%5D%0Apast%20%3D%20%20prices%5B:,1:%5D%0Areturns%20%3D%20future%20%20-%20past%0Aabsolute%20returns%20%3D%20returns%0Arelative%20returns%20%3D%20absolute%20returns%20%2F%20past%0A%0A%22Perform%20portfolio%20optimization%20(maximize%20return%20and%20minimize%20variance)%22%0AR%20%3D%20mean(relative%20returns%27)%0Aq%20%3D%2010%0Asigma%20%3D%20cov(relative%20returns%27)%0Af(w%20with%20shape%20%5Blength(stocks),1%5D)%3D%20R*w%20-%20%20q*w%27*sigma*w%20%20s.t.%20sum(w)%20%3D%201,%20w%20%3E%200%0Amaximize%20f%0A&t=code)



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
