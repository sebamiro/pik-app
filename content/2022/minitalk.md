+++
title = "minitalk"
template = "project.html"
weight = 5
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/minitalk42/">GitHub</a>

---

# Minitalk

## Summary

Is an individual project about a small client-server comunication program
through UNIX signals. It's mandatory to use just SIGUSR1 and SIGUSR2 (user defined signals),
so the client program must send the text as a binary message, and the server
keeps a buffer to store the received characters until the complete message is received,
then the server prints it out.

```
void
sendchar(int pid, char c)
{
	int	i = 0;
	int	signal = 0;

	while (i < 8)
	{
		if (c & 128)
			signal = SIGUSR1;
		else
			signal = SIGUSR2;
		if (kill(pid, signal))
			exit(1);
		usleep(100);
		i++;
		c <<= 1;
	}
}
```

## Introduction

The purpose of this project is to code a small data exchange program
using UNIX signals.

## Mandatory Part

You must create a communication program in the form of a client and a server.
- The server must be started first. After its launch, it has to print its PID.
- The client takes two parameters:
  - The server PID.
  - The string to send.
- The client must send the string passed as a parameter to the server.
Once the string has been received, the server must print it.
- The server has to display the string pretty quickly. Quickly means that if you think
it takes too long, then it is probably too long.
- Your server should be able to receive strings from several clients in a row without
needing to restart.
- The communication between your client and your server has to be done only using
UNIX signals.
- You can only use these two signals: SIGUSR1 and SIGUSR2

## Bonus part

Bonus list:
- The server acknowledges every message received by sending back a signal to the
client.
- Unicode characters support!
