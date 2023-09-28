+++
title = "minishell"
template = "project.html"
weight = 7
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/Minishell">GitHub</a>

---

# Minishell

## Summary

Is an group project about creating a basic shell program that allows users
to execute commands, this includes running external programs, built-in commands,
and handling command-line arguments, manage processes, and handle basic shell functionalities as:
- Environment variables, allowing users to set, unset, and modify variables.
- Input/Output redirection, allowing users to redirect the standard input and
  output of commands to files or other commands.
- Pipes (| character), the output of each command in the pipeline is
  connected to the input of the next command via a pipe.

```
int
ft_echo(t_cmd **cmd)
{
	int	i = 0;
	bool n_flag = false;

	if (!(*cmd)->arg && write(1, "\n", 1))
		return (0);
	while ((*cmd)->arg[i] && is_n_flag((*cmd)->arg[i])) {
		n_flag = true;
		i++;
	}
	while ((*cmd)->arg[i]) {
		putstr((*cmd)->arg[i]);
		if ((*cmd)->arg[i])
			write(1, " ", 1);
		i++;
	}
	if (!n_flag)
		write(1, "\n", 1);
	return (0);
}
```

## Introduction

The existence of shells is linked to the very existence of IT.

At the time, all developers agreed that communicating with a computer using aligned
1/0 switches was seriously irritating.

It was only logical that they came up with the idea of creating a software to com-
municate with a computer using interactive lines of commands in a language somewhat
close to the human language.

Thanks to Minishell, you’ll be able to travel through time and come back to problems
people faced when Windows didn’t exist.

## Mandatory part

Write a shell that:

- Display a prompt when waiting for a new command.
- Have a working history.
- Search and launch the right executable (based on the PATH variable or using a
relative or an absolute path).
- Avoid using more than one global variable to indicate a received signal. Consider
the implications: this approach ensures that your signal handler will not access your
main data structures.
- Not interpret unclosed quotes or special characters which are not required by the
subject such as \ (backslash) or ; (semicolon).
- Handle ’ (single quote) which should prevent the shell from interpreting the meta-
characters in the quoted sequence.
- Handle " (double quote) which should prevent the shell from interpreting the meta-
characters in the quoted sequence except for $ (dollar sign).
- Implement redirections:
  - < should redirect input.
  - \> should redirect output.
  - << should be given a delimiter, then read the input until a line containing the
delimiter is seen. However, it doesn’t have to update the history!
  - \>\> should redirect output in append mode.
- Implement pipes (| character). The output of each command in the pipeline is
connected to the input of the next command via a pipe.
- Handle environment variables ($ followed by a sequence of characters) which
should expand to their values.
- Handle $? which should expand to the exit status of the most recently executed
foreground pipeline.
- Handle ctrl-C, ctrl-D and ctrl-\ which should behave like in bash.
- In interactive mode:
  - ctrl-C displays a new prompt on a new line.
  - ctrl-D exits the shell.
  - ctrl-\ does nothing.
- Your shell must implement the following builtins:
  - echo with option -n
  - cd with only a relative or absolute path
  - pwd with no options
  - export with no options
  - unset with no options
  - env with no options or arguments
  - exit with no options

## Bonus part

Your program has to implement:
- && and || with parenthesis for priorities.
- Wildcards * should work for the current working directory.

