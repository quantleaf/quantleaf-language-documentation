
Following example will fetch data from a CSV file located on GitHub that describes house prices and some related properties. 
We use these properties to model the house price using linear regresssion.


```
house price data = get("https://raw.githubusercontent.com/ywchiu/riii/master/data/house-prices.csv")

"View a few rows of the data"
table(house price data select row from 0 to 10)

"Extract columns of interest"
prices = house price data column Price 
square feet = house price data column SqFt
bedrooms = house price data column Bedrooms

"Model house price with linear regression"
house price(square feet,bedrooms,a,b) =  a * square feet + b * bedrooms

"Define the loss between the error of the model and the true price"
prediction error(a,b) = sqrt(mean((house price(square feet,bedrooms,a,b) - prices)^2))

"Find the parameters a and b"
minimize prediction error
```