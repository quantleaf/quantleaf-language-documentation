# Quantleaf Language Documentation & Examples

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
a list with an element = a list + "hello world"
```
### Removing elements

```
a list = [hello world] 
a list without an element = a list - "hello world"
```

### Transpose 
```
a list = [1,2,3]'
a list = tranpose([1,2,3])
```

### Accessing elements (Python syntax)
```
the best fruits = [banana, orange]
print the best fruits [0]

some matrix = [[1,2,3],[4,5,6]]
a smaller matrix  = some matrix[1:,2:3]

fruit price matrix = [[Apple, Orange],[2,3]]
apple price = fruit price matrix column Apple and row 1
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
histogram(x, bars = 2, label = Some histogram)
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


