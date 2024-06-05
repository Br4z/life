---
Author: Geeks for Geeks
Language: English
Source: https://www.geeksforgeeks.org/python-regex
---

# RegEx

Is a powerful tool for matching text based on a pre-defined pattern. It can detect the presence or absence of a text by matching it with a particular pattern, and also can split a pattern into one or more sub-patterns. The Python standard library provides a "re" module for regular expressions.

## Raw String Notation

Raw string notation (`rtext`) keeps regular expressions sane. Without it, every backslash (`\`) in a regular expression would have to be prefixed with another one to escape it.

## `re.search`

```PY
re.search(pattern, string, flags=0)
```

Scan through `string` looking for the first location where the `pattern` produces a match, and return a corresponding `Match` (otherwise it returns `None`).

## `re.match`

```PY
re.match(pattern, string, flags=0)
```

If zero or more characters at the beginning of `string` match `pattern`, return a corresponding `Match` (otherwise it returns `None`).

## `re.split`

```PY
re.split(pattern, string, maxsplit=0, flags=0)
```

Split `string` by the occurrences of `pattern`. If capturing parentheses are used in `pattern`, then the text of all groups in the pattern is also returned as part of the resulting list.

## `re.findall`

```PY
re.findall(pattern, string, flags=0)
```

Return all non-overlapping matches of `pattern` in `string`, as a list of strings or tuples. The string is scanned left-to-right, and matches are returned in the order found.
