# Data Structures

## Task 1

* `combine_dict(*args)` function retrieves changeable numbers of dictionary and sums the values of the same dictionary keys using a method `dict.get()` that accesses the dictionaries received by the function and dictionary created inside it; otherwise, it uses the dictionary method `dict.update()`:

```python
def combine_dicts(*args: dict) -> str:
    comb_dict = {}
    for dicts in args:
        key_set = set(comb_dict.keys()) & set(dicts.keys())
        if key_set:
            for key_1 in key_set:
                comb_dict.update({key_1: dicts.get(key_1) + comb_dict.get(key_1)})
            key_set_1 = set(dicts.keys()) - key_set
            for key_2 in key_set_1:
                comb_dict.update({key_2: dicts.get(key_2)})
        elif not key_set:
            comb_dict.update(dicts)
    return f'Modified dictionary with summarized values in case of identical keys:' \
           f'\n{comb_dict}'
```

* Function output:

```python
if __name__ == '__main__':
    dict_1 = {'a': 100, 'b': 200}
    dict_2 = {'a': 200, 'b': 300}
    dict_3 = {'a': 300, 'd': 100}
    dict_4 = {'a': 300, 'e': 124, 'h': 13}
    dict_5 = {'q': 11, 'p': 13}
    dict_6 = {'p': 13}
    print(combine_dicts(dict_1, dict_2, dict_3, dict_4, dict_5, dict_6))

>>> Modified dictionary with summarized values in case of identical keys:
    {'a': 900, 'b': 500, 'd': 100, 'e': 124, 'h': 13, 'q': 11, 'p': 26}
```
