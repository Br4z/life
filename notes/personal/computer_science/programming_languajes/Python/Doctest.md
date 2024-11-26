---
Author: Geeks for Geeks
Language: English
Source: https://www.geeksforgeeks.org/testing-in-python-using-doctest-module
---

# Doctest

**Docstrings** are used not only for the description of a class or a function to provide a better understanding of the code and its use but, also used for testing purposes. This module finds patterns in the docstring that look like interactive **shell commands**. The input and expected output are included in the docstring, then the doctest module uses this docstring for testing the processed output.

## How to use Doctest

1. Import `testmod` from `doctest` to test the function.

2. Define our test function.

3. Provide a suitable docstring containing the desired output on certain inputs.

4. Define the logic.

5. Call `testmod` with the name of the function to test and set `verbose` to `True` as arguments.

    > You can achieve a similar behavior using `-v` in the script execution.

    > If `verbos` is set to `False` (default), output will be shown in case of failure only, not in case of success.

## Limitations of Doctest module

- Limited test coverage: Doctest relies heavily on docstrings, making it suitable mainly for testing small code snippets or simple functions. It may not cover all aspects of complex functions or classes.

- Readability issues: test cases embedded within docstrings can sometimes clutter the documentation, leading to reduced readability, especially for larger projects with numerous tests.

- Brittleness: Doctest tests are sensitive to changes in output formatting or minor code modifications, which can cause tests to fail unnecessarily. This brittleness makes maintenance challenging, especially in evolving codebases.

## Usage example

```PY
def multiple_test_cases(number):
    """
    This function checks multiple test cases for a given number.
    Define input and expected output:
    >>> multiple_test_cases(0)
    "Zero"
    >>> multiple_test_cases(5)
    "Positive"
    >>> multiple_test_cases(-5)
    "Negative"
    >>> multiple_test_cases(100)
    "Large positive"
    >>> multiple_test_cases(-100)
    "Large negative"
    """
    if number == 0:
        return "Zero"
    elif number > 0:
        if number > 10:
            return "Large positive"
        else:
            return "Positive"
    else:
        if number < -10:
            return "Large negative"
        else:
            return "Negative"


if __name__ == "__main__":
    import doctest
    doctest.testmod(verbose=True)
```
