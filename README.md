# Conditionals

## Task 1

1. Write a program that determines whether the Point A(x,y) is in the shaded area or not.

* Formulas for checking the occurrence of coordinates in a shaded area:

`abs(x) == y`

`abs(x) < y`

* Using formulas above create validating function with `if` and `else` conditions:

```python
def validate_point(x_: float, y_: float) -> bool:
    if -1 <= x_ <= 1 and 0 <= y_ <= 1:
        if x_ <= y_:
            return True
        else:
            return False
    else:
        return False
``` 

* Define two variables to input coordinates and print the result:


```python
if __name__ == '__main__':
    x = abs(float(input('Enter x: ')))
    y = float(input('Enter y: '))

    print('Is point in shadow area:', validate_point(x, y))
```

## Task 2

1. Write a program that prints the input number from 1 to 100. But for multiple of three print "Fizz" instead of the number and for the multiples of five print "Buzz". For numbers which are multiples of both three and five print "FizzBuzz".

* Create condition checking numbers in range from 1 to 100:

```python
if 1 <= num <= 100:
    # your code here
else:
    return 'Out of range'
```

* Insert into condition body validation of multiple 3 and 5 otherwise return number:

```python
if number % 3 == 0 and number % 5 == 0:
    return 'FizzBuzz'
elif number % 3 == 0:
    return 'Fizz'
elif number % 5 == 0:
    return 'Buzz'
else:
    return str(number)
```

* Define variable to input number and print the result in an endless loop :

```python
if __name__ == '__main__':
    while True:
        num = int(input('Insert the number: '))

        print(fizz_buzz(num))
```
