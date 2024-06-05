---
Author: Geeks for Geeks
Language: English
Source: https://www.geeksforgeeks.org/python-map-function
---

# `map`

Applies a given function to all the items in an input sequence (or multiple sequences) and returns an iterator with the results.

## Maps syntax

```PY
map(function, sequences)
```

- `function`: function that transforms an element or elements.

    > The function must accept as many arguments as there are sequences.

- `sequences`: one or more sequences that need to be mapped. These can be lists, tuples, sets, or any other iterables.

It returns an iterator that applies the function to all items of the given sequences.

## Usage expample

```PY
numbers_1 = [1, 2, 3]
numbers_2 = [4, 5, 6]

result = map(lambda x, y: x + y, numbers_1, numbers_2)
print(list(result))
```
