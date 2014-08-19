## Warm-up

Print the numbers between 1 and 100 in a vertical list.
```python
listOfNumbers = range(1, 101)

for n in listOfNumbers:
	print n
```

> The for loop prints each number in the range during each of the loop's 100 runs.

> Remember, the range has to end at 101.

A couple of wrong answers:
```python
numbers = range(1, 101)

print numbers
```
> If we merely print the list of numbers without the loop, the list is horizontal, incomplete & incorrect.

```python
numbers = range(1, 101)

for n in numbers:
	print numbers
```
> We don't need to print out the whole list ( range )! How will we print each list element individually?

Print all the multiples of three between 1 and 100.
```python
listOfNumbers = range(3, 101, 3)

for n in listOfNumbers:
	print n
```
> Why do we start the range at 3?

> If we start the range at 1, our list reads [ 1, 4, 7, 10, ... ]

> If we start the range at zero the list is almost correct, except that zero is included.


## Summing things

Create  an integer variable `total`. This container `total` is used to record summed variables. Remember, the = sign doesn't work like it does in math (doesn't indicate equality, it's an operation). Instead, the = sign figures out the value of its right side, and puts it into the variable on its left side.

```python
total = 0
```
> Visualize a situation in which you had to add up a bunch of numbers. What is the least amount of brain space required? 

> You only need to keep one number in your head!

> Thus we create another container container, or the total variable.

How can we find the sum of all numbers between 1 - 100? Ask the students to remeber that variables are containers. One can take things out of the container as well as put things back into the container. Essentially, the value of `total` can be changed using the = sign.

Walk through the loop's first step. During this run the value of `n` is 1 ( the first list element specified by the range ). At that point in time `total` starts at 0. `total` = `total` + 1 becomes `total` = 0 + 1, so `total` = 1.

Printing the sum of 1 - 100.
```python
total = 0
numbers = range(1, 101)

for n in numbers:
	total = total + n
print total
```
> Which number do we add to the total during each loop run? The current element of the list of numbers, or n.

> So total starts at 0. total = total + 1 is total = 0 + 1, so total now is 1.

> Next iteration, n = 2. So, 2 is added to total, making total 3.

Check it with the n (n + 1) / 2 formula, explain the formula.

How do we print all of the multiples of three? The easiest way is to utilize the third parameter of the range function. This parameter is the distance between adjacent numbers in the list `numbers`, so instead of [ 1, 2, 3, ... ] the list `numbers` becomes [ 1, 4, 7, ... ].

Printing the sum of all multiples of three between 1  - 100.
```python
total = 0
numbers = range(0, 101, 3)
for n in numbers:
	total = total + n
print total
```
> Why is the first parameter of the range zero?

> If we start the range at 1, our list will sum 1 + 4 + 7 + ... instead of 0 + 3 + 6 + ...

## Euler problem 1

This is [Euler problem number 1](https://projecteuler.net/problem=1): Find the sum of all the multiples of 3 or 5 below 1000.

> What is the sum of the multiples of 3 and 5 between 1 - 1000?

> What will we use to consider each list (range) element individually?

Suggest that the students to use lists and a `for` loop. Remind them that the `range` function's third parameter can be used to print the sum of a number's multiples. You can also hint to the students that they should create two separate totals, then add them together to obtain the final total.

Incorrect solution.
```python
threesTotal = 0
threesList = range(1, 1001, 3)

for x in threesList:
	threesTotal = threesTotal + x

fivesTotal = 0
fivesList = range(1, 1001, 5)

for y in fivesList:
	fivesTotal = fivesTotal + y

total = threesTotal + fivesTotal

print total
```
> If we start the range at 1, our threesList reads [ 1, 4, 7, 10, ... ]. None of these numbers are multiples of 3.

Incorrect solution.
```python
threesTotal = 0
threesList = range(0, 1001, 3)

for x in threesList:
	threesTotal = threesTotal + x

fivesTotal = 0
fivesList = range(0, 1001, 5)

for y in fivesList:
	fivesTotal = fivesTotal + y

total = threesTotal + fivesTotal

print total
```
> This solution adds the multiples of 3 to the multiples of 5.

> However it adds multiples of both 3 AND 5 twice, once per list.

The correct solution to this problem is 234168.

> If your solution is different, question "why?" and troubleshoot.

Troubleshooting. Ask the students to modify the range's end ( second ) parameter using variable substitution.
```python
end = 1001
threesList = range(0, end, 3)
```

If they cannot find the issue, lessen the ranges to span 1 - 20.
```python
end = 20
threesList = range(0, end, 3)
```

The new solution is 78.

> If your solution is still different, manually add the multiples of 3 and 5 between 1 - 20.

```
3 + 5 + 6 + 9 + 10 + 12 + 15 + 18 = 78
```

Explain the multiple of 15 overlap. The number 15 is counted once in the total of multiples of 3 and again in the total for multiples of 5.

> How will we account for the multiples of 15 being counted twice?

> Subtract the total for the multiples of 15 from our current total!

Correct solution. The final solution is 234168.
```python
threesTotal = 0
threesList = range(0, 1001, 3)

for x in threesList:
	threesTotal = threesTotal + x

fivesTotal = 0
fivesList = range(0, 1001, 5)

for y in fivesList:
	fivesTotal = fivesTotal + y

fifteensTotal = 0
fifteensList = range(0, 1001, 15)

for z in fifteensList:
	fifteensTotal = fifteensTotal + z

total = threesTotal + fivesTotal - fifteensTotal

print total
```


For students who understand the `if` statment, there is a much simpler solution to Euler problem 1.
```python
total = 0
for i in range(1, 1001):
	if i % 3 == 0 or i % 5 == 0:
		total += i
print total
```
> The or ensures that multiples of both 3 and 5 are only counted once.


## Advanced topics

Average of a list

```python
numbers = range(1, 100)
total = 0
.. sum them up

average = total / len(numbers)
```


Spies problem

```python
name = "keshav"

for letter in name:
	print letter
```

explain the ord function - talk about [ASCII](http://www.asciitable.com/)
```python
name = "keshav"

for letter in name:
	print ord(letter)
```

offset the ascii characters
```python
name = "abcdefg"

for letter in name:
	print ord(letter) - 96
```

Use a total to sum it up
```python
name = "keshav"
total = 0
for letter in name:
	total = total + ord(letter) - 96

print total
```
