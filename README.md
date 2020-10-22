# Loops

## Transpose a matrix

* The `while` loop allows infinitely accepting values and converting it to a nested list until the `exit` command is entered:

```python
while True:
    matrix_input = input('Input: ').replace(' ', '')

    if matrix_input == 'exit':
        break

    matrix_input = [list(matrix_input)]
    matrix_list += matrix_input
```

* Next two `for` loops outputs nested list as original matrix and transposed it:

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

