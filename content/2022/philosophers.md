+++
title = "philosophers"
template = "project.html"
weight = 6
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/philosophers42">GitHub</a>

---

# Philosophers

## Summary

Is an individual project about a classic problem in concurrent programming that
involves simulating a scenario where a group of philosophers sits around a table,
and each philosopher alternates between thinking, eating and sleeping.
The philosophers are represented as concurrent threads or processes, and they
interact with shared resources (forks) to eat, implementing synchronization mechanisms
to prevent conflicts and ensure proper resource sharing as mutex locks and semaphores
are used to avoid data races.

```
pthread_mutex_lock(&table->philo[philo->left_index].fork);
state(philo, FORK);
pthread_mutex_lock(&table->philo[philo->rigth_index].fork);
state(philo, FORK);
pthread_mutex_lock(&table->eat_check);
state(philo, EAT);
(philo->times_ate)++;
philo->last_eat = get_time();
pthread_mutex_unlock(&table->eat_check);
ft_sleep(table->time_to_eat);
pthread_mutex_unlock(&table->philo[philo->left_index].fork);
pthread_mutex_unlock(&table->philo[philo->rigth_index].fork);
```

## Introduction 

In this project, you will learn the basics of threading a process.
You will see how to create threads and you will discover mutexes.

Here are the things you need to know if you want to succeed this assignment:
- One or more philosophers sit at a round table.
There is a large bowl of spaghetti in the middle of the table.
- The philosophers alternatively eat, think, or sleep.
While they are eating, they are not thinking nor sleeping;
while thinking, they are not eating nor sleeping;
and, of course, while sleeping, they are not eating nor thinking.
- There are also forks on the table. There are as many forks as philosophers.
- Because serving and eating spaghetti with only one fork is very inconvenient, a
philosopher takes their right and their left forks to eat, one in each hand.
- When a philosopher has finished eating, they put their forks back on the table and
start sleeping. Once awake, they start thinking again. The simulation stops when
a philosopher dies of starvation.
- Every philosopher needs to eat and should never starve.
- Philosophers don’t speak with each other.
- Philosophers don’t know if another philosopher is about to die.
- No need to say that philosophers should avoid dying!

## Mandatory part

Philosophers with threads and mutexes

- Each philosopher should be a thread.
- There is one fork between each pair of philosophers. Therefore, if there are several
philosophers, each philosopher has a fork on their left side and a fork on their right
side. If there is only one philosopher, there should be only one fork on the table.
- To prevent philosophers from duplicating forks, you should protect the forks state
with a mutex for each of them.

## Bonus part

Philosophers with processes and semaphores

The specific rules for the bonus part are:
- All the forks are put in the middle of the table.
- They have no states in memory but the number of available forks is represented by
a semaphore.
- Each philosopher should be a process. But the main process should not be a
philosopher.
