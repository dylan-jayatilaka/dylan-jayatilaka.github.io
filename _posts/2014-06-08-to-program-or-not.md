---
layout: post
title: "To program or not"
description: "To program or not --- and how"
category: articles
tags: [Programming, understanding, philosophy, naming, specification, clarity, software life cycle, maintenance]
modified: 201-06-07
image:
  feature: so-simple-sample-image-3.jpg
  credit: Michael Rose
  creditlink: http://mademistakes.com
comments: false
share: true
---

Doing quantum chemistry or quantum crystallography means doing calculations.

That leaves you with two choices: 
1. Use some else’s program, or 
2. Write your own.

Here I argue that you should write your own.

## Why write programs?

If you don’t write your own programs, you are obliged to trust that the program
you use is correct. That by itself is not a problem: you may after all only be
interested in the answer, and what that answer can reveal about some other
bigger question.

But what if something goes wrong? After all, scientific calculations are
usually complex. 

Then it helps to know something about how the methods works --- how the program
works --- so you can know program limitations and can work around them.

More importantly, everyone needs to know about how *accurate* their calculated
answer is. In this case, knowing *something* about the algorithm implementation
is essential --- even if you don’t know all the details.

## Understanding

So: you are a scientist and you want to write a moderately complex program to
do a quantum chemical calculation. How do you start?

Let’s assume you have done the obvious and learned to program in a suitable 
language for scientific programming. Fortran, C, Java or python. And let’s
assume you’ve read the books and know the theory. Now what?

The key step is to *understand* what you want to do.

But what is **understanding**?

For me it means:

1. *Giving meaningful names to things* so that you can refer to
   those things by name when explaining things or --- in our case --- writing
   down the algorithms or equations, deriving such equations if necessary. I
   won’t pursue this aspect further: that is the province of textbooks. What I
   want to talk about here is what is **not** in the textbooks. So let’s assume
   that you have a meaningful set of names, you have these names associated
   with some equations which determine your calculation.

2. If the equations are complicated, in order to program them, you need a plan.
   You need to structure intermediate results in a way that is both *easy to
   understand* and *efficient to compute*.

Let’s discuss these points in more detail.

## [Call a spade a spade](http://en.wikipedia.org/wiki/To_call_a_spade_a_spade)

Naming entities meaningfully is by far the most important and difficult part of
the programming process.

Your disbelief is audible.

You say: surely understanding the quantum theory is more difficult?

I say: that is the *same thing*.

Think about it. 

Naming something properly is the start of how you *think* about that thing.
Naming and understanding go together like hand and glove: you simply can’t
think about something clearly unless it is at least named properly. This goes
for quantum theory, programming, and conversation.

Imagine calling a cup a bowl. Now imagine doing the equivalent when  writing a
programs. Clearly, names are, or should be, even more important in this
context. To wit, imagine calling a heavily used variable `v` when it holds the
position coordinate and the velocity by variable `x`. Imagine naming a variable
holding the momentum of partice 1 `l2`. What a disaster! Yet this is *exactly*
what happens in much scientific software.

If you think I am joking about this just read wikipedia about the 
[software development process](http://en.wikipedia.org/wiki/Software_development_process). 
You will learn that the first step is the “specification”. In fact, it is dogma
in software engineering to “write the documentation first” before doing any
kind of programming. Clearly that dogma is nothing but a formalization of the
naming-thinking process, whereby the unknown objects needed in an algorithm are
formally described in text, and described in sufficient detail to permit code
to be written down. Unfortunately, the writing of documentation *before* coding
is rarely undertaken by any scientific programmer.

## Efficiency versus clarity

Now to the second point.

Begin with the realization that the objectives of efficiency and clarity are
largely but not completely independent. Generally speaking it *is* harder to
write a efficient program in a clear way because it may have to take advantage
of special machine characteristics.

Of the two characeristics **clarity is much more important**. That is
because a clear code is easier to understand. Furthermore, a clearly written
code has benefits later down the track, such as:

* **Better bug detection and reduced maintenance**. Perhaps later you will
  actually recall and understand what you did.

* **Better opportunities for optimization and code evolution** by changing
  algorithms. Generally speaking the greatest gains in efficiency occur due to
  the use of *new algorithms* rather than optimization of the instructions of
  computer codes to take advantage of hardware.

* **Greater chance of collaboration and sharing workload**, since an unclear
  code is unlikely to be adopted as the basis of a future work by you or
  anyone else. It is worth keeping in mind the fact that the vast amount of
  effort spent on a program occurs in maintenance and code evolution.

## What next?

If you are convinced by the above arguments, we should pay attention to best
practice in software engineering. In computer science there are two broad approaches
to creating creating well-structured code:

* Object-oriented methods

* Functional programming methods

We would do well to understand the essence of these approaches, but that is for
another time.

