# Functions

1.Write a Python function to listeven and odd numbers in a list. 


```python

def separate_even_odd(numbers):
    even_numbers = []
    odd_numbers = []
    
    for num in numbers:
        if num % 2 == 0:
            even_numbers.append(num)
        else:
            odd_numbers.append(num)
    
    return even_numbers, odd_numbers

numbers = [1, 2, 3, 4, 5, 6]
even, odd = separate_even_odd(numbers)
print("Even numbers:", even)
print("Odd numbers:", odd)
```

    Even numbers: [2, 4, 6]
    Odd numbers: [1, 3, 5]
    

2.Write and run a Python program that asks the user to enter 8 integers(one at a time), and then prints out how many of
those integers were even numbers. For example, if the users entered 19, 6, 9, 20, 13, 7, 6, and 1, then your program 
should print out 3 since 3 of those numbers were even.


```python
even_count = 0

for i in range(8):
    try:
        num = int(input("Enter an integer: "))
        if num % 2 == 0:
            even_count += 1
    except ValueError:
        print("Invalid input. Please enter an integer.")

print("The number of even integers entered:", even_count)

```

    Enter an integer: 19
    Enter an integer: 6
    Enter an integer: 9
    Enter an integer: 20
    Enter an integer: 13
    Enter an integer: 7
    Enter an integer: 6
    Enter an integer: 1
    The number of even integers entered: 3
    

3. Write a Python program where you take any positive integers n, if n is even, divide it by 2 to get n/2 if n is odd,
multiply it by 3 and add 1 to obtain 3n + 1.Repeat the process until you reach 1


```python
def collatz_sequence(n):
    while n != 1:
        print(n)
        if n % 2 == 0:
            n = n // 2
        else:
            n = 3 * n + 1
    print(1)

n = int(input("Enter a positive integer: "))
if n <= 0:
    print("Please enter a positive integer.")
else:
    collatz_sequence(n)
```

    Enter a positive integer: 6
    6
    3
    10
    5
    16
    8
    4
    2
    1
    

4.Write a Python program to compute the sum of all multiples of 3 or 5 below 500.


```python
def sum_multiples_3_or_5(limit):
    total = 0
    for number in range(limit):
        if number % 3 == 0 or number % 5 == 0:
            total += number
    return total

limit = 500

result = sum_multiples_3_or_5(limit)

print("The sum of all multiples of 3 or 5 below 500 is:", result)

```

    The sum of all multiples of 3 or 5 below 500 is: 57918
    

5.To write a python program to find first n prime numbers from a list of given  numbers


```python
def list_of_primes(n):
    primes = []
    for y in range (2, n):
        for z in range(2, y):
            if y % z == 0:
                break
        else:
            primes.append(y)
    primes.sort()
    return primes

list_of_primes(20)
```




    [2, 3, 5, 7, 11, 13, 17, 19]



6.To write a python program to compute matrix multiplication


```python
def matrix_multiply(matrix1, matrix2):
    result = []
    
    if len(matrix1[0]) != len(matrix2):
        print("Matrix multiplication is not possible.")
        return None

    for i in range(len(matrix1)):
        result.append([0] * len(matrix2[0]))

    for i in range(len(matrix1)):
        for j in range(len(matrix2[0])):
            for k in range(len(matrix2)):
                result[i][j] += matrix1[i][k] * matrix2[k][j]

    return result

matrix_A = [[1, 2], [3, 4]]
matrix_B = [[5, 6], [7, 8]]

result_matrix = matrix_multiply(matrix_A, matrix_B)

if result_matrix:
    for row in result_matrix:
        print(row)
```

    [19, 22]
    [43, 50]
    

7.Write a python program function to count the numbers of vowels in a string


```python
def count_vowels(string):
    
    string = string.lower()
    
    vowel_count = 0
    
    vowels = set("aeiou")
    
    for char in string:
        if char in vowels:
            vowel_count += 1
    
    return vowel_count

input_string = "Basaveshwara College"
result = count_vowels(input_string)
print("Number of vowels:", result)
```

    Number of vowels: 8
    

8. Write a python function for finding factorial for the give number using a recursive function


```python
def factorial_recursive(n):
    if n == 0:
        return 1
    else:
        return n * factorial_recursive(n - 1)

number = 7
result = factorial_recursive(number)
print(f"The factorial of {number} is {result}")
```

    The factorial of 7 is 5040
    

9.Write a python Function for generating the Fibonacci series using the function


```python
a=int(input('any number pl: '))
def fib():

    a,b=0,1
    while 1:
        yield a
        a,b=b,a+b
        
a=fib()
```

    any number pl: 6
    


```python
next(a)
```




    0




```python
next(a)
```




    1




```python
next(a)
```




    1




```python
next(a)
```




    2




```python
next(a)
```




    3



10. Python program to display the given integer in reverse order using the function without an in-built function


```python
def reverse_integer(number):
    reversed_number = 0
    while number > 0:
        digit = number % 10
        reversed_number = reversed_number * 10 + digit
        number = number // 10
    return reversed_number


num = int(input("Enter an integer: "))
reversed_num = reverse_integer(num)
print("Reversed integer:", reversed_num)
```

    Enter an integer: 12345
    Reversed integer: 54321
    

11.Write a Python function to display all integers within the range 200 to 300 whose sum of digit is an even number.


```python
def is_even_digit_sum(number):
    digit_sum = sum(int(digit) for digit in str(number))
    return digit_sum % 2 == 0

def display_even_digit_sum_numbers(start, end):
    for num in range(start, end + 1):
        if is_even_digit_sum(num):
            print(num)

display_even_digit_sum_numbers(200, 300)

```

    200
    202
    204
    206
    208
    211
    213
    215
    217
    219
    220
    222
    224
    226
    228
    231
    233
    235
    237
    239
    240
    242
    244
    246
    248
    251
    253
    255
    257
    259
    260
    262
    264
    266
    268
    271
    273
    275
    277
    279
    280
    282
    284
    286
    288
    291
    293
    295
    297
    299
    

12.Write a Python function to find a number of digits and sum of digits for a given integer


```python
def count_digits_and_sum(number):

    num_str = str(number)
    
    num_of_digits = len(num_str)
    digit_sum = 0
    
    for digit in num_str:
        digit_sum += int(digit)
    
    return num_of_digits, digit_sum

input_number = 12345
num_of_digits, digit_sum = count_digits_and_sum(input_number)
print(f"Number of digits: {num_of_digits}")
print(f"Sum of digits: {digit_sum}")
```

    Number of digits: 5
    Sum of digits: 15
    

13.Write a Function called is_sorted that takes a list as a paramater and returns True if the list is sorted in 
ascending order and false otherwise and has_duplicates that takes a list and returns True if there is any element
that returns that appears more than once. It should not modify the original list


```python
def is_sorted(lst):
   
    return all(lst[i] <= lst[i + 1] for i in range(len(lst) - 1))

def has_duplicates(lst):
  
    seen = set()
    for item in lst:
        if item in seen:
            return True
        seen.add(item)
    return False

lst = [5, 6, 7, 8, 9]
print(is_sorted(lst)) 

lst = [8, 1, 6, 2, 5]
print(is_sorted(lst))  

lst = [1, 5, 5, 10, 6]
print(has_duplicates(lst))  

lst = [1, 3, 7, 8, 5]
print(has_duplicates(lst))
```

    True
    False
    True
    False
    

14.Write the functions called nested_sum that takes a list of integersand adds up the elements from all the nested
ifs and cumsums that takes a list of numbers and returns the cumulative sum;that is, a new list where the ith element
is is the sum of the first i+1 elements from the original list


```python
def nested_sum(lst):
    total = 0
    for sublist in lst:
        total += sum(sublist)
    return total

def cumsum(lst):
    cumulative_sum = 0
    result = []
    for num in lst:
        cumulative_sum += num
        result.append(cumulative_sum)
    return result

nested_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
cumulative_list = [1, 2, 3, 4, 5]
print("Nested Sum:", nested_sum(nested_list))
print("Cumulative Sum:", cumsum(cumulative_list))
```

    Nested Sum: 45
    Cumulative Sum: [1, 3, 6, 10, 15]
    


```python

```
