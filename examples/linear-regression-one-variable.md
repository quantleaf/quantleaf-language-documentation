Simple 1D linear regression.


```
"The data to fit our line to"
x = [1,2,3,4,5,6,7]
y = [3,5,10,5,9,14,18]

"Defining the line"
f(x,k,m) = x*k + m

"Define the distance between the line and data points as a function of k and m"
distance from data(k,m) = (f(x,k,m) - y)^2

"Find k and m that minimizes this distance"
result = minimize distance from data

"Show the result from the optimization"
print result

"Visualsera datan samt den anpassade linjen"
estimated k = result.parameters.k
estimated m = result.parameters.m

scatter plot(x,y, label = Observations) 
and plot(x,f(x,estimated k,estimated m), label = The line)

```