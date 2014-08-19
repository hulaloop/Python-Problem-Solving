# Easy

Ask the students to write a program that takes in one's `mark` ( percentage points ) received on an exam. The program should then print the mark along with the corresponding grade ( A, B, C, ... ).
```python
mark = int(input("What mark did you receive on the exam?")
		   
if mark >= 90:
	return "A"
else:
	if mark >= 80:
		return "B"
	else:
		if mark >= 70:
			return "C"
		else:
			if mark >= 60:
				return "D"
			else:
				return "F"

print("Mark:", str(mark), "Grade:", grade(mark))
```

> In order to check our inputted mark, we first convert it into an integer type.

# Medium

Write a program that gives financial advice based on how much money the user has.
```python
money = int(input("How much spending money do you have?"))

if money == 100:
	print("You can buy a pair of headphones.")
elif money < 50:
	print("You can buy a movie ticket.")
elif money < 10:
	print("You can buy a burger.")
```

> We use an else if because we want to bypass all other if conditions once one of the if conditions is true.
