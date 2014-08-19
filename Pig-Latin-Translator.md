# Pig latin translator

Review the rules of pig latin found at [WikiHow](http://www.wikihow.com/Speak-Pig-Latin). Ask the students to create a translator that takes a user-inputted word and converts it to pig latin.

> Initialize an output variable which we can place the translated word into.

> Create a list of the vowels to reference later.

> We standardize our input using the lower case function.

```python
word = input("Speak, human.")
word = word.lower()
vowels = [ "a", "e", "i", "o", "u" ]
output = ""
```

If the word begins with a vowel, we merely add a suffix. If the word begins with a consonant, we move the consonant to the end of the word and add a suffix ( note that this does not account for consonant clusters ).

> The first thing we check is whether the word begins with a vowel or a consonant.

> We use splicing to remove the consonant from the beginning of the string and place it onto the end.

> We also use splicing to add suffixes to both.

```python
if word[0] == "a" or word[0] == "e" or word[0] == "i" or word[0] == "o" or word[0] == "u":
	output += word + "yay"
else:
	output += word[1:] + word[:1] + "ay"

print output
```

Now, account for consonant clusters ( ex: glove becomes oveglay, not lovegay ). We substitute our splicing indicies for a variable to allow for manipulation.

> Convert the word into a character list so we can loop through and check each letter individually.

> If the next letter being considered is a vowel, we exit the loop ( have becomes avehay ). 

> If the next letter is a consonant, we increment our index variable and check the next letter until a vowel is found.

```python
else:
	start = 0
	for letter in list(word):
		if letter in vowels:
			break
		else:
			start += 1
	output += word[start:] + word[:start] + "ay "

print output
```

Account for the fact that when the letter 'Y' occurs at the end of a consonant cluster, it is treated like a vowel ( remains unspliced at the beginning of the word ). For example, "rhythm" becomes "ythmrhay".

```python
else:
	start = 0
	for letter in list(word):
		if letter in vowels:
			break
		else:
			if letter is "y":
				break
			else:
				start += 1
	output += word[start:] + word[:start] + "ay "
```

Modify the code so it converts multiple words.

> Use the split function to split the input into independent words at each space.

> Create another for loop so that our previous code is performed once for each word.

```python
words = input("Speak, human.")
words = words.lower()
words = words.split(" ")
vowels = [ "a", "e", "i", "o", "u" ]
output = ""

for word in words:
    if word[0] in vowels:
        output += word + "yay "
    else:
		start = 0
		for letter in list(word):
			if letter in vowels:
				break
			else:
				if letter is "y":
					break
				else:
					start += 1
		output += word[start:] + word[:start] + "ay "

print output
```
