# Quantleaf Language Documentation & Examples

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
a list of todos contains do laundry, cleaning and calling grandma
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

## Objects
```
some data object = get <URL THAT RETRIEVES JSON>
some property = property of some data object
same property = some data object.property
```
## Mathematical Optimization (ML)
```
f(x) = x^2 
print(minimize f)
```

## GET request
```
some data = get <YOUR URL>
```

### If data is CSV (you can treat the variable as an matrix)
```
some data = get <YOUR CSV URL>
print(some data[2,3])
```

### Comments
```
Comments are just comments, just write them anywhere
print 1 + 1
```
## More...
This was a basic introduction. More to come! 



