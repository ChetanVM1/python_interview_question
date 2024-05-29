# Medium Level Theoretical Questions

## 1. What are decorators in Python?
Decorators in Python are a way to modify the behavior of a function without changing its source code. They are defined using the `@` symbol followed by the decorator function name.

## 2. Explain the difference between '==' and 'is' in Python.
The `==` operator compares the values of two objects, while the `is` operator compares the identity (memory location) of two objects. Two objects with the same value may not necessarily be the same object in memory.

## 3. What is the difference between a shallow copy and a deep copy?
A shallow copy creates a new object that contains references to the same elements as the original object. A deep copy creates a new object with copies of the elements from the original object.

## 4. What is a lambda function in Python?
A lambda function in Python is an anonymous function that can take any number of arguments but can only have one expression. It is defined using the `lambda` keyword followed by the arguments and a colon `:`.

## 5. Describe the use of the 'yield' keyword in Python.
The `yield` keyword in Python is used in generator functions to return a generator iterator. It allows the function to generate values one at a time, rather than creating and returning a list of all the values at once.

## 6. What is the purpose of the 'with' statement in Python?
The `with` statement in Python is used to provide a convenient syntax for working with objects that need setup and teardown, such as file handling or locking. It ensures that the object is properly initialized and cleaned up, even if an exception occurs.

## 7. Explain the concept of list comprehension in Python.
List comprehension in Python provides a concise way to create lists. It allows you to generate a new list based on an existing iterable (such as a list, tuple, or string) using a single line of code. List comprehension can include conditional statements and loops.

## 8. What is the difference between 'sorted' and 'sort' methods in Python?
The `sorted` function in Python returns a new sorted list from an iterable, while the `sort` method sorts the elements of a list in-place. The `sorted` function can be used with any iterable, while `sort` is only applicable to lists.

## 9. How do you create a set in Python?
Sets in Python are created using curly braces `{}` or the `set()` function. Sets are unordered collections of unique elements. Duplicate elements are automatically removed when a set is created.

## 10. What is the purpose of the 'map' function in Python?
The `map` function in Python applies a given function to each item of an iterable (such as a list, tuple, or string) and returns a map object. It is commonly used to perform an operation on each element of an iterable.

## 11. Explain the concept of generators in Python.
Generators in Python are a special type of function that return an iterator. They use the `yield` keyword instead of `return` to return values one at a time, allowing for the efficient generation of sequences without creating and storing the entire sequence in memory at once.

## 12. What is the difference between 'join' and 'split' methods in Python strings?
The `join` method in Python concatenates the elements of an iterable (such as a list, tuple, or set) into a single string, using the string on which the method is called as the separator. The `split` method splits a string into a list of substrings, using a specified separator (whitespace by default).

## 13. How do you create a class in Python?
In Python, a class is defined using the `class` keyword followed by the class name. The class body contains the attributes (variables) and methods (functions) that define the behavior of the class. Classes can also inherit from other classes using the `()` syntax after the class name.

## 14. What is the purpose of the `__init__ `method in Python classes?

The `__init__` method in Python serves as the **constructor** for a class. When you create an object of a class, the `__init__` method is automatically called, allowing you to initialize the object's state. Here are some key points about the `__init__` method:

1. **Initialization**: The primary purpose of `__init__` is to initialize the object's attributes (also known as data members or instance variables). You can assign values to these attributes within the method.

2. **Constructor Analogy**: Think of `__init__` as similar to a constructor in languages like C++ or Java. It runs as soon as an object of the class is instantiated.

3. **Self Parameter**: The first parameter of `__init__` is always `self`, which represents the instance of the class. It allows you to access and modify the object's attributes within the method.

4. **Example**:
    ```python
    class Person:
        def __init__(self, name):
            self.name = name

        def say_hi(self):
            print('Hello, my name is', self.name)

    p = Person('Nikhil')
    p.say_hi()  # Output: Hello, my name is Nikhil
    ```




## 15. Explain the concept of inheritance in Python.
Inheritance in Python allows a class to inherit attributes and methods from another class. The class that inherits is called the derived class or child class, and the class being inherited from is called the base class or parent class. Inheritance promotes code reuse and hierarchical organization of classes.

## 16. What is the difference between 'super' and 'self' in Python classes?
In Python classes, `self` is a convention used as the first argument in instance methods, referring to the current instance of the class. `super` is a function used to call methods of the base class from the derived class, allowing for method overriding and extension.

## 17. How do you create a module in Python?
In Python, a module is a file containing Python definitions and statements. To create a module, you simply need to write Python code in a file with a `.py` extension. Modules can be imported into other Python scripts using the `import` statement, allowing for code reuse and organization.

## 18. What is the purpose of the 'try-except' block in Python?
The `try-except` block in Python is used for exception handling. The `try` block contains the code that might raise an exception, while the `except` block specifies the type of exception to catch and the corresponding error handling logic. This allows for graceful error handling and prevents the program from crashing.

## 19. Explain the concept of duck typing in Python.
Duck typing in Python is a style of dynamic typing in which an object's methods and properties determine the valid semantics, rather than its inheritance from a particular class. If an object walks like a duck and quacks like a duck, it is considered a duck, regardless of its actual type.

## 20. What is the difference between 'append' and 'insert' methods in Python lists?
The `append` method in Python lists adds an element to the end of the list, while the `insert` method inserts an element at a specified index. `append` modifies the list in-place, while `insert` shifts the existing elements to make room for the new element.

