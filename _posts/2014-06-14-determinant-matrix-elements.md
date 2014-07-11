---
layout: post
title: "Determinant matrix elements"
description: "Matrix elements of many-electron operators between determinant wavefunctions"
category: articles
tags: [Matrix element, determinant, one-electron operator, two-electron operator]
modified: 201-06-07
image:
  feature: samuel-monnier-patternmond.jpg
  credit: Samuel Monnier
  creditlink: http://www.algorithmic-worlds.net/blog/blog.php?Post=20110201
comments: false
share: true
---


In quantum chemistry we often want to do integrals like this:

$$
\braopket{\mathscr{A} \Phi_I}{M}{\mathscr{A} \Phi_J}
=
\int
(\mathscr{A} \Phi_I)^\star  M (\mathscr{A} \Phi_J) \, d\B{x}
$$

This integral is generically called a “matrix element”, and specifically
it is a “determinant matrix element”.

The integration in this matrix element is over electronic coordinates
The functions \\( \Phi_K = \phi\sub{k_1}(\B{x_1})\ldots\phi(\B{x}\sub{N}) \\)
are Hartree orbital products.
\\( M \\) is some kind of operator --- perhaps a function of one or more of
those coordinates, or derivatives of those coordinates --- which importantly
is symmetric in the electron coordinates, since all electrons are indistinguishable.
(Read [here](http://dylan-jayatilaka.net/articles/the-determinant-wavefunction)
  and [here](http://dylan-jayatilaka.net/articles/the-antisymmetrizer) to know more).

Now you can see that the determinant matrix element above involves products of
two antisymmetrizers \\( \mathscr{A} \\). The parentheses make clear that these
antisymmetrizers only “operate” on the electron coordinates in the functions
\\( \Phi_K \\) immediately to their right.

## Why are (determinant) matrix elements important?

The reason for that matrix elements are important is they allows to
convert a partial differential equation, such as the Schrodinger equation,
into a matrix equation involving numbers. Matrix equations involving
numbers are much easier to solve on computers.

The reason for that determinant matrix elements are important is that
a determinant is the simplest reasonable model wavefunction for a
group of electrons.

Clearly, we need to be able to work out or simplify this matrix element
in order to do numerical calculations.

## Matrix elements between determinant wavefunctions

Luckily we can use
[previous results](http://dylan-jayatilaka.net/articles/the-antisymmetrizer)
showing that the antisymmetrizeris hermitian, and that a product of two
antisymmetrizers is idempotent i.e.

$$
\begin{align}
\braopket{\mathscr{A} \Phi_I}{M}{\mathscr{A} \Phi_J}
= &
\braket{\Phi_I}{\mathscr{A} M \mathscr{A} \Phi_J}
&&
\s{$\mathscr{A}$ is hermitian}
\\
= &
\braket{\Phi_I}{M \mathscr{A}^2 \Phi_J}
&&
\s{$M$ is symmetric}
\\
= &
\sqrt{N!}
\braket{\Phi_I}{M \mathscr{A} \Phi_J}
&&
\s{$\mathscr{A}$ is nearly idempotent}
\\
= &
\int \Phi_I(\B{x})^\star\,{M}\,\left(\sum_u \epsilon_u P_u \Phi_J(\B{x})\right)\,d\B{x}
\end{align}
$$

To make further progress we need to make certain assumptions about the
operator \\( M \\).




