Simple 1D linear regression.

[Run this example](https://quantleaf.com/?q=%22The%20data%20to%20fit%20our%20line%20to%22%0Ax%20%3D%20%5B1,2,3,4,5,6,7%5D%0Ay%20%3D%20%5B3,5,10,5,9,14,18%5D%0A%0A%22Defining%20the%20line%22%0Af(x,k,m)%20%3D%20x*k%20%2B%20m%0A%0A%22Define%20the%20distance%20between%20the%20line%20and%20data%20points%20as%20a%20function%20of%20k%20and%20m%22%0Adistance%20from%20data(k,m)%20%3D%20(f(x,k,m)%20-%20y)%5E2%0A%0A%22Find%20k%20and%20m%20that%20minimizes%20this%20distance%22%0Aresult%20%3D%20minimize%20distance%20from%20data%0A%0A%22Show%20the%20result%20from%20the%20optimization%22%0Aprint%20result%0A%0A%22Visualsera%20datan%20samt%20den%20anpassade%20linjen%22%0Aestimated%20k%20%3D%20result.parameters.k%0Aestimated%20m%20%3D%20result.parameters.m%0A%0Ascatter%20plot(x,y,%20label%20%3D%20Observations)%20%0Aand%20plot(x,f(x,estimated%20k,estimated%20m),%20label%20%3D%20The%20line)&t=code)


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

"Visualize data and the line"
estimated k = result.parameters.k
estimated m = result.parameters.m
scatter plot(x,y, label = Observations) 
and plot(x,f(x,estimated k,estimated m), label = The line)

```
