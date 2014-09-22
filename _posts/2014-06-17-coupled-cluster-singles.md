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

According to the previous notes the coupled cluster single (CCS) wavefunction 
has the form

$$
\Psi = (\exp T_1) \Phi
     = \exp \left( \sum_I^{N\sub{o}} \sum_A^{N\sub{v}} T_I^A \right) \Phi
$$

where the single excitation operator replaces spinorbital \\( I \\)
in determinant \\( \Phi \\) (an occupied) with an orbital
\\( A \\) which does not occur in \\( \Phi \\) (an unoccupied or virtual
spoinorbital) i.e.

$$
T_I^A \Phi = t_I^A \Phi_I^A.
$$

\\( t_I^A \\) is the amplitude associated with the singly
excited determinant \\( \Phi_I^A \\).

## The CCS wavefunction is just a determinent wavefunction

We can carry out further simplifications to the equations above:

$$
\begin{align}
\Psi & = \exp \left( \sum_I^{N\sub{o}} \sum_A^{N\sub{v}} T_I^A \right) \Phi \\
     & = \prod_I  \exp \left( \sum_I T_I^A \right) \Phi \\
     & = \prod_I \left( 1 + T_I^A + \frac{1}{2} (T_I^A)^2 + \ldots \right) \Phi \\
     & = \prod_I \left( 1 + t_I^A \Phi_I^A \right).
\end{align}
$$

The second and third lines follows from the definition of the exponential function.
The final line follows from the fact that

$$
(T_I^A)^2\Phi = (T_I^A)^3\Phi = \ldots = 0
$$

i.e. it is not possible to substitute spinorbital \\( I \\) more than once in
determinant \\( \Phi \\).

In fact, the final line can be written as an unnormalized single determinant
\\( \Phi’ \\) made from new spinorbitals \\( \phi’\sub{I} \\) like this,

$$
\begin{align}
\Phi’ & = \mathscr{A} \phi’\sub{1}       (\B{x}\sub{1}) \ldots
                      \phi’\sub{N\sub{e}}(\B{x}\sub{N\sub{e}}) \\
\phi’\sub{I}(\B{x}) & = \phi_I(\B{x}) + \sum_A t_I^A \phi_A(\B{x})
\end{align}
$$

(This follows from the column expansion rule for determinants)[http://en.wikipedia.org/wiki/Determinant].
Therefore the \\( T_1 \\) operator in the coupled cluster wavefunction
causes a mixture of unoccupied spinorbitals into the reference orbitals,

$$
\Psi = (\exp T_1) \Phi = \Phi’.
$$


## The CCS wavefunction for a HF reference has zero amplitudes



