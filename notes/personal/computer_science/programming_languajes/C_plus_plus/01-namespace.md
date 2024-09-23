---
Author: Geeks for Geeks
Language: English
Source: https://www.geeksforgeeks.org/namespace-in-c
reviewed_on: "2024-10-16"
---

# Namespace

It provides the space where we can define or declare an identifier, in other words, we can define the space or context in which identifiers are defined.

## Why use it?

A namespace is designed to overcome the name collision error and is used as additional information to differentiate functions, classes, similar variables, etc.

> Different libraries with the same bindings.

## Declaring a namespace

A namespace definition begins with the namespace keyword followed by the namespace name as follows:

```CPP
namespace  namespace_name {
    // Code declarations
}
```

> You can nest namespaces.

## The `using`

This directive tells the compiler that the subsequent code is making use of names in the specified namespace.

```CPP
using namespace <namespace>;

// Follwing code
```

## Usage example

```CPP
#include <iostream>
#include <string>

namespace first_namespace {
    void func() {
        std::cout << "Inside first_namespace" << std::endl;
    }

    namespace second_space {
        void func() {
            std::cout << "Inside second_namespace" << std::endl;
        }
    }

    void cout(std::string text) {
        std::cout << text << std::endl;
    }
}

using namespace first_namespace::second_space;
int main () {
    func();
    first_namespace::cout("text");

    return 0;
}
```
