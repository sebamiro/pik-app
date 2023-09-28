+++
title = "push_swap"
template = "project.html"
weight = 4
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/push_swap42/">GitHub</a>

---

# Push_swap

## Summary

Is an individual project about creating an algorithm that efficiently sorts
a stack of integers in ascending order using only a specific set of operations

There are two stacks: Stack A and Stack B, initially, all the numbers to be sorted
are in Stack A, while Stack B is empty. Operations allowed on the stacks are limited:

		sb:   swaps the 2 top elements of b
        sa:   swaps the 2 top elements of a
		ss:   both sa and sb
		pa:   moves the top element of b at the top of a
		pb:   moves the top element of a at the top of b
		ra:   shifts all elements of a from bottom to top
		rb:   shifts all elements of b from bottom to top
		rr:   both ra and rb
		rra:  shifts all elements of a from top to bottom
		rrb:  shifts all elements of b from top to bottom
		rrr:  both rra and rrb

The algorithm needs to be efficient, aiming for the smallest number of steps (operations) possible,
taking into account edge cases and error handling.

## Introduction

The Push swap project is a very simple and a highly straightforward algorithm project:
data must be sorted.

You have at your disposal a set of integer values, 2 stacks, and a set of instructions
to manipulate both stacks.

Your goal? Write a program in C called push_swap which calculates and displays
on the standard output the smallest program, made of Push swap language instructions,
that sorts the integers received as arguments.

Writing a sorting algorithm is always a very important step in a developer’s journey. It
is often the first encounter with the concept of complexity.

Sorting algorithms and their complexity are part of the classic questions discussed
during job interviews. It’s probably a good time to look at these concepts since you’ll
have to face them at some point.

The learning objectives of this project are rigor, use of C, and use of basic algorithms.
Especially focusing on their complexity.

Sorting values is simple. To sort them the fastest way possible is less simple. Especially
because from one integers configuration to another, the most efficient sorting solution can
differ.

## Mandatory part

Your project must comply with the following rules:
- You have to turn in a Makefile which will compile your source files. It must not
relink.
- Global variables are forbidden.
- You have to write a program named push_swap that takes as an argument the stack
a formatted as a list of integers. The first argument should be at the top of the
stack (be careful about the order).
- The program must display the smallest list of instructions possible to sort the stack
a, the smallest number being at the top.
- Instructions must be separated by a ’\n’ and nothing else.
- The goal is to sort the stack with the lowest possible number of operations. During
the evaluation process, the number of instructions found by your program will be
compared against a limit: the maximum number of operations tolerated. If your
program either displays a longer list or if the numbers aren’t sorted properly, your
grade will be 0.
- If no parameters are specified, the program must not display anything and give the
prompt back.
- In case of error, it must display "Error" followed by a ’\n’ on the standard error.
Errors include for example: some arguments aren’t integers, some arguments are
bigger than an integer and/or there are duplicates.

## Bonus part

Write a program named checker that takes as an argument the stack a formatted
as a list of integers. The first argument should be at the top of the stack (be careful
about the order). If no argument is given, it stops and displays nothing.

It will then wait and read instructions on the standard input, each instruction will
be followed by ’\n’. Once all the instructions have been read, the program has to
execute them on the stack received as an argument

If after executing those instructions, the stack a is actually sorted and the stack b
is empty, then the program must display "OK" followed by a ’\n’ on the standard
output.

In every other case, it must display "KO" followed by a ’\n’ on the standard output

In case of error, you must display "Error" followed by a ’\n’ on the standard er-
ror. Errors include for example: some arguments are not integers, some arguments
are bigger than an integer, there are duplicates, an instruction doesn’t exist and/or
is incorrectly formatted.

