### Assignment: Counting Vowels

Write a function that returns the amount of vowels in a given word.

```python
count_vowels('hello')
>>> 2
```

### Basic
```python
def is_vowel(letter):
	"""
	return True if the given letter is in the `vowels` list, otherwise False
	"""
	vowels = ['a','e','i','o','u','y']
	return letter in vowels

def count_vowels(word):
	"""
		for every letter in the given word, increment a counter if the letter is a vowel
	"""
	count = 0
	for letter in word:
		if is_vowel(letter):
			count += 1
	return count
```
### Advanced
```python
def count_vowels(word):
	"""
		get a list which consists of only the vowels in a word, and take the length of it	
	"""
	return len(filter(lambda letter: letter in ['a','e','i','o','u','y'],word))
```

