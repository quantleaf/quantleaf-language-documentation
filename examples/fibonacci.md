Calculate some fibonacci numbers

[Run this example](https://quantleaf.com/?q=fib(n)%20if%20n%20%3C%3D%201%20n%20else%20fib(n-1)%20%2B%20fib(n-2)%20%0Aprint%20fib(8)&t=code)


```
fib(n) = if n <= 1 n else fib(n-1) + fib(n-2) 
print fib(8)
```

You can also write the same program in more verbose ways.


```
fib(n) 
	if n <= 1 
		return n 
	fib(n-1) + fib(n-2)
print fib(8)
```

```
fib(n) 
	if (n <= 1) {
        return n
    }
	return fib(n-1) + fib(n-2)
print(fib(8))
```


(In swedish)
```
fib(n) 
	if (n <= 1) {
        returnera n
    }
	returnera fib(n-1) + fib(n-2)
skriv ut fib(8)
```