# Easy

Count how many odd numbers there are between 1 - 963. The answer is 481.
```python
odd = 0
for i in range(963):
	if not i % 2 == 0:
		odd = odd + 1
print odd
```

Print the average of all numbers from 1 - 53241. The average is 26620.
```python
total = 0
count = 0

for i in range(53241):
	total += i
	count += 1
	
print total/count
```

# Medium

## Euler Problem 2

Ask the students to print all of the Fibonacci numers under one million in a vertical list.

> This problem can alternatively be solved using a for loop!

```python
x = 0
y = 1
py = 0

while y < 1000000:
	print y
	py = y
	y = x + y
	x = py
```

Ask the students to print the sum of all even Fibonacci numbers under one million in a vertical list.

> How will we check if each number is even? The modulus operator!

> We create another variable total to keep track of the sum. 

> Notice that the total is printed only once at the program's end.

```python
x = 0
y = 1
py = 0
total = 0

while y < 1000000:
	if y % 2 == 0:
		total += y
	py = y
	y = x + y
	x = py
	
print total
```
The total should read: 1089154.
