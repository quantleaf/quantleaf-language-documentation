# Quantleaf Language
The Quantleaf Language is a natural language like programming language. The purpose of this language is to make programming something that more people could enjoy. 

You do not need to install anything to start writing code. Just visit [quantleaf.com](https://quantleaf.com) and get started.

For a quick "deep dive" [check this linear regression example](https://quantleaf.com/?q=%22The%20data%20to%20fit%20our%20line%20to%22%0Ax%20%3D%20%5B1,2,3,4,5,6,7%5D%0Ay%20%3D%20%5B3,5,10,5,9,14,18%5D%0A%0A%22Defining%20the%20line%22%0Af(x,k,m)%20%3D%20x*k%20%2B%20m%0A%0A%22Define%20the%20distance%20between%20the%20line%20and%20data%20points%20as%20a%20function%20of%20k%20and%20m%22%0Adistance%20from%20data(k,m)%20%3D%20(f(x,k,m)%20-%20y)%5E2%0A%0A%22Find%20k%20and%20m%20that%20minimizes%20this%20distance%22%0Aresult%20%3D%20minimize%20distance%20from%20data%0A%0A%22Show%20the%20result%20from%20the%20optimization%22%0Aprint%20result%0A%0A%22Visualsera%20datan%20samt%20den%20anpassade%20linjen%22%0Aestimated%20k%20%3D%20result.parameters.k%0Aestimated%20m%20%3D%20result.parameters.m%0A%0Ascatter%20plot(x,y,%20label%20%3D%20Observations)%20%0Aand%20plot(x,f(x,estimated%20k,estimated%20m),%20label%20%3D%20The%20line)&t=code), or see [other examples here](https://github.com/quantleaf/quantleaf-language-documentation/tree/master/examples).

Two things to note. The project is currently in the testing phase which means major changes could occur. 
The documentation below is in English but the Quantleaf Language can also be written in Swedish, but is not yet well documented. The language will also in the future support/understand more languages (and is by design intended of doing so). 

You can get help with issues [here](https://github.com/quantleaf/quantleaf-language-documentation/issues).


## Documentation

### Print
```
print(1+1)
```

or 

```
print 1+1
```

or end your program with some value

```
sqrt(2)
```

### Variables
Variable names are case insensitive. Variable names can contain spaces.

A number
```
some variable = 123
```
A string (text) variable.
```
some variable = "hello world"
```

A string (text) variable. Quations can be omitted for string variables if the string is "meaningless"
```
some variable = hello world
```


### Lists
#### Creating
```
a list = A,B,C
```
or
```
a list = [1,2,3]
```
Example of two dimensional (a matrix)
```
a complex kind of list = [[A,"B",123],[456,???,hello world]]
```
You can also use the word "contains" to build a list
```
a list of todos contains do laundry, cleaning and call grandma
```
#### Adding elements

```
a list = [] 
a list with an element = a list add "hello world"
```
#### Removing elements

```
a list = [hello world] 
a list without an element = a list remove "hello world"
```

#### Transpose 
Flip a matrix along its diagonal
```
a list = [1,2,3]'
```
or
```
a list = transpose([1,2,3])
```

#### Accessing elements

Indexing starts at 0 (first element starts at position 0)


Select row by indices
```
the best fruits = [banana, orange]
print the best fruits [0]
```


Select row by ranges
```
some matrix = [[1,2,3],[4,5,6]]
a smaller matrix  = some matrix[0,1:3]
print(a smaller matrix)
```
or 
```
some matrix = [[1,2,3],[4,5,6]]
a smaller matrix  = some matrix row 0 and column from 1 to 3
print(a smaller matrix)
```


You can select columns and rows by value. If you select a column with name "Apple", you expect the first row to contain the element "Apple" somewhere. The selected column will not include the first row. Same concept holds for rows. 
```
fruit price matrix = [[Apple, Orange],[2,3]]
apple price = fruit price matrix column Apple
print(apple price)
```



### Looping

```
for i = 1 to 10 print (i)
```
or
```
foreach fruit in [banana, apple, kiwi] print fruit
```

### If, Else If, Else conditions
```
x = 123
if x > 1
    print hello
else if x = 2 
    print world
else
    print "something"
```

### Functions

#### Defining functions

You can write function in many different ways.
Functions can return values, by writing *return* before something, or by writing the value last. A few examples of **equivalent** functions.
```
f(x) = x^2
```
```
f(x)
    x^2
```

```
f(x) { x^2 }
```
```
f(x) = 
{ 
    x^2 
}
```
```
f(x) 
    return x^2 
```
```
f(x)
    square = x^2
    square
```


Below are some small examples of the **same** program using *if* statements and *return* statements (which lets us exit functions before the end is reached)

```
taste(fruit) if fruit = apple good else bad
```

```
taste(fruit)
    if fruit equals apple
        return good
    return bad
```

```
taste(fruit)
{
    if(fruit == apple)
        return good
    bad
}
```
#### Call/Use functions
You can pass arguments by position or assign by name (or both).

By position
```
f(x,y)=x*y
print(f(1,2))
```

By name
```
f(x,y)=x*y
print(f(y=2,x=1))
```
### Objects, accessing properties
```
some data object = get <URL THAT RETRIEVES JSON>
some property = property of some data object
same property = some data object.property
```
### Mathematical Optimization
#### Unconstrained
```
f(x) = x^2 
print(minimize f)
```
#### Constrained
```
f(x) = x^2 s.t. x > 0
print(minimize f)
```

```
print(minimize f(x) = x^2 s.t. x > 0)
```

### HTTP GET request
```
some data = get <YOUR URL>
```

#### CSV data from HTTP GET
```
some data = get <YOUR CSV URL>
print(some data[2,3])
```

### Comments
```
"Comments are written with surrounding quotation symbols"
print 1 + 1
```

### Visualization
#### Line plot
```
x = [1,2,3]
y = [3,4,5]
plot(x,y, label = Some line)
```
#### Histogram chart
```
x = [1,2,3,3,3,3,4,5,5,5,5,5]
histogram(x, bars = 4, label = Some histogram)
```

#### Bar chart
```
x = [apple, apple, orange, pineapple]
bar chart(x,label = Fruits)
```

#### Scatter plot
```
x = [1,2,3]
y = [3,4,5]
scatter plot(x,y)
```

#### Combining charts/plots
Use the word "and" or ","
```
x = [1,2,3]
y = [3,4,5]
z = [1,2,3,3,3,3,3,4]
plot(x,y, label = Some line) and histogram(z)
```


#### Table
This method will try to convert content into a table and visualize it
```
table(get(<YOUR CSV URL>))
```


