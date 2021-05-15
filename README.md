# Quantleaf Language
Two things to note. The project is currently in testing phase. Which means, major changes could occur. 
The documentation below is in english but the Quantleaf Language can also be written in Swedish, but is not yet documented.

For a quick "deep dive" [check this linear regression example](https://github.com/quantleaf/quantleaf-language-documentation/blob/master/examples/linear-regression-one-variable.md), or see [other examples here](https://github.com/quantleaf/quantleaf-language-documentation/tree/master/examples).


# Documentation

## Print
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

## Variables
```
some variable = 123
some variable = hello world
some variable = "hello world"
```

## Lists
### Creating
```
a list = A,B,C
a list = [1,2,3]
a complex kind of list = [[A,"B",123],[456,???,hello world]]
a list of todos contains do laundry, cleaning and call grandma
```
### Adding elements

```
a list = [] 
a list with an element = a list add "hello world"
```
### Removing elements

```
a list = [hello world] 
a list without an element = a list remove "hello world"
```

### Transpose 
```
a list = [1,2,3]'
a list = tranpose([1,2,3])
```

### Accessing elements

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



## Looping

```
for i = 1 to 10 print (i)
foreach fruit in [banana, apple, kiwi] print fruit
```

## If, Else If, Else
```
if 2 > 1
  print hello
else if 3  > 2 print world
else
  print "something"
```

## Functions
```
f(x) = x^2

f(x) { x^2 }

f(x)
  x^2


taste(fruit) if fruit = apple good else bad

taste(fruit)
  if fruit equals apple
    return good
  return bad
  
taste(fruit)
{
  if(fruit == apple)
    return good
  bad
}
```

## Objects, accessing properties
```
some data object = get <URL THAT RETRIEVES JSON>
some property = property of some data object
same property = some data object.property
```
## Mathematical Optimization
### Unconstrained
```
f(x) = x^2 
print(minimize f)
```
### Constrained
```
f(x) = x^2 s.t. x > 0
print(minimize f)
```

```
print(minimize f(x) = x^2 s.t. x > 0)
```

## HTTP GET request
```
some data = get <YOUR URL>
```

### If data is CSV (you can treat the variable as a matrix)
```
some data = get <YOUR CSV URL>
print(some data[2,3])
```

## Comments
```
"Comments are written with surrounding quotation symbols"
print 1 + 1
```

## Visualization
### Line plot
```
x = [1,2,3]
y = [3,4,5]
plot(x,y, label = Some line)
```
### Histogram chart
```
x = [1,2,3,3,3,3,4,5,5,5,5,5]
histogram(x, bars = 4, label = Some histogram)
```

### Bar chart
```
x = [apple, apple, orange, pineapple]
bar chart(x,label = Fruits)
```

### Scatter plot
```
x = [1,2,3]
y = [3,4,5]
scatter plot(x,y)
```

### Combining charts/plots
Use the word "and" or ","
```
x = [1,2,3]
y = [3,4,5]
z = [1,2,3,3,3,3,3,4]
plot(x,y, label = Some line) and histogram(z)
```


### Table
This method will try to convert content into a table and visualize it
```
table(get(<YOUR CSV URL>))
```


