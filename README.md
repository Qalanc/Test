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

## Task 2

* Class representing linked List and class `Node` storing each linked list node:

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class Linked_List:
    def __init__(self, nodes=None):
        self.head = None
        if nodes is not None:
            node = Node(data=nodes.pop(0))
            self.head = node
            for elem in nodes:
                node.next = Node(elem)
                node = node.next
```

* `Linked_List` class method `__iter__()` to iterate through linked list as Python original list:

```python
def __iter__(self):
    node = self.head
    while node is not None:
        yield node
        node = node.next
```

* Magic method `__repr__()` returns human readable linked list:

```python
def __repr__(self):
    node = self.head
    nodes = []
    while node is not None:
        nodes.append(node.data)
        node = node.next
    nodes.append('None')
    return ' -> '.join(nodes)
```

* The following method retrieves index and returns value: 

```python
def show(self, index):
    counter = 0
    for node in self:
        if index == counter:
            return node
        counter += 1

    raise Exception("Linked list index is out of range")
```

* `Linked_List.append_left()` and `Linked_List.append()` methods allows to insert values to the end or beginning of the list, respectively:

```python
def append_left(self, node):
    node.next = self.head
    self.head = node

def append(self, node):
    if not self.head:
        self.head = node
        return
    for i in self:
        pass
    i.next = node
```

* The following method receive `index` argument and `new_node` that will change an existing value:

```python
def change(self, index, new_node):
    if not self.head:
        raise Exception("Linked list is empty")

    counter = 0
    for node in self:
        if index == counter:
            node.data = new_node
            return
        counter += 1

    raise Exception("Linked list index is out of range")
```

* `Linked_List.insert()` method works like the method above, but by inserting values, not replacing them:

```python
def insert(self, index, insert_node):
    if not self.head:
        raise Exception("Linked list is empty")

    counter = 1
    for node in self:
        if index == counter:
            insert_node.next = node.next
            node.next = insert_node
            return
        counter += 1

    raise Exception("Linked list index is out of range")
```

* Method working as `list.remove()`:

```python
def remove(self, pop_node):
    if not self.head:
        raise Exception("List is empty")

    if pop_node == 0:
        self.head = self.head.next
        return

    counter = 0
    previous_node = self.head
    for node in self:
        if counter == pop_node:
            previous_node.next = node.next
            return
        previous_node = node
        counter += 1

    raise Exception("Node with data not found")
```

* The following methods clear the list and return it's length: 

```python
 def clear(self):
        if not self.head:
            raise Exception("Linked list is empty")

        for node in self:
            self.head = node
        self.head = None

def len(self):
    if not self.head:
        return 0
    
    counter = 0
    for node in self:
        counter += 1
    return counter
```

* Class output:

```python
if __name__ == '__main__':
    CustomList = Linked_List(['b', 'c', 'd', 'e'])

    # __iter__() method
    for el in CustomList:
        print(el)

    >>> b
    >>> c
    >>> d
    >>> e

    # __repr__() method
    print('\n', CustomList)

    >>> ['b', 'c', 'd', 'e', 'None']

    print('\n', CustomList.show(3))

    >>> e

    CustomList.append_left(Node('a'))
    CustomList.append(Node('g'))
    print('\n', CustomList)

    >>> ['a', 'b', 'c', 'd', 'e', 'g', 'None']

    CustomList.change(3, 7)
    print('\n', CustomList)

    >>> ['a', 'b', 'c', 7, 'e', 'g', 'None']

    CustomList.insert(2, Node(3))
    print('\n', CustomList)

    >>>  ['a', 'b', 3, 'c', 7, 'e', 'g', 'None']

    CustomList.remove(1)
    print('\n', CustomList)
    
    >>>  ['a', 3, 'c', 7, 'e', 'g', 'None']

    print('\n', CustomList.len())
    
    >>> 6

    CustomList.clear()
    print('\n', CustomList)
    
    >>> ['None']
```
