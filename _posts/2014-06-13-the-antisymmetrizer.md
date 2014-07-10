---
layout: post
title: "The antisymmetrizer"
description: "The antisymmetrizer operator"
category: articles
tags: [antisymmetrizer, permutations, pauli principle, wavefunction, determinant]
modified: 201-06-07
image:
  feature: rene-magritte-decalcomania.jpg
  credit: Rene Magritte - Decalcomania
  creditlink: http://www.algorithmic-worlds.net/blog/blog.php?Post=20110201
comments: false
share: true
---

In this post the  _antisymmetrizer operator_ is officially defined.

Those who read the
[determinant wavefunctions post](http://dylan-jayatilaka/articles/the-determinant-wavefunction)
will already be familiar with this operator.

I discuss it again here in order to describe more of it’s properties, which are
important for evaluating many-electron integrals. Such integrals form the
bread-and-butter of quantum chemistry --- so knowing about the antisymmetrizer
is important.

More important for me is that the “antisymmetric” nature of electrons is one of
the puzzling and amazing things about quantum mechanics itself. It’s just so
cool and weird!

## The antisymmetrizer

The antisymmetrizer is so-called because when it is applied to an arbitrary
function of labelled arguments, that function is changed into a new function
which changes sign whenever those arguments are swapped.

The antisymmetrizer operator is defined by

$$
\mathscr{A}
=
\frac{1}{\sqrt{N!}} \sum_u^{N!} \epsilon_u P_u
$$

Notes:

- The sum is over all permutations \\( u \\) of a set of integers
  \\( \{ 1, \ldots, N \} \\).

- \\( P_u \\) is an operator which permutes those integer labels in any
  expression which follows. For example, \\( P_u \\) might be the elementary
  permutation \\( (1 2) \\) which swaps labels 1 and 2, although there
  may be more complicated permutations such as the cycle \\( (1 2 3) \\).
  See wikpedia [here](http://en.wikipedia.org/wiki/Permutation)
  for more information.

-  The number of terms in the summation is \\( N! \\).

- \\( \epsilon_u \\) is a number which is either +1 or -1 called the
  _signature_, _sign_ or _paity_ of the permutation \\( P_u \\). It
  is +1 (or -1) if \\( P_u \\) can be decomposed into a sequence of even
  (rrespectively, odd) elementary permutations or _swaps_ . It is _not_ at all
  obvious that any permutation may be decomposed as either even or odd.
  If you are interested, several proofs of this fact are given in
  [wikipedia](http://en.wikipedia.org/wiki/Parity_of_a_permutation).
  The quantity \\( \epsilon_u \\) is also called the
  [Levi-Civita symbol](http://en.wikipedia.org/wiki/Levi-Civita_symbol)
  which may be familiar to some of you.

## Making functions antisymmetric

We have the following theorem:

The function \\( F(\B{x}_1 \ldots \B{x}_n) = \mathscr{A}\, f(\B{x}_1 \ldots \B{x}_n) \\)
is antisymmetric, i.e.

$$
   F(\ldots \B{x}_j \ldots \B{x}_i \dots)
= -F(\ldots \B{x}_i \ldots \B{x}_j \dots)
\ \ \mbox{for } i<j<N.
$$

Proof:

$$
\begin{align}
F(\ldots, \B{x}_j \ldots \B{x}_i \dots)
= & P_{(i j)} F \\
= & P_{(i j)} \frac{1}{\sqrt{N!}} \sum_u^{N!} \epsilon_u P_u f \\
= & \frac{1}{\sqrt{N!}} \sum_u^{N!} \epsilon_u P_{(i j)} P_u f \\
= & \frac{1}{\sqrt{N!}} \sum_v^{N!} (-\epsilon_u) P_v f \ \ \mbox{where } P_v = P_{(i j)} P_u \\
= & - F
\end{align}
$$

Remarks: The only tricky part is the penultimate line. There, we used two
facts. First, that the product of two permutations is another permutation 
\\( P_v\\). This should be obvious, but actually follows from the fact that
permutations form a [mathematical group](http://en.wikipedia.org/wiki/Group_(mathematics)). 
Second, since \\( P_v \\) has one extra swap compared to \\( P_u \\) its
signature \\( \epsilon_v = -\epsilon_u \\).

We have shown that the antisymmetrizer \\( \mathscr{A} \\) makes any function
which it is applied to antisymmetric.

## The antisymmetrizer makes determinant wavefunctions

If you read the 
[previous post](http://dylan-jayatilaka/articles/the-detereminant-wavefunction)
you will see that the antisymmetrizer makes determinant wavefunctions:

$$
\mathscr{A}\phi_1(\B{x}_1)\ldots\phi_N(\B{x}_N)
=
\frac{1}{\sqrt{N!}}
\textrm{det}\,
\left|
\begin{array}{lll}
\phi_1(\textrm{x}_1)          & \ldots & \phi_1(\textbf{x}_N) \\
\vdots                        & \ddots & \vdots          \\
\phi_N(\textrm{x}_1) & \ldots & \phi_N(\textrm{x}_N)
\end{array}
\right|.
$$

## The antisymmetrizer is Hermitian

The antisymmetrizer is Hermitian if \\( \mathscr{A}^\dagger = \mathscr{A} \\),
which means that for any functions \\( \Phi_I \\) and \\( \Phi_J \\)
that these operators are allowed to “act” on we must have

$$
\braket{\Phi_I}{\mathscr{A}^\dagger\, \Phi_J}
\equiv
\braket{\mathscr{A}\, \Phi_I}{\Phi_J}
=
\braket{\Phi_I}{\mathscr{A}\, \Phi_J}.
$$

Proof:

$$
\begin{align}
\braket{\mathscr{A}\Phi_I}{\Phi_J}
= &
\int
(\mathscr{A} \Phi_I)^* \Phi_J d\B{x}
&& \s{by definition}
\\
= &
\int
(\mathscr{A} \Phi_I^*) \Phi_J d\B{x}
&& \s{$\mathscr{A}$ unaffected by conjugation}
\\
= &
\frac{1}{\sqrt{N!}}
\sum_u^{N!} \epsilon_u
\int
(P_u \Phi_I^*(\B{x})) \Phi_J(\B{x}) d\B{x}
&& \s{ substitute $\mathscr{A}$ definition}
\\
= &
\frac{1}{\sqrt{N!}}
\sum_u^{N!} \epsilon_u
\int
\Phi_I^*(\B{y}) (P_u^{-1} \Phi_J(\B{y}) d\B{y})
&& \s{substitute $\B{y} = P_u \B{x}$}
\\
= &
\frac{1}{\sqrt{N!}}
\sum_u^{N!} \epsilon_u
\int
\Phi_I^* (P_u^{-1} \Phi_J) d\B{y}
&& \s{$d\B{y}= d\B{y}_1 \ldots d\B{y}_N$ is symmetric}
\\
= &
\frac{1}{\sqrt{N!}}
\sum_w^{N!} \epsilon_w
\int
\Phi_I^* (P_w \Phi_J) d\B{y}
&& \s{substiute $P_w=P_u^{-1}$; and $\epsilon_w=\epsilon_u$}
\\
= &
\braket{\Phi_I}{\mathscr{A}\, \Phi_J}
&& \
\end{align}
$$

Remark: In an \\( M \\)-dimensional *finite* dimensional space
\\( V = \mbox{span}\, (\Phi_I ; I=1,\ldots,M) \\) the adjoint
\\( \mathscr{A}^\dagger \\) is also called the “hermitian conjugate”.
In quantum chemistry we usually deal with finite dimensional spaces, so
the terms “self-adjoint” and “hermitian” are equivalent. To be honest
I am no sure of the relevance of infinite dimensional spaces
in any practical calculation.

## Antisymmetrizers are (nearly) idempotent

The following theorem holds:

$$
\mathscr{A}^2 = \sqrt{N!} \mathscr{A}
$$

In other words, antisymmetrizing a function which is already antisymmetric
doesn’t change it from being antisymmetric (except for a factor).

Note: An operators which obeys \\( P^2 = P \\) is called an *idempotent* or
*projection* operator. In our case \\( (1/\sqrt{N!}) \mathscr{A} \\) would be
idempotent.

Proof:

$$
\begin{align}
\mathscr{A}^2
= &
\frac{1}{N!}
(\sum_u^{N!} \epsilon_u P_u)
(\sum_v^{N!} \epsilon_v P_v)
&&
\s{ substitute $\mathscr{A}$ definitions}
\\
= &
\frac{1}{N!}
\sum_u^{N!}
\sum_v^{N!}
(\epsilon_u \epsilon_v) (P_u P_v)
&&
\
\\
= &
\frac{1}{N!}
\sum_u^{N!}
\sum_w^{N!} \epsilon_w P_w
&&
\s{ substitute $P_w = P_u P_v$ for fixed $u$}
\\
= &
\frac{\sqrt{N!}}{N!}
\sum_u^{N!} \mathscr{A}
&&
\
\\
= &
\sqrt{N!} \mathscr{A}
&&
\s{constant sum $u$ gives factor $N!$}
\end{align}
$$






