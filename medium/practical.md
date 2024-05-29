### Medium Level Programing Question 

1. Implement a function to check if a string is a palindrome.
   - ```python
     def is_palindrome(s):
         return s == s[::-1]
     
     word = "racecar"
     if is_palindrome(word):
         print(word, "is a palindrome")
     else:
         print(word, "is not a palindrome")
     

2. Write a program to find the Fibonacci series up to n terms.
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
     print("Fibonacci series up to", num_terms, "terms:", fib_sequence)
     

3. Create a Python class for a simple calculator.
   - ```python
     class Calculator:
         def add(self, a, b):
             return a + b
         
         def subtract(self, a, b):
             return a - b
         
         def multiply(self, a, b):
             return a * b
         
         def divide(self, a, b):
             if b == 0:
                 return "Error: Division by zero"
             return a / b
     
     calc = Calculator()
     print("5 + 3 =", calc.add(5, 3))
     print("10 - 4 =", calc.subtract(10, 4))
     print("2 * 6 =", calc.multiply(2, 6))
     print("15 / 3 =", calc.divide(15, 3))
     

4. Write a program to sort a list of elements using the bubble sort algorithm.
   - ```python
     def bubble_sort(lst):
         n = len(lst)
         for i in range(n):
             for j in range(0, n-i-1):
                 if lst[j] > lst[j+1]:
                     lst[j], lst[j+1] = lst[j+1], lst[j]
         return lst
     
     numbers = [5, 2, 8, 1, 9]
     sorted_numbers = bubble_sort(numbers)
     print("Sorted list:", sorted_numbers)
     

5. Implement a function to find the intersection of two lists.
   - ```python
     def find_intersection(list1, list2):
         return list(set(list1) & set(list2))
     
     numbers1 = [1, 2, 3, 4, 5]
     numbers2 = [4, 5, 6, 7, 8]
     intersection = find_intersection(numbers1, numbers2)
     print("Intersection:", intersection)
     

6. Write a Python program to find the maximum element in a list using recursion.
   - ```python
     def find_max(lst):
         if len(lst) == 1:
             return lst[0]
         else:
             return max(lst[0], find_max(lst[1:]))
     
     numbers = [10, 5, 8, 12, 7]
     max_element = find_max(numbers)
     print("Maximum element:", max_element)
     

7. Create a function to reverse a list in-place.
   - ```python
     def reverse_list(lst):
         left = 0
         right = len(lst) - 1
         
         while left < right:
             lst[left], lst[right] = lst[right], lst[left]
             left += 1
             right -= 1
         
         return lst
     
     my_list = [1, 2, 3, 4, 5]
     reversed_list = reverse_list(my_list)
     print("Reversed list:", reversed_list)
     

8. Write a program to implement a queue using a list.
   - ```python
     class Queue:
         def __init__(self):
             self.queue = []
         
         def enqueue(self, item):
             self.queue.append(item)
         
         def dequeue(self):
             if not self.is_empty():
                 return self.queue.pop(0)
             else:
                 return "Queue is empty"
         
         def is_empty(self):
             return len(self.queue) == 0
         
         def __len__(self):
             return len(self.queue)
     
     queue = Queue()
     queue.enqueue(10)
     queue.enqueue(20)
     queue.enqueue(30)
     print("Dequeued element:", queue.dequeue())
     print("Queue size:", len(queue))
     

9. Implement a function to find the second smallest element in a list.
   - ```python
     def find_second_smallest(lst):
         if len(lst) < 2:
             return None
         
         smallest = min(lst[0], lst[1])
         second_smallest = max(lst[0], lst[1])
         
         for i in range(2, len(lst)):
             if lst[i] < smallest:
                 second_smallest = smallest
                 smallest = lst[i]
             elif lst[i] < second_smallest:
                 second_smallest = lst[i]
         
         return second_smallest
     
     numbers = [5, 2, 8, 1, 9]
     second_smallest = find_second_smallest(numbers)
     print("Second smallest element:", second_smallest)
     

10. Write a Python program to find the sum of all even numbers in a list.
    - ```python
      def sum_of_even(lst):
          return sum(num for num in lst if num % 2 == 0)
      
      numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
      even_sum = sum_of_even(numbers)
      print("Sum of even numbers:", even_sum)
      

11. Create a function to find the length of the longest word in a string.
    - ```python
      def longest_word_length(text):
          words = text.split()
          lengths = [len(word) for word in words]
          return max(lengths)
      
      sentence = "The quick brown fox jumps over the lazy dog."
      max_length = longest_word_length(sentence)
      print("Length of the longest word:", max_length)
      

12. Write a program to implement a binary search algorithm.
    - ```python
      def binary_search(lst, target):
          left = 0
          right = len(lst) - 1
          
          while left <= right:
              mid = (left + right) // 2
              if lst[mid] == target:
                  return mid
              elif lst[mid] < target:
                  left = mid + 1
              else:
                  right = mid - 1
          
          return -1
      
      numbers = [1, 3, 5, 7, 9]
      print("Index of 5:", binary_search(numbers, 5))
      print("Index of 2:", binary_search(numbers, 2))
      

13. Implement a function to find the number of occurrences of a character in a string.
    - ```python
      def count_char(s, char):
          return s.count(char)
      
      text = "Hello, World!"
      count = count_char(text, "l")
      print("Number of occurrences of 'l':", count)
      

14. Write a Python program to find the sum of all prime numbers in a list.
    - ```python
      def is_prime(num):
          if num < 2:
              return False
          for i in range(2, int(num**0.5) + 1):
              if num % i == 0:
                  return False
          return True
      
      def sum_of_primes(lst):
          return sum(num for num in lst if is_prime(num))
      
      numbers = [2, 3, 4, 5, 6, 7, 8, 9, 10]
      prime_sum = sum_of_primes(numbers)
      print("Sum of prime numbers:", prime_sum)
      

15. Create a function to find the maximum subarray sum using Kadane's algorithm.
    - ```python
      def max_subarray_sum(lst):
          max_so_far = lst[0]
          max_ending_here = lst[0]
          
          for i in range(1, len(lst)):
              max_ending_here = max(lst[i], max_ending_here + lst[i])
              max_so_far = max(max_so_far, max_ending_here)
          
          return max_so_far
      
      numbers = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
      max_sum = max_subarray_sum(numbers)
      print("Maximum subarray sum:", max_sum)
      

16. Write a program to implement a stack using a list.
    - ```python
      class Stack:
          def __init__(self):
              self.stack = []
          
          def push(self, item):
              self.stack.append(item)
          
          def pop(self):
              if not self.is_empty():
                  return self.stack.pop()
              else:
                  return "Stack is empty"
          
          def peek(self):
              if not self.is_empty():
                  return self.stack[-1]
              else:
                  return "Stack is empty"
          
          def is_empty(self):
              return len(self.stack) == 0
          
          def __len__(self):
              return len(self.stack)
      
      stack = Stack()
      stack.push(10)
      stack.push(20)
      stack.push(30)
      print("Top element:", stack.peek())
      print("Popped element:", stack.pop())
      print("Stack size:", len(stack))
      

17. Implement a function to find the missing number in a list of consecutive numbers.
    - ```python
      def find_missing_number(lst):
          n = len(lst) + 1
          expected_sum = n * (n + 1) // 2
          actual_sum = sum(lst)
          return expected_sum - actual_sum
      
      numbers = [1, 2, 3, 4, 6, 7, 8, 9, 10]
      missing_number = find_missing_number(numbers)
      print("Missing number:", missing_number)
      

18. Write a Python program to find the number of unique elements in a list.
    - ```python
      def count_unique(lst):
          return len(set(lst))
      
      my_list = [1, 2, 3, 2, 4, 5, 1, 6]
      unique_count = count_unique(my_list)
      print("Number of unique elements:", unique_count)
      

19. Create a function to find the longest common prefix among a list of strings.
    - ```python
      def longest_common_prefix(strs):
          if not strs:
              return ""
          
          prefix = strs[0]
          for i in range(1, len(strs)):
              while prefix and not strs[i].startswith(prefix):
                  prefix = prefix[:-1]
              if not prefix:
                  return ""
          
          return prefix
      
      words = ["flower", "flow", "flight"]
      common_prefix = longest_common_prefix(words)
      print("Longest common prefix:", common_prefix)
      

20. Write a program to implement a linked list data structure.
    - ```python
      class Node:
          def __init__(self, data):
              self.data = data
              self.next = None
      
      class LinkedList:
          def __init__(self):
              self.head = None
          
          def append(self, data):
              new_node = Node(data)
              if self.head is None:
                  self.head = new_node
                  return
              last_node = self.head
              while last_node.next:
                  last_node = last_node.next
              last_node.next = new_node
          
          def print_list(self):
              current_node = self.head
              while current_node:
                  print(current_node.data)
                  current_node = current_node.next
      
      linked_list = LinkedList()
      linked_list.append(1)
      linked_list.append(2)
      linked_list.append(3)
      linked_list.print_list()
      

