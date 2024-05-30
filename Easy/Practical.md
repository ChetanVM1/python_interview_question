### Practical Python Question

1. Write a Python program to swap two variables.
   - ```python
     a = 10
     b = 20
     a, b = b, a
     print("Swapped values: a =", a, "b =", b)
     ```

2. Create a function that returns the factorial of a number.
   - ```python
     def factorial(n):
         if n == 0:
             return 1
         else:
             return n * factorial(n-1)
     
     num = 5
     print("Factorial of", num, "is", factorial(num))
     ```

3. Write a program to check if a number is prime.
   - ```python
     def is_prime(num):
         if num < 2:
             return False
         for i in range(2, int(num**0.5) + 1):
             if num % i == 0:
                 return False
         return True
     
     number = 17
     if is_prime(number):
         print(number, "is a prime number")
     else:
         print(number, "is not a prime number")
     ```

4. Implement a function to reverse a string.
   - ```python
     def reverse_string(s):
         return s[::-1]
     
     text = "hello"
     print("Reversed string:", reverse_string(text))
     ```

5. Write a Python program to find the largest element in a list.
   - ```python
     def find_largest(lst):
         return max(lst)
     
     numbers = [10, 5, 8, 12, 7]
     largest = find_largest(numbers)
     print("Largest element:", largest)
     

6. Create a function to check if a number is even or odd.
   - ```python
     def is_even(num):
         return num % 2 == 0
     
     number = 7
     if is_even(number):
         print(number, "is even")
     else:
         print(number, "is odd")
     ```

7. Write a program to find the sum of all elements in a list.
   - ```python
     def sum_of_elements(lst):
         return sum(lst)
     
     numbers = [2, 4, 6, 8, 10]
     total = sum_of_elements(numbers)
     print("Sum of elements:", total)
     

8. Implement a function to check if a string is a palindrome.
   - ```python
     def is_palindrome(s):
         return s == s[::-1]
     
     word = "racecar"
     if is_palindrome(word):
         print(word, "is a palindrome")
     else:
         print(word, "is not a palindrome")
     ```

9. Write a Python program to find the average of a list of numbers.
   - ```python
     def calculate_average(lst):
         return sum(lst) / len(lst)
     
     numbers = [5, 10, 15, 20, 25]
     average = calculate_average(numbers)
     print("Average:", average)
    
     

10. Create a function to convert Celsius to Fahrenheit.
    - ```python
      def celsius_to_fahrenheit(celsius):
          return (celsius * 9/5) + 32
      
      temperature = 25
      fahrenheit = celsius_to_fahrenheit(temperature)
      print(temperature, "°C is equal to", fahrenheit, "°F")
      

11. Write a program to find the second largest element in a list.
    - ```python
      def find_second_largest(lst):
          unique_elements = set(lst)
          unique_elements.remove(max(unique_elements))
          return max(unique_elements)
      
      numbers = [10, 5, 8, 12, 12, 7]
      second_largest = find_second_largest(numbers)
      print("Second largest element:", second_largest)
      

12. Implement a function to count the number of vowels in a string.
    - ```python
      def count_vowels(s):
          vowels = 'aeiou'
          count = 0
          for char in s.lower():
              if char in vowels:
                  count += 1
          return count
      
      text = "Hello, World!"
      num_vowels = count_vowels(text)
      print("Number of vowels:", num_vowels)
      ```

13. Write a Python program to find the product of all elements in a list.
    - ```python
      def product_of_elements(lst):
          result = 1
          for num in lst:
              result *= num
          return result
      
      numbers = [2, 3, 4, 5]
      product = product_of_elements(numbers)
      print("Product of elements:", product)
      

14. Create a function to check if a number is a perfect square.
    - ```python
      import math

      def is_perfect_square(num):
          sqrt = math.sqrt(num)
          return sqrt.is_integer()
      
      number = 16
      if is_perfect_square(number):
          print(number, "is a perfect square")
      else:
          print(number, "is not a perfect square")
      ```

15. Write a program to find the common elements between two lists.
    - ```python
      def find_common_elements(list1, list2):
          return list(set(list1) & set(list2))
      
      numbers1 = [1, 2, 3, 4, 5]
      numbers2 = [4, 5, 6, 7, 8]
      common = find_common_elements(numbers1, numbers2)
      print("Common elements:", common)
      

16. Implement a function to remove duplicates from a list.
    - ```python
      def remove_duplicates(lst):
          return list(set(lst))
      
      numbers = [1, 2, 3, 2, 4, 5, 1]
      unique_numbers = remove_duplicates(numbers)
      print("List without duplicates:", unique_numbers)
      ```

17. Write a Python program to find the maximum and minimum elements in a list.
    - ```python
      def find_max_min(lst):
          return max(lst), min(lst)
      
      numbers = [10, 5, 8, 12, 7]
      max_value, min_value = find_max_min(numbers)
      print("Maximum element:", max_value)
      print("Minimum element:", min_value)
      

18. Create a function to check if a string is a valid email address.
    - ```python
      import re

      def is_valid_email(email):
          pattern = r'^[\w\.-]+@[\w\.-]+\.\w+$'
          return bool(re.match(pattern, email))
      
      email_address = "example@example.com"
      if is_valid_email(email_address):
          print("Valid email address")
      else:
          print("Invalid email address")
      ```

19. Write a program to find the sum of digits in a number.

   ```python
   def sum_of_digits(num):
       return sum(int(digit) for digit in str(num))
   
   number = 12345
   total = sum_of_digits(number)
   print("Sum of digits:", total)
   ```



20. Implement a function to generate the first n Fibonacci numbers.
- ```python
  def fibonacci(n):
      if n <= 0:
          return []
      elif n == 1:
          return [0]
      elif n == 2:
          return [0, 1]
      else:
          fib = [0, 1]
          for i in range(2, n):
              fib.append(fib[-1] + fib[-2])
          return fib
  
  num_terms = 10
  fib_sequence = fibonacci(num_terms)
  print("First", num_terms, "Fibonacci numbers:", fib_sequence)
  ```
