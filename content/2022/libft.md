+++
title = "libft"
template = "project.html"
weight = 0
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/libft42/">GitHub</a>

-----------

# Libft

## Summary 

Is an individual project that requieres to create a C library for future projects,
it has some re-implemented standard C functions, and other non-standar functions.
We get a deeper understanding of data structures and basic algorithms. During the
cursus we are only allowed to use functions that we have programed, so we have to
keep growing this libary with anything we would find useful.

```
char*
ft_strjoin(const char *s1, const char *s2)
{
	size_t	total;
	char	*str;

	total = ft_strlen(s1) + ft_strlen(s2) + 1;
	str = ft_calloc(total, 1);
	if (!str)
		return (NULL);
	ft_strlcat(str, s1, total);
	ft_strlcat(str, s2, total);
	return (str);
}
```

## Introduction

C programming can be very tedious when one doesn’t have access to the highly useful
standard functions. This project is about understanding the way these functions work,
implementing and learning to use them. Your will create your own library. It will be
helpful since you will use it in your next C school assignments.
Take the time to expand your libft throughout the year. However, when working
on a new project, don’t forget to ensure the functions used in your library are allowed in
the project guidelines

## Mandatory part

Write your own library: a collection of functions
that will be a useful tool for your cursus.

### Technical considerations

- Declaring global variables is forbidden.
-  If you need helper functions to split a more complex function, define them as static
functions. This way, their scope will be limited to the appropriate file.
- Place all your files at the root of your repository.
- Turning in unused files is forbidden.
- Every .c files must compile with the flags -Wall -Wextra -Werror.
- You must use the command ar to create your library. Using the libtool command
is forbidden.
- Your libft.a has to be created at the root of your repository.

### Libc function

To begin, you must redo a set of functions from the libc. Your functions will have the
same prototypes and implement the same behaviors as the originals. They must comply
with the way they are defined in their man. The only difference will be their names. They
will begin with the ’ft_’ prefix. For instance, strlen becomes ft_strlen.

### Additional function

In this second part, you must develop a set of functions that are either not in the libc,
or that are part of it but in a different form.

## Bonus part

If you completed the mandatory part, do not hesitate to go further by doing this extra
one. It will bring bonus points if passed successfully.
Functions to manipulate memory and strings is very useful. But you will soon discover
that manipulating lists is even more useful.

-----------

Libc functions | Additional functions | Bonus Functions
:----------- | :----------- | :-----------
memset		| ft_memalloc	| ft_lstnew		 
bzero		| ft_memdel		| ft_lstdelone	
memcpy		| ft_strnew		| ft_lstdel	
memccpy		| ft_strdel		| ft_lstadd
memmove		| ft_strclr		| ft_lstiter	
memchr		| ft_striter	| ft_lstmap	
memcmp		| ft_striteri	|		
strlen		| ft_strmap		|	
strdup		| ft_strmapi	|
strcpy		| ft_strequ		|				
strncpy		| ft_strnequ	|			
strcat		| ft_strsub		| 
strlcat		| ft_strjoin	|
strchr		| ft_strtrim	| 
strrchr		| ft_strsplit	|
strstr		| ft_itoa		| 
strnstr		| ft_putchar	| 
strcmp		| ft_putstr		| 
strncmp		| ft_putendl	| 
atoi		| ft_putnbr		| 
isalpha		| ft_putchar_fd	| 
isdigit		| ft_putstr_fd	| 
isalnum		| ft_putendl_fd	| 
isascii		| ft_putnbr_fd	| 
isprint		|| 
toupper		| |
tolower		| |
