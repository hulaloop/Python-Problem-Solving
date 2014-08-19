# Warmup Exercises

### Print each number between 1 to 100.

The correct solution looks something like this:
```python
numbers = range(1, 101)
for number in numbers:
	print number
```

A more concise solution would be:
```python
for number in range(1, 101): print number
```

Some incorrect solutions:
```python
# Incorrect range, doesn't include 100
numbers = range(1, 100)

# Only prints out the underlying list.
print range(1, 101)

# Same problem as above
numbers = range(1, 101)
print numbers

# Prints out the entire list for each number 
for number in numbers:
	print numbers	# should be "print number"
```

### Print all the multiples of 3 between 1 and 100.

Students need to use the modulus operator (```%```), which is most simply expressed as *the remainder after dividing*. They may need a refresher on the modulus, i.e. that ```a % b``` is *the remainder after dividing ```a``` by ```b```*. Some examples:

```
6 % 3     ==>     0 (no remainder)
5 % 2     ==>     1
14 % 3    ==>     2
26 % 11   ==>     4
103 % 21  ==>     20
103 % 103  ==>    0
```

The observation that students need to make is that a number divided by a factor of that number (e.g. 6 divided by 3) always yields a remainder of 0. Therefore, checking to see if the remainder after dividing 

The correct solution builds on the previous one, that is
```python
numbers = range(1, 101)
for number in numbers:
	if number % 3 == 0
```
