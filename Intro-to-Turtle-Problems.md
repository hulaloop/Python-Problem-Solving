### 1. Draw a square, then inscribe a circle.

Students will need to apply
  * **variable substitution** to ensure the square size matches the circle size
  * **a loop** to draw a circle
  * **visualization** in planning a more complex turtle route

![Circle inscribed in a square](http://pythonroom.com/img/turtle/exercise1.png)

Notice in the solution how the square is drawn such that the turtle is not starting in the corner, but rather in the middle of one of the square's edges. This allows the circle to be drawn immediately after the square is drawn.
```
import turtle
t = turtle.Turtle()

# Draw the square with variable side length.
side = 115
t.forward(side / 2)
t.left(90)
t.forward(side)
t.left(90)
t.forward(side)
t.left(90)
t.forward(side)
t.left(90)
t.forward(side / 2)

# Draw the circle inside the square.
numbers = range(0, 360)
for number in numbers:
	t.forward(1)
	t.left(1)
```

### 2. Circumscribe a circle.

This exercise is very similar to the one above, except this time the turtle must start from the corner and draw a slightly wider circle. It must also start drawing the circle at a bit of an angle - this is difficult to calculate, but can be assumed to be 45 degrees due to symmetry.

![Square inscribed in a circle](http://pythonroom.com/img/turtle/exercise2.png)

```python
import turtle
t = turtle.Turtle()

length = 80
sides = range(0, 4)
for s in sides:
	t.forward(length)
	t.left(90)

t.right(45)
numbers = range(0, 360)
for number in numbers:
	t.forward(1)
	t.left(1)
```

## 3. Draw a square spiral.

![Square spiral](http://pythonroom.com/img/turtle/exercise3.png)

You could present this as "how could you keep drawing a line where each side is longer than the one you just drew?"

```python
import turtle
t = turtle.Turtle()

numbers = range(1, 100)
for n in numbers:
	t.forward(n * 2)	# Notice how n is scaled up by a factor of 2
	# t.forward(n)		# This will fill in a solid square using the spiral pattern
	t.left(90)
```

## 4. Draw a circular spiral.

![Circular spiral](http://pythonroom.com/img/turtle/exercise4.png)

For this particular implementation of this drawing exercise, notice how the turning amount remains fixed. The amount the turtle goes forward is the number being looked at divided by 20, so the turning radius increases very gradually. Some students may implement the circular spiral by keeping the `forward` amount fixed, and using `n` to modify the input to the `left` command. There are several acceptable ways for this challenge to be solved. 

```python
import turtle
t = turtle.Turtle()

numbers = range(20, 300)

for n in numbers:
	t.forward(n / 20)
	t.left(5)
```

## 5. Alternate colors while drawing a spiral

[TODO]
