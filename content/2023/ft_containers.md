+++
title = "containers"
template = "project.html"
weight = 9
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/ft_containers">GitHub</a>

---

# Containers

## Summary

Is an individual project about implementing the various container
types of the C++ standard template library, in C++98.

- Stack: Container adaptor, use an encapsulated object of a specific
  container class as its underlying container, providing a set of member functions to access its elements. Last-in first-out.
- Vector: Implemented as dynamic arrays with the ability to resize itself automatically when an element is inserted or deleted,
  ith their storage being handled automatically by the container. The elements are stored contiguously, which means that can
  be accessed not only through iterators, but also using offsets to regular pointers to elements.
- Map: Is a sorted associative container that contains key-value pairs with unique keys. Keys are sorted by using the
  comparison function Compare. Search, removal, and insertion operations have logarithmic complexity. Implemented as a Red-Black tree.
- Set: Is container that store unique elements following a specific order. The value of an element also identifies it, cannot be modified once in the container
  (the elements are always const), but they can be inserted or removed from the container.

		├─ Vector
		├─ Map
		├─ Stack
		├─ Set
		├─ utility
		├─ Itreator/
		│  ├─ iterator_traits
		│  ├─ random_access_iterator
		│  └─ reverse_iterator
		├─ RedBlackTree/
		│  ├─ RBT
		│  ├─ RBT_iterator
		└  └─ node

## Introduction

The standard C++ containers have all a specific usage.
To make sure you understand them, let’s re-implement them!

In this project, you will implement a few container types of the C++ standard template
library.
You have to take the structure of each standard container as reference. If a part of
the Orthodox Canonical form is missing in it, do not implement it.
As a reminder, you have to comply with the C++98 standard, so any later feature of
the containers MUST NOT be implemented, but every C++98 feature (even deprecated
ones) is expected

### Compiling

- Compile your code with c++ and the flags -Wall -Wextra -Werror
- Your code should still compile if you add the flag -std=c++98

### Allowed/Forbidden

You are not coding in C anymore. Time to C++! Therefore:
- You are allowed to use everything from the standard library. Thus, instead of
sticking to what you already know, it would be smart to use as much as possible
the C++-ish versions of the C functions you are used to.
- However, you can’t use any other external library. It means C++11 (and derived
forms) and Boost libraries are forbidden. The following functions are forbidden
too: *printf(), *alloc() and free(). If you use them, your grade will be 0 and
that’s it.

### A few design requirements
- Memory leakage occurs in C++ too. When you allocate memory, you must avoid
memory leaks.
- Any function implementation put in a header file (except for function templates)
means 0 to the exercise.
- You should be able to use each of your headers independently from others. Thus,
they must include all the dependencies they need. However, you must avoid the
problem of double inclusion by adding include guards. Otherwise, your grade will
be 0.

## Mandatory part

Implement the following containers and turn in the necessary \<container\>.hpp files:
- vector<br>
You don’t have to do the vector\<bool\> specialization.
- map
- stack<br>
It will use your vector class as default underlying container. But it must still be
compatible with other containers, the STL ones included.
You also have to implement:
- iterators_traits
- reverse_iterator
- enable_if<br>
Yes, it is C++11 but you will be able to implement it in a C++98 manner.
This is asked so you can discover SFINAE.
- is_integral
- equal and/or lexicographical_compare
- std::pair
- std::make_pair

### Requirements

- The namespace must be ft.
- Each inner data structure used in your containers must be logical and justified (this
means using a simple array for map is not ok).
- You cannot implement more public functions than the ones offered in the standard
containers. Everything else must be private or protected. Each public function or
variable must be justified.
- All the member functions, non-member functions and overloads of the standard
containers are expected.
- You must follow the original naming. Take care of details.
- If the container has an iterator system, you must implement it.
- You must use std::allocator.
- For non-member overloads, the keyword friend is allowed. Each use of friend
must be justified and will be checked during evaluation.
- Of course, for the implementation of map::value_compare, the keyword friend is
allowed.

### Testing

- You must also provide tests, at least a main.cpp, for your defense. You have to go
further than the main given as example!
- You must produce two binaries that run the same tests: one with your containers
only, and the other one with the STL containers.
- Compare outputs and performance / timing (your containers can be up to 20
times slower).
- Test your containers with: ft::\<container\>.

## Bonus part

You will get extra points if you implement one last container:
- set<br>
But this time, a Red-Black tree is mandatory.

