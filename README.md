# Conditionals

## Task 1

1. Write a program that determines whether the Point A(x,y) is in the shaded area or not.

* Equations for checking the occurrence of coordinates in a shaded area:

`abs(x) == y`

`abs(x) < y`

* Using equations above create validating function with `if` and `else` conditions:

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

*Full Python code: [Task 1](https://gitlab.com/maksym.karpov/online-python-external-program/-/blob/master/Conditionals/hw_3_1.py)

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
* Full Python code: [Task 2](https://gitlab.com/maksym.karpov/online-python-external-program/-/blob/master/Conditionals/hw_3_2.py)

## Task 3

1. Simulate the one round of play for baccarat game: 

2. Rules:

    * cards have a point value:
        * the 2 through 9 cards in each suit are worth face value (in points);
        * the 10, jack, queen and king have no point value (i.e. are worth zero);
        * aces are worth 1 point
     
    * Sum the values of cards. If total is more than 9 reduce 10 from result. E.g. 5 + 9 = 14, 14 - 10 = 4, 4 is the result
    
    * Player is not allowed to play another cards like joker
    
* Create `list` with cards allowed to play and a function to work with it:

```python
cards = ['2', '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K', 'A']

def play(first_card_: str, second_card_: str) -> str:
    # your code here
```

* Create part of dictionary with `zip()` function that merge keys and values:

```python
cards_2_9 = cards[0:cards.index('10')]
cards_dict_2_9 = {k: int(i) for k, i in zip(cards_2_9, cards_2_9)}
``` 

* Define other parts using dictionary generator:

```python
cards_10_k = cards[cards.index('10'): cards.index('A')]
cards_dict_10_k = {y: 0 for y in cards_10_k}

cards_dict_a = {g: 1 for g in cards[cards.index('A')]}
```

* New `cards_dict` variable which collects all the parts:

```python
cards_dict = dict()
cards_dict.update(cards_dict_2_9)
cards_dict.update(cards_dict_10_k)
cards_dict.update(cards_dict_a)
```

* Create a condition availability entered by the user cards in the dictionary and returns a string representation entered cards sum with `dict.get()` method:

```python
if first_card_ in cards_dict and second_card_ in cards_dict.keys():
    return str(cards_dict.get(first_card_) + cards_dict.get(second_card_))
else:
    return 'Do not cheat!'
```

* Define two variables to input cards and print the result:

```python
if __name__ == '__main__':
    first_card = str(input('Plat first card: ')).upper()
    second_card = str(input('Play second card: ')).upper()

    print('Your result:', play(first_card, second_card))
```

* Full Python code: [Task 2](https://gitlab.com/maksym.karpov/online-python-external-program/-/blob/master/Conditionals/hw_3_3.py)
