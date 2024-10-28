The SOLID principles are five design principles that help in building software that is scalable, maintainable, and flexible. Here are examples for each principle:

1. Single Responsibility Principle (SRP)

Each class should have only one reason to change, meaning it should have only one job.

Example:
Imagine a User class that handles user data. According to SRP, it should not be responsible for saving itself to a database. Instead, you’d have:

	•	A User class that contains user-related attributes and methods.
	•	A UserRepository class that handles database operations for user data.

```
class User:
    def __init__(self, name, email):
        self.name = name
        self.email = email

class UserRepository:
    def save(self, user: User):
        # Logic to save the user to the database
        pass
```

2. Open/Closed Principle (OCP)

Classes should be open for extension but closed for modification.

Example:
Suppose you have a Discount class that calculates discounts. Instead of modifying the class each time a new discount type is added, you could create a base Discount class and extend it with subclasses.

```
class Discount:
    def apply_discount(self, price):
        return price

class SeasonalDiscount(Discount):
    def apply_discount(self, price):
        return price * 0.9  # 10% off

class LoyaltyDiscount(Discount):
    def apply_discount(self, price):
        return price * 0.8  # 20% off
```

3. Liskov Substitution Principle (LSP)

Subtypes should be substitutable for their base types without altering the correctness of the program.

Example:
Imagine a Bird class with a method fly(). If you create a Penguin subclass, it shouldn’t inherit fly() because penguins can’t fly. Instead, you could create a base Bird class and have a FlyingBird subclass with a fly() method.

```
class Bird:
    def lay_eggs(self):
        pass

class FlyingBird(Bird):
    def fly(self):
        pass

class Penguin(Bird):
    def swim(self):
        pass
```

4. Interface Segregation Principle (ISP)

Clients should not be forced to depend on interfaces they do not use.

Example:
Imagine a Printer interface with methods like print(), fax(), and scan(). A simple printer might not need the fax() and scan() methods. Instead, break it into smaller interfaces.

```
class Printer:
    def print(self, document):
        pass

class Scanner:
    def scan(self, document):
        pass

class MultiFunctionPrinter(Printer, Scanner):
    def print(self, document):
        # print logic
        pass

    def scan(self, document):
        # scan logic
        pass
```

5. Dependency Inversion Principle (DIP)

High-level modules should not depend on low-level modules but on abstractions. Also, abstractions should not depend on details; details should depend on abstractions.

Example:
Instead of a UserService class depending directly on a MySQLDatabase class, it should depend on an IDatabase interface. This way, the UserService can work with any database implementing IDatabase.

```
class IDatabase:
    def save(self, data):
        pass

class MySQLDatabase(IDatabase):
    def save(self, data):
        # MySQL save logic
        pass

class UserService:
    def __init__(self, database: IDatabase):
        self.database = database

    def save_user(self, user):
        self.database.save(user)
```

By applying these principles, you can create code that is easier to maintain, extend, and adapt.
