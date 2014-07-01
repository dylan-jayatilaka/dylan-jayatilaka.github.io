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


Now in quantum chemistry we often want to do integrals like this:

$$
\braopket{\mathscr{A}’ \Phi_I}{M}{\mathscr{A} \Phi_J}
=
\int
(\mathscr{A} \Phi_I)^*  M (\mathscr{A} \Phi_J) d\mathbf{x}_1\ldots\mathbf{x}_N
$$

The integration in this matrix element is over electronic coordinates
\\( \mathbf{x}_i \\) and the functions \\( \Phi_K \\) are usually *symmetric*
functions of those same coordinates. \\( M \\) is some kind of operator ---
perhaps a function of one or more of those coordinates, or derivatives of those
coordinates.

Such an integral is generically called a “matrix elements”.

The reason for that matrix elements are important is they allows to 
convert a partial differential equation, such as the Schrodinger equation,
into a matrix equation involving numbers. Matrix equations involving
numbers are much easier to solve in computers.

Look at the above matrix element. you can see that it involves products of two
antisymmetrizers. (It should be clear that these antisymmetrizers only “operate”
on the electron coordinates in the functions \\( \Phi_K \\) immediately to
their right). We need to be able to evaluate such products. We can use some
results from a previous post to obtain the required results.

## Matrix elemnts between determinant wavefunctions

The following theorem holds:

$$
\mathscr{A}’\Phi_I M \mathscr{A} \Phi_J = \Phi_I \sum_w^{N!} M \epsilon_w P_w \Phi_J
$$

The importance of this theorem is it allows to remove one of the antisymmetrizers
on the left, thus replacing a summation of \\( ()N!)^2 \\) terms into one involving
only \\( N! \\) permutations --- and these permutations only apply to the
function on the right. Note also that the \\( N! \\) has disappeared.

The proof is relatively easy an depends only on the group property of
permutations, especially that the left coset of the whole group is itself.
However, you don’t really need to know what a coset is to follow this proof.

$$
\begin{align}
\mathscr{A}’\Phi_I \mathscr{A} \Phi_J 
= &
(N!)^{-1}
\sum_v^{N!} \epsilon_v P_v \Phi_I
M
\sum_u^{N!} \epsilon_u P_u \Phi_J
\\
= &
(N!)^{-1}
\sum_v^{N!} P^{-1}_v P_v \Phi_I
M
\sum_u^{N!} (\epsilon_v\epsilon_u) (P^{-1}_v P_u) \Phi_J
\\
= &
(N!)^{-1}
\sum_v^{N!} \Phi_I
M
\sum_w^{N!} \epsilon_w P_w \Phi_J
\\
= &
Phi_I
M
\sum_w^{N!} \epsilon_w P_w \Phi_J
\end{align}
$$





