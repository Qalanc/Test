# Loops

## Transpose a matrix

* The `while` loop allows to infinitely accept the entered values and to convert it to a nested list until the `exit` command is entered:

```python
while True:
    matrix_input = input('Input: ').replace(' ', '')

    if matrix_input == 'exit':
        break

    matrix_input = [list(matrix_input)]
    matrix_list += matrix_input
```

* Next two `for` loops outputs nested list as original matrix and transposed ones:

```python
print('\nOriginal matrix is:')
for el_list in matrix_list:
    print()
    for el in range(0, len(el_list)):
        print(el_list[el], end=' ')


print('\n\nTransposed matrix is:')
for y in range(0, len(matrix_list[0])):
    print()
    for i in range(0, len(matrix_list)):
        print(matrix_list[i][y], end=' ')
```

## Factorial

* Calculate factorial using recursive function until input number equals one:

```python
def fact(num):
    if num == 1:
        return 1
    return num * fact(num - 1)
```

* The same program logic as in the function above, but using a `while` loop with `break` operator:

```python
def factorial(number):
    counter = 1
    while number > 1:
        counter *= number
        number -= 1
    return counter
```

* Printing the results of functions in the current module:

```python

if __name__ == '__main__':
    input_num = int(input('Please, enter the number to calculate the factorial: '))
    print(f'Function fact({input_num}): {fact(input_num)}')
    print(f'Function factorial({input_num}): {factorial(input_num)}')
```

## Fibonacci sequence

* Function prints sequence of Fibonacci numbers by adding the last two numbers from the list:

```python
def fibonacci(num):
    if num == 1:
        print([0])

    fib_list = [0, 1]

    while len(fib_list) < num:
        fib_list.append(fib_list[-2] + fib_list[-1])

    print(fib_list)
    print(sum(fib_list))
```

* Calculate series Fibonacci numbers by swapping variables:

```python
def fib(num):
    if num == 1:
        print([0])

    f1 = 0
    f2 = 1
    counter = 2
    fibonacci_list = [0, 1]

    while counter < num:
        f1, f2 = f2, f1 + f2
        fibonacci_list.append(f2)
        counter += 1

    print(fibonacci_list)
    print(sum(fibonacci_list))
```

Printing function outputs:

```python
if __name__ == '__main__':
    input_num = int(input('Please, enter the number to calculate the fibonacci sequence: '))

    print(f'\nFunction fibonacci({input_num}):')
    fibonacci(input_num)

    print(f'\nFunction fib({input_num}):')
    fib(input_num)
```

## Binary representation

* Assign `reverse_binary` variable string representation of remainder of the division by 2 and assignment of value from integer division `num` variable:

```python
while num >= 1:
    reverse_binary += str(num % 2)
    num //= 2
```

* Print binary representation of number and it sum:

```python
print('Number is ' + print_num + ', binary representation is ' + reverse_binary[::-1]
      + ', sum is ' + str(reverse_binary.count('1')))
```
