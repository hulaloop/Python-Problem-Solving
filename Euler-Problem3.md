# Euler Problem 3

What is the largest prime factor of the number 13195?

```python
import math

def isPrime(n):
    if n == 1:
        return False
    i = 2
    while True:
        if n % i == 0:
            return False
        i += 1
        if i*i >= n:
            break
    return True

answer = 0

for i in range(2, 13195):
	if 13195 % i == 0:
		if isPrime(i):
			answer = i

print answer
```
