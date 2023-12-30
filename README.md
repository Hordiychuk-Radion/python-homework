# python-homework

**1. Counting Odd and Even Numbers In list**

```
odd_count = 0
even_count = 0


num_list = list(map(int, input("Enter a list of numbers separated by space: ").split()))

for number in num_list:
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1



print(f"Number of odd numbers: {odd_count}")
print(f"Number of even numbers: {even_count}")

```
**2. Factorial Calculation (Input Number, Output Result)**


```
def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n - 1)

number = int(input("Enter a number to find its factorial: "))
result = factorial(number)
print(f"The factorial of {number} is {result}")
```

**3. Write a program that prompts the user to enter a password. Check if the entered password meets the following criteria:
At least 8 characters long
Contains both uppercase and lowercase letters
Contains at least one digit**

```
def check_password_criteria(password):
    try:
        if len(password) < 8:
            raise ValueError("Password should be at least 8 characters long.")
        if not any(char.isupper() for char in password):
            raise ValueError("Password should contain at least one uppercase letter.")
        if not any(char.islower() for char in password):
            raise ValueError("Password should contain at least one lowercase letter.")
        if not any(char.isdigit() for char in password):
            raise ValueError("Password should contain at least one digit.")

        print("Password meets the criteria.")
    except ValueError as e:
        print(f"Invalid Password: {e}")


password = input("Enter a password: ")
check_password_criteria(password)
```
**4. Palindrome Checker.  A palindrome is a word that reads the same backward as forward (ignoring spaces, punctuation, and capitalization).**

```
def is_palindrome(word):
    word = ''.join(e.lower() for e in word if e.isalnum())
    return word == word[::-1]

word = input("Enter a word to check if it's a palindrome: ")

if is_palindrome(word):
    print(f"The word '{word}' is a palindrome.")
else:
    print(f"The word '{word}' is not a palindrome.")
```

**5. Create a simple "Guess the Number" game where the computer randomly selects a number between 1 and 100, and the user has to guess it. Provide feedback to the user if their guess is too high or too low.**

```
import random

def guess_the_number():
    secret_number = random.randint(1, 100)
    attempts = 0

    while True:
        guess = int(input("Guess the number between 1 and 100: "))
        attempts += 1

        if guess < secret_number:
            print("Too low. Try again!")
        elif guess > secret_number:
            print("Too high. Try again!")
        else:
            print(f"Congratulations! You guessed it in {attempts} attempts.")
            break

guess_the_number()
```


**6. Write a program that takes a sentence as input and counts the frequency of each word in the sentence. Ignore case and punctuation.**

```
import string
from collections import Counter

def count_word_frequency(sentence):
    
    words = sentence.translate(str.maketrans('', '', string.punctuation)).lower().split()

    
    word_count = Counter(words)

    
    for word, count in word_count.items():
        print(f"'{word}': {count}")

user_sentence = input("Enter the sentence: ")
count_word_frequency(user_sentence)
```
**7. Implement a program that multiplies two matrices. Matrices can be represented as 2D lists. Ensure that the matrices are compatible for multiplication. Matrix Example: 
matrix1 = [[1, 2, 3], [4, 5, 6]]
matrix2 = [[7, 8], [9, 10], [11, 12]]**


```
def multiply_matrices(matrix1, matrix2):
    
    if len(matrix1[0]) != len(matrix2):
        return "Matrices are incompatible for multiplication."

    result = [[0 for _ in range(len(matrix2[0]))] for _ in range(len(matrix1))]

    for i in range(len(matrix1)):
        for j in range(len(matrix2[0])):
            for k in range(len(matrix2)):
                result[i][j] += matrix1[i][k] * matrix2[k][j]

    return result


matrix1 = [[1, 2, 3], [4, 5, 6]]
matrix2 = [[7, 8], [9, 10], [11, 12]]

result_matrix = multiply_matrices(matrix1, matrix2)
if isinstance(result_matrix, str):
    print(result_matrix)
else:
    for row in result_matrix:
        print(row)
```
