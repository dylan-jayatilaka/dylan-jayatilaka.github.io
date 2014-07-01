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

Those who have read the post on [determinant
wavefunctions](https://dylan.jayatilaka.net/) will be familiar with this
operator. 

The reason to discuss it is to describe some of it’s properties which are
important for evaluating many-electron integrals. Such integrals form the
bread-and-butter of quantum chemistry --- so knowing about the antisymmetrizer
is important.

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

* The sum is over all permutations \\( u \\) of a set of integers
  \\( \{ 1, \ldots, N \} \\).

* \\( P_u \\) is an operator which permutes those integer labels in any
  expression which follows. For example, \\( P_u \\) might be the elementary
  permutation \\( (1 2) \\) which swaps labels 1 and 2, although there
  may be more complicated permutations such as the cycle \\( (1 2 3) \\).
  See wikpedia [here](http://en.wikipedia.org/wiki/Permutation)
  for more information. 

*  The number of terms in the summation is \\( N! \\).

* \\( \epsilon_u \\) is a number which is either +1 or -1 called the
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

Suppose we have an arbitrary function \\( f(\B{x}_1,\ldots,\B{x}_n) \\). 
Then the function

$$
F(\B{x}_1 \ldots \B{x}_n)
=
\mathscr{A}\, 
f(\B{x}_1 \ldots \B{x}_n)
$$

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
facts. First, that the product of two permutations is another permutation \\(
P_v \\). This should be obvious, but actually follows from the fact that
permutations form a [mathematical group](). Second, since \\( P_v \\) has one
extra swap compared to \\( P_u \\) its signature 
\\( \epsilon_v = -\epsilon_u \\).

We have shown that the antisymmetrizer \\( \mathscr{A} \\) makes any function
which it is applied to antisymmetric.

## The antisymmetrizer is Hermitian

The antisymmetrizer is Hermitian if

$$
\braket{\Phi_I}{\mathscr{A}^\dagger\, \Phi_J}
\equiv
\braket{\mathscr{A}\, \Phi_I}{\Phi_J}
=
\braket{\Phi_I}{\mathscr{A}\, \Phi_J}
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
&& \s{variable substitution $\B{y} = P_u \B{x}$}
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

Remark: In an \( N_D \\)-dimensional finite dimensional space
\\( V = \mbox{span}\, (\Phi_I ; I=1,\ldots,M) \\) the adjoint
\\( \mathscr{A}^\dagger \\) is also called the “hermitian conjugate”.
In quantum chemistry we usually deal with finite dimensional spaces, so 
the terms “self-adjoint” and “hermitian” are equivalent.

## Antisymmetrizers are (nearly) idempotent

The following theorem holds:

$$
\mathscr{A}^2 = \sqrt{N!} \mathscr{A}
$$

Proof:





