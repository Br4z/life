---
Author: Geeks for Geeks
Language: English
Source: https://www.geeksforgeeks.org/python-lambda
---

# `lambda`

`lambda` is used to create anonymous functions.

## Lambda syntax

```PY
lambda arguments: expression
```

## Lambda properties

- Can have any number of arguments but only one expression, which is evaluated and returned.

- Syntactically restricted to a single expression.

## Usage examples

```PY
filter_numbers = lambda string: "".join([character for character in string if not character.isdigit()])
print(f"filter_numbers(): {filter_numbers("Geeks101")}")

do_exclaim = lambda string: string + "!"
print(f"do_exclaim(): {do_exclaim("I am tired")}")

sum_digits = lambda number: sum([int(digit) for digit in str(number)])
print(f"sum_digits(): {sum_digits(101)}")
```
