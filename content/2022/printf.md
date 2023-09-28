+++
title = "printf"
template = "project.html"
weight = 1
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/printf42/">GitHub</a>

-----------

# Printf

## Summary

Is an individual project about recoding the famous printf C function
into its own library, to learn about variadic functions and improve algorithmic methodology
<br>
- %: (% character)
- c: char (character)
- s: char * (string)
- p: void * (pointer's address)
- u: unsigned int (unsigned decimal integer)
- x/X: unsigned int (hexadecimal)
- d/i: int (integer)

```
int
findtype(va_list ap, char c)
{
	if (c == '%')
		return (write(1, "%", 1));
	else if (c == 'c')
		return (handlechar(ap));
	else if (ft_strchr(c, "diuxX"))
		return (handlenbr(ap, c));
	else if (c == 's')
		return (handlestr(ap));
	else if (c == 'p')
		return (handleptr(ap));
	return (-1);
}
```

## Introduction

You will discover a popular and versatile C function: printf(). This exercise is a great
opportunity to improve your programming skills. It is of moderate difficulty.
You will discover variadic functions in C.
The key to a successful ft_printf is a well-structured and extensible code.

## Mandatory part

Write a library that contains ft_printf(), a
function that will mimic the original printf()

You have to recode the printf() function from libc.
The prototype of ft_printf() is:<br>
```
int ft_printf(const char *, ...);
```

Here are the requirements:
- Don’t implement the buffer management of the original printf().
- Your function will be compared against the original printf().
- You must use the command ar to create your library.
Using the libtool command is forbidden.
- Your libftprintf.a has to be created at the root of your repository.

You have to implement the following conversions:
- ``` %c ``` Prints a single character.
- ``` %s ``` Prints a string (as defined by the common C convention).
- ``` %p ``` The void * pointer argument has to be printed in hexadecimal format.
- ``` %d ``` Prints a decimal (base 10) number.
- ``` %i ``` Prints an integer in base 10.
- ``` %u ``` Prints an unsigned decimal (base 10) number.
- ``` %x ``` Prints a number in hexadecimal (base 16) lowercase format.
- ``` %X ``` Prints a number in hexadecimal (base 16) uppercase format.
- ``` %% ``` Prints a percent sign.

## Bonus part

- Manage any combination of the following flags: ’-0.’ and the field minimum width
under all conversions.
- Manage all the following flags: ’# +’ (Yes, one of them is a space)

