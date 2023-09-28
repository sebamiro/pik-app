+++
title = "fract-ol"
template = "project.html"
weight = 3
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/fract-ol/">GitHub</a>

---

# Fract-ol

## Summary

Is an individual project about creating fractal exploration program in C

Fractals List:
- Mandelbrot
- Julia
- Burning ship
- Mandelbar
- Heart
- Buffalo
- Perpendicular mandelbrot
- Celtic mandelbrot
- Celtic mandelbar
- Perpendicular celtic

<img alt="fract-ol-image" src='../../fractol.png' >

## Introduction

The term fractal was first used by mathematician Benoit Mandelbrot in 1974. He based
it on the Latin word fractus which means "broken" or "fractured".

A fractal is an abstract mathematical object, like a curve or a surface, which pattern
remains the same at every scale.

Various natural phenomena – like the romanesco cabbage – have some fractal features.

It’s time for you to create a basic computer graphics project!

You are going to use the school graphical library: the MiniLibX! This library was
developed internally and includes basic necessary tools to open a window, create images
and deal with keyboard and mouse events.

This will be the opportunity for you to get familiar with the MiniLibX, to discover
or use the mathematical notion of complex numbers, to take a peek at the concept of
optimization in computer graphics and practice event handling

## Mandatory part

This project is about creating a small fractal
exploration program. First, you have to know what
a fractal is.

### Rendering

- Your program must offer the Julia set and the Mandelbrot set.
- The mouse wheel zooms in and out, almost infinitely (within the limits of the
computer). This is the very principle of fractals.
- You must be able to create different Julia sets by passing different parameters to
the program.
- A parameter is passed on the command line to define what type of fractal will be
displayed in a window.
  - You can handle more parameters to use them as rendering options.
  - If no parameter is provided, or if the parameter is invalid, the program displays
a list of available parameters and exits properly.
- You must use at least a few colors to show the depth of each fractal. It’s even
better if you hack away on psychedelic effects

### Graphic management

- Your program has to display the image in a window.
- The management of your window must remain smooth (changing to another win-
dow, minimizing, and so forth).
- Pressing ESC must close the window and quit the program in a clean way.
- Clicking on the cross on the window’s frame must close the window and quit the
program in a clean way.
- The use of the images of the MiniLibX is mandatory.

## Bonus part

You will get some extra points with the following features:
- One more different fractal (more than a hundred different types of fractals are
referenced online).
- The zoom follows the actual mouse position.
- In addition to the zoom: moving the view by pressing the arrows keys.
- Make the color range shift.


