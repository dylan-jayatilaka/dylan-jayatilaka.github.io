---
layout: post
title: "Convert a one-electron into a two-electron term"
description: "Convert a one into two electron term"
category: articles
tags: [Matrix element, one-electron operator, two-electron operator]
modified: 201-06-07
image:
  feature: theodore-chasseriau-the-sisters.jpg
  credit: Theodore Chasseriau - The Two Sisters
  creditlink: http://upload.wikimedia.org/wikipedia/commons/7/79/Th%C3%A9odore_Chass%C3%A9riau_003.jpg
comments: false
share: true
---


In quantum chemistry the Hamiltonian is usually split into a
one-electron term and a two-electron term,

$$
\begin{align}
H & = h^{(1)} + h^{(2)}
\\
  & = \sum\sub{i=1}^N h(\B{x}\sub{i}) +
  \frac{1}{2}
  \sum\sub{i=1}^N 
  \sum\sub{\stackrel{j=1}{j\neq i}}^N v(\B{x}\sub{i},\B{x}\sub{j})
\end{align}
$$

It has always seemed to me a bit silly to do this, because the one-electron
term can be converted into a two-electron term by the following trick:

$$
h^{(1)} =
\frac{1}{N}
\sum\sub{i=1}^N \sum\sub{j=1}^N  \left( h(\B{x}\sub{i}) + h(\B{x}\sub{j}) \right).
$$

The sum is over all electrons \\( N \\). Now the one electron term has been
written as a two electron term, and it can be incorporated into the “normal”
two-electron term. The matrix elements of this “converted” one-electron term in
the atomic orbital basis are

$$
(\mu\nu|h^{(1)}|\kappa\lambda) =
  h\sub{\mu\nu} S\sub{\kappa\lambda}
+ S\sub{\mu\nu} h\sub{\kappa\lambda}.
$$

Here \\( \B{h} \\) and \\( \B{S} \\) are the usual core and overlap matrices,
respectively. It is easy to include them into the normal two electron
integrals, since these matrices are usually be stored in the memory of the
computer.

## When is the trick useful?

This trick becomes very useful when dealing with correlated methods.
In that case, we need to worry about one-electron matrix elements
at all, which considerably simplifies the equations. Also, the
terms pertaining to “single excitations” in the correlated methods
may effectively be combined with, or derived from, the “double excitations”.
Effectively, the correlated methods only need to worry about double
excitations. 


Pretty cool, huh?

## Caveat

Note: this does not help when you want to consider specific subterms
involving single excitations, as in the CCSD(T) theory. In that case,
using this trick, we would obtain these triples corrections as part
of the CCSD(Q) method. In view of the way that the one electron terms
actually “belong” to the two electron terms, perhaps this is actually
a theoretically more satisfactory theory---if not actually more practical.
