What is the result of each of the following:

```
1. ‘Python’[1]
2. “Strings are sequences of characters.”[5]
3. len(“wonderful”)
4. ‘Mystery’[:4]
5. ‘p’ in ‘Pineapple’
6. ‘apple’ in ‘Pineapple’
7. ‘pear’ not in ‘Pineapple’
8. ‘apple’ > ‘pineapple’
9. ‘pineapple’ < ‘Peach’
```

Answers:

```
1. ‘Python’[1] = ‘y’
2. ‘Strings are sequences of characters.’[5] = ‘g’
3. len(‘wonderful’) = 9
4. ‘Mystery’[:4] = ‘Myst’
5. ‘p’ in ‘Pineapple’ = True
6. ‘apple’ in ‘Pineapple’ = True
7. ‘pear’ not in ‘Pineapple’ = True
8. ‘apple’ > ‘pineapple’ = False
9. ‘pineapple’ < ‘Peach’ = False
```

Create a program that can tell you the number of digits in an inputted integer.

> Remember that input boxes output String type variables!

```python
number = input("What is your integer?")
print "Your integer has " + str(len(number)) + " digits."
```

rip from [InteractivePython](http://interactivepython.org/runestone/static/thinkcspy/Strings/strings.html#exercises)

Write a program that prints out all of the vowels in an inputted word.

> The nested loop lets us view the String as a list of characters, then check if each character is a vowel.

```python
word = input("Speak, human.")
word = word.lower()
vowels = [ "a", "e", "i", "o", "u" ]
size = len(word)

for i in range(1, size):
	for v in vowels:
		if word[i] == v:
			print v

print word
```
