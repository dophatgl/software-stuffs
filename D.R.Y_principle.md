The DRY (Don’t Repeat Yourself) principle is aimed at reducing redundancy in code. The idea is that every piece of knowledge or logic should exist in only one place, avoiding duplicate code and promoting reusability. This helps make code more maintainable, as changes only need to be made in one place.

Examples of DRY

1. Using Functions to Eliminate Duplicate Logic

If you have a block of code that performs the same operation in multiple places, encapsulate it in a function and call the function instead.

Example without DRY:

```
# Calculating area for circles in multiple places without DRY
circle1_area = 3.14 * (radius1 ** 2)
circle2_area = 3.14 * (radius2 ** 2)
circle3_area = 3.14 * (radius3 ** 2)
```

With DRY:

```
def calculate_circle_area(radius):
    return 3.14 * (radius ** 2)

# Now calling the function wherever needed
circle1_area = calculate_circle_area(radius1)
circle2_area = calculate_circle_area(radius2)
circle3_area = calculate_circle_area(radius3)

```
2. Using Constants for Repeated Values

If you have values that are used repeatedly throughout your code, use constants instead of hardcoding values everywhere.

Example without DRY:

```
# Using the same tax rate in multiple places without DRY
total1 = price1 * 0.08
total2 = price2 * 0.08
total3 = price3 * 0.08
```
With DRY:

```
TAX_RATE = 0.08

total1 = price1 * TAX_RATE
total2 = price2 * TAX_RATE
total3 = price3 * TAX_RATE

```
3. Using Loops to Avoid Repetitive Code

If you find yourself writing similar code for each item in a collection, you can use a loop to handle them in a DRY way.

```
Example without DRY:

item1 = process_item(data[0])
item2 = process_item(data[1])
item3 = process_item(data[2])
```
With DRY:

```
# Using a loop to process each item in the collection
processed_items = [process_item(item) for item in data]

```
4. Inheritance in Object-Oriented Programming (OOP)

DRY can also be applied in OOP through inheritance and abstraction. If several classes share similar methods, you can move the shared code to a base class and have the subclasses inherit it.

Example without DRY:

```
class Dog:
    def sound(self):
        return "Bark"
    def sleep(self):
        return "Sleeping"

class Cat:
    def sound(self):
        return "Meow"
    def sleep(self):
        return "Sleeping"

```
With DRY:

```
class Animal:
    def sleep(self):
        return "Sleeping"

class Dog(Animal):
    def sound(self):
        return "Bark"

class Cat(Animal):
    def sound(self):
        return "Meow"

```
By following DRY, you can simplify your code, make it more readable, and reduce the risk of errors when updates are necessary.
