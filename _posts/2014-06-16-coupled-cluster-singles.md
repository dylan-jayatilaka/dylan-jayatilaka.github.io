---
layout: post
title: "Coupled cluster singles"
description: "Coupled cluster singles wavefunction"
category: articles
tags: [Coupled cluster, singel excitation, Hartree-Fock]
modified: 201-06-07
image:
  feature: regina-valluzzi-transition-to-chaos.jpg
  credit: Regina Valluzzi - Transition to Chaos
  creditlink: http://nerdlypainter.blogspot.com.au/2011/03/archive-february-newsletter-featuring.html
comments: false
---

The coupled cluster single (CCS) wavefunction has the form

$$
\begin{align}
\Psi & = e^{T_1} \Phi \\
     & = e^{\sum_I^{N\sub{o}} \sum_A^{N\sub{v}} T_I^A ) \Phi \\
     & = \prod_I  e^{\sum_I T_I^A ) \Phi \\
     & = \prod_I (1 + T_I^A\Phi_I^A).
$$

Here we have introduced the single excitation operator \\( T_I^A \\)
which is defined by \\( \sum_I^{N\sub{o}} \sum_A^{N\sub{v}} \\).

## The CCS wavefunction is just a determinent wavefunction

We can carry out further simplifications to the equations above:

$$
\begin{align}
\Psi & = e^{\sum_I^{N\sub{o}} \sum_A^{N\sub{v}} T_I^A ) \Phi \\
     & = \prod_I  e^{\sum_I T_I^A ) \Phi \\
     & = \prod_I (1 + T_I^A\Phi_I^A).
$$

The second line follows from the properties of the exponential function.

The final line follows from the fact that \\( (\sum_I T_I^A)^2 = 0) i.e.
it is not possible to substitute spinorbital \\( I \\) more than once.

In fact, the final line can be written as an (unnormalized) single determinant
\\( \Phi’ \\) made from new spinorbitals \\( phi’\sub{I} \\) like this,

$$
\begin{align}
\Phi’ & = \mathscr{A} \phi’\sub{1}       (\B{x}\sub{1}) \ldots
                    \phi’\sub{N\sub{e}}(\B{x}\sub{N\sub{e}}) \\
\phi’\sub{I} & = \sum_A t_I^A
\end{align}
$$

Therefore the \\( T_1 \\) operator in the coupled cluster wavefunction
causes a mixture of unoccupied spinorbitals into the reference orbitals.


## The CCS wavefunction for a HF reference has zero amplitudes



