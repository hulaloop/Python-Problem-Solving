## Counting years

How many years have passed since 1900? Remind the students of the concept of a list, or range. Initialize `years`, a range beginning at 1900 and ending at 2015 (n+1th year). Next initialize `count`, a variable that will keep track of the number of years that have passed since 1900. Create a for loop that will cycle through the range one constituent year at a time. `count` will increase by one for each iteration of the loop, which loops exactly 115 times (one time for each year that passes from 1900 forwards). We then print `count` outside the loop to obtain this final solution of 115.
```python
years = range(1900, 2015)

count = 0 # count refers to the number of years passed since 1900

for y in years:
	count = count + 1
	
print count
```
> We create a list of years with one element for each year in our range. Why does our range end in 2015?

> The range actually goes from 1900 - 2014.

> We create the count variable to keep track of the number of years passed since 1900.

> We're going to increase `count` by one each year. So, we place `count` indented in the loop.

> Why do we print count outside of the loop? We only want one answer that equals the total years (115)!


## Counting months

Next, ask the students to calculate how many months have passed since 1900. Create `months`, another range beginning at 1 and ending at 13. Emphasize that this range has 12 constituents, one for each of the months of the year. 

We set up a nested for loop so that we may iterate through all twelve months for each run of `years`. Ensure that `count` is indented under the inner loop `months` so that it increments by one for each of the 1380 months that have passed since 1900.
```python
years = range(1900, 2015)
months = range(1, 13)

count = 0 # count refers to the number of months passed since 1900

for y in years:
	for m in months:
		count = count + 1
		
print count
```
> We used  a for loop to count years. How will we count months?

> Use another for loop with a range. The months range(1, 13) has an element for each year's twelve months.

> For each run (or year) in the outer loop `years`, we run through 12 months (runs) in the inner loop.

> Make sure to indent `count` so that it is under the inner loop, increasing monthly instead of yearly!


## Counting days (1 month ~ 31 days)

Introduce the concept of counting the number of days passed since 1900 [ assuming every month has 31 days (12 * 31 ~ 365 ) ]. Ensure that the students recognize the necessity of a third range `days` and an accompanying nested loop inside `months`. 

Note that `days` is initialized within the loop for `months` because the parameters for `days` will change later depending on the month. Also Note that `days` must be initialized at the same or lesser indentation than any later instance of `days`. This method yields that 42780 days have passed since 1900.
```python
years = range(1900, 2015)
months = range(1, 13)

count = 0 # count refers to the number of days passed since 1900

for y in years:
	for m in months:
		days = range(1, 32)
		for d in days:
			count = count + 1

print count
```
> Most months have 31 days. Let's assume there are 31 days in every month. What is our range?

> We create the days list inside the loop. Later, we will change the range based on the month.


## Counting days (without leap years)

Note the mistaken assumption that each month is 31 days long. Most months do have 31 days, except February, April, June, September and November. The latter four months are 30 days long. Ask the students to assume that February has 28 days for now.

First, ask the students to create an 'if' statement for February. If `months` is on its second iteration ( m = 2 ), `days` should range( 1, 29 ) instead of the default. Next, create another 'if' to set range( 1, 31 ) when the `m` is 4, 6, 9 or 11. When printed, `count` equals 41975 days.
```python
years = range(1900, 2015)
months = range(1, 13)

count = 0 # count refers to the number of days passed since 1900

for y in years:
	for m in months:
		days = range(1, 32)
		if m == 2:
			days = range(1, 29)
		if m == 4 or m == 6 or m == 9 or m == 11:
			days = range(1, 31)
		for d in days:
			count = count + 1

print count
```
> Let's assume February always has 28 days. How will we check if the month is February?

> How will we count 28 days for February? Change the second parameter of the range to 29.

> What if we added else: days = range(1, 32) instead of using days = range(1, 32) as default (under the months loop)?

> The program wouldn't compile. The days loop is created at a bigger indentation than its use in the for d in days loop.


## Counting days (with leap years)

How many days pass between 1900 and 2014, factoring in for leap years? Our final problem requires us to use the modulus, or remainder. A `%`, or modulus divides its left input by the right input and outputs the remainder. Give the students five or six practice problems using the modulus function ( ex: 20 % 3 = 2 ).

Within the 'if' for February, we set up another 'if' using the modulus to check if the current year `y` in `years` is divisible by 4 (leap year). The days range is changed to range( 1, 30 ) if the year is a leap year.

Counting with leap years.
```python
years = range(1900, 2015)
months = range(1, 13)

count = 0

for y in years:
	for m in months:
		days = range(1, 32)
		if m == 2:
			days = range(1, 29)
			if y % 4 == 0:
				days = range(1, 30)
		if m == 4 or m == 6 or m == 9 or m == 11:
			days = range(1, 31)
		
		for d in days:
			count = count + 1

print count
```
> How are a single equals sign and a double equals sign different?

> We use the double equals sign to check if the left side is equal to the right side.

> We check for leap years within the if statement for February. How will we check if its a leap year?

> If it is a leap year, what is the days range changed to?

Every 100 years, the leap year does not count. Ask the students to factor this phenomenon into their program.

Counting with leap years (with centuries).
```python
years = range(1900, 2015)
months = range(1, 13)

count = 0

for y in years:
	for m in months:
		days = range(1, 32)
		if m == 2:
			days = range(1, 29)
			if y % 100 == 0:
				days = range(1, 29)
			elif y % 4 == 0:
				days = range(1, 30)
		if m == 4 or m == 6 or m == 9 or m == 11:
			days = range(1, 31)
		
		for d in days:
			count = count + 1

print count
```
> If the century condition is true, we want to ignore the leap year change.

> We use the else if (elif) so that the leap year will count if the century condition is false.

> When the century condition is true, the leap year elif is ignored.

Every 400 years, the leap year counts again. Ask the students to factor this phenomenon into their program.

Counting leap years (with every four centuries).
```python
years = range(1900, 2015)
months = range(1, 13)

count = 0

for y in years:
	for m in months:
		days = range(1, 32)
		if m == 2:
			days = range(1, 29)
			if y % 400 == 0:
				days = range(1, 30)
			elif y % 100 == 0:
				days = range(1, 29)
			elif y % 4 == 0:
				days = range(1, 30)
		if m == 4 or m == 6 or m == 9 or m == 11:
			days = range(1, 31)
		
		for d in days:
			count = count + 1

print count
```
> Use the same idea we used to factor in the centuries.

> Make sure you ignore the century condition if the fourth century condition is true.
