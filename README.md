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
