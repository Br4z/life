---
Author: Daniel Marcial
Language: English
Source: https://www.freecodecamp.org/news/build-your-first-python-package

Author: Geeks for Geeks
Language: English
Source: https://www.geeksforgeeks.org/python-modules
---

# Module

It is a file containing definitions and statements. A module can define functions, classes, and variables. A module can also include runnable code.

## Importing a module

We can import the functions and classes defined in a module to another module using `import` in some other source file.

## Locating modules

Whenever a module is imported, the interpreter looks for several locations. First, it will check for the **built-in** module; if it is not found, then it looks for a list of directories defined in `sys.path`. The interpreter searches for the module in the following manner:

1. Current directory.

2. Each directory in `PYTHONPATH`.

    > The "PYTHONPATH" is an environment variable consisting of a list of directories.

3. The installation-dependent list of directories configured at the time Python is installed.

## Module creation

In the `setup.py` we will store information about the package, namely the package name, its version, platform dependencies and so on. To build the distributable package we will use the `python <setup file> sdist bdist_wheel` command.

> To install `setuptool` we can do it through pip, using the command `pip install setuptools`.

> The `bdist_wheel` (provided by the `wheel`) argument is only needed if we want to upload the package to PyPi.
