
Following example will fetch data from a CSV file located on GitHub that describes house prices and some related properties. 
We use these properties to model the house price using linear regresssion.

[Run this example](https://quantleaf.com/?q=house%20price%20data%20%3D%20get(%22https:%2F%2Fraw.githubusercontent.com%2Fywchiu%2Friii%2Fmaster%2Fdata%2Fhouse-prices.csv%22)%0A%0A%22View%20a%20few%20rows%20of%20the%20data%22%0Atable(house%20price%20data%20select%20row%20from%200%20to%2010)%0A%0A%22Extract%20columns%20of%20interest%22%0Aprices%20%3D%20house%20price%20data%20column%20Price%20%0Asquare%20feet%20%3D%20house%20price%20data%20column%20SqFt%0Abedrooms%20%3D%20house%20price%20data%20column%20Bedrooms%0A%0A%22Model%20house%20price%20with%20linear%20regression%22%0Ahouse%20price(square%20feet,bedrooms,a,b)%20%3D%20%20a%20*%20square%20feet%20%2B%20b%20*%20bedrooms%0A%0A%22Define%20the%20loss%20between%20the%20error%20of%20the%20model%20and%20the%20true%20price%22%0Aprediction%20error(a,b)%20%3D%20sqrt(mean((house%20price(square%20feet,bedrooms,a,b)%20-%20prices)%5E2))%0A%0A%22Find%20the%20parameters%20a%20and%20b%22%0Aminimize%20prediction%20error&t=code)


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