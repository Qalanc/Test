# Types and Values

## Exercise 1

1. Return the count of negative numbers in next list [4, -9, 8, -11, 8]
2. Note: do not use conditionals or loops

* Create function that takes `list` and returns `int` data types. With method `repr()` return a canonical string representation of the object and using string method `str.count()` calculate negative values with minus sign:

```python
def count_negatives(numbers: list) -> int:
    numbers = repr(numbers)
    return numbers.count('-')
```

* Use to following construction to avoid executing of function when import module:

```python
if __name__ == '__main__':
    input_numbers = [4, -9, 8, -11, 8]
    print(f'There are {count_negatives(input_numbers)} negative numbers in list {input_numbers}')
```

## Exercise 2

1. You have first 5 best players according API rankings. Set the first place player (at the front of the list) to last place and vice versa.
2. players = ['Ashleigh Barty', 'Simona Halep', 'Naorni Osaka', 'Karolina Pliskova', 'Elina Svitolina']

* Define list of tennis players:

```python
tennis_players = ['Ashleigh Barty', 'Simona Halep', 'Naorni Osaka', 'Karolina Pliskova', 'Elina Svitolina']
``` 

* Create function that takes `list` data types and returns it vice versa version. Thus, using slicing `players[::-1]` returns list with step `-1`:

```python
def change_position(players: list):
    players = players[::-1]
    print(players)
```

* Call function to see the result:

```python
if __name__ == '__main__':
    change_position(tennis_players)
```

## Exercise 3

1. Swap words "reasonable" and "unreasonable" in quote "The reasonable man adapts himself to the world; the unreasonable one persists in trying to adapt the world to himself."
2. Note. Do not use `<string>.replace()` function or similar.

* Define quote with `str` object:

```python
sentence = 'The reasonable man adapts himself to the world; the unreasonable one persists in trying to adapt the ' \
           'world to himself'
```

* Create two `list` objects. The first object represents the list of words, obtained by `str` method `split`, from the quote. The second object for adapting it:

```python
list_words = sentence.split()
new_list = list()
```

* Operate with words to be changed using two `int` objects with required words indexes:

```python
reasonable = list_words.index('reasonable')
unreasonable = list_words.index('unreasonable')
```

* Create loop that going through the list quote words and write it to `new_list` variable using `list` method `list.append()`, except "reasonable" and "unreasonable" swapping words:

```python
for i in range(0, len(list_words)):
    if i == reasonable:
        new_list.append(list_words[unreasonable])
    elif i == unreasonable:
        new_list.append(list_words[reasonable])
    else:
        new_list.append(list_words[i])
```

* Use `str` method to `join` create string from the list and print it:

```python
new_sentence = ' '.join(new_list)

print(new_sentence)
```
