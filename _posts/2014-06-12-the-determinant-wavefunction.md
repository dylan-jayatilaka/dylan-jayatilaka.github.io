---
layout: post
title: "The determinant wavefunction and identical particles"
description: "The single determinant wavefunction is discussed"
category: articles
tags: [wavefunction, determinant, Hartree-Fock, DFT]
modified: 2014-11-04
image:
  feature: samuel-monnier-patternmond.jpg
  credit: Samuel Monnier
  creditlink: http://www.algorithmic-worlds.net/blog/blog.php?Post=20110201
comments: false
share: true
---

This article explains how the Pauli principle evolves naturally to
the idea of a single determinant wavefunction and how that it turn
comes from the idea of identical particles.

## Pauli principle

The Pauli principle states that when the coordinates of *any* pair of electrons
is swapped the sign of the wavefunction is reversed,

$$
 \Psi(\textbf{x}_1 \ldots
      \textbf{x}_i \ldots
      \textbf{x}_j \ldots
      \textbf{x}_N)
=
-\Psi(\textbf{x}_1 \ldots
      \textbf{x}_j \ldots
      \textbf{x}_i \ldots
      \textbf{x}_N)
$$

Pauli proved from relativistic quantum mechanics that this property holds for
*any* set of identical *fermions* i.e. any particle with half-integer spin.
He also showed that for identical *bosons* -- particles with integer spin --
swapping the coordinates does *not* change the sign pf the wavefunction.

## Why is Pauli’s principle true?

The real reason is not well understood: the famous physicist Richard Feynman
certainly thought so.

However, it **is** easy to **rationalize** the Pauli principle. Keep reading.

As you know, the probability of finding two particles at positions
\\( \B{x}\sub{1} \\) and \\( \B{x}\sub{2} \\) is given by

$$
P(\B{x}\sub{1},\B{x}\sub{2}) = |\Psi(\B{x}\sub{1},\B{x}\sub{2})|^2
$$

Now suppose the particles are identical. Then, if we swap their positions, we
will not be able to tell that anything has happened. Therefore we expect
that reversing the positions for identical particles leads to the *same* 
probability,

$$
\begin{align}
P(\B{x}\sub{1},\B{x}\sub{2}) &= P(\B{x}\sub{2},\B{x}\sub{1}) \\
\textrm{i.e.} \ |\Psi(\B{x}\sub{2},\B{x}\sub{1})|^2 &= |\Psi(\B{x}\sub{1},\B{x}\sub{2})|^2.
\end{align}
$$

Naively, the above equation has two solutions:

$$
\Psi(\B{x}\sub{2},\B{x}\sub{1}) = \pm\Psi(\B{x}\sub{1},\B{x}\sub{2}).
$$

The solution with the negative sign corresponds to fermions, while the positive
sign corresponds to bosons. It is not too difficult to polish up this argument
properly by introducing a Hermitian “coordinate swap” operator. Proving that
the signs are related to spin is much harder.


## Hartree's orbital-product wavefunction

The simplest wavefunction we can think of is Hartree's orbital-product
wavefunction

$$
\Phi(\textbf{x}_1 \ldots
     \textbf{x}_N)
=
\phi_1(\textbf{x}_1) \ldots
\phi_N(\textbf{x}_N)
$$

Think of this as wavefunction representing electron 1 in orbital
\\( \phi_1 \\), electron 2 in orbital \\( \phi_2 \\), and so on
for all \\( N \\) particles.
Note: if we swap coordinates \\( \textbf{x}_i \\) and
\\( \textbf{x}_j \\) in the above product, it is the same as leaving the
coordinates unchanged but swapping the functions \\( \phi_i \\) and
\\( \phi_j \\). So we see that after the swap we we will not have the same
wavefunction --- the electrons will be in different orbitals. So the
wavefunction is not the same --- let alone obey the Pauli principle where
the wavefunction is supposed to be the same except for sign reversal.

How can we make a wavefunction which satisfies the Pauli principle?

Let's make the problem a bit easier. Suppose we wanted a wavefunction
where swapping electrons led to *no* change. How to achieve that?

## Symmetric orbital-product wavefunction

One way is to take any wavefunction, permute the particle coordinates in all
ways, then add all these permuted-coordinate wavefunctions together. We call
this a **symmetrized wavefunction** because if we swap any pair of coordinates
in this sum it will remain unchanged. It remains the same because in the list
of all permuted wavefunctions a particular term always occurs with a unique
partner where the two coordinates are swapped. We write the symmetrized
wavefunction like this:

$$
\Phi(\textbf{x}_1 \ldots \textbf{x}_{N})
=
\frac{1}{\sqrt{N!}}
\sum_u^{N!} P_u
\phi_1(\textbf{x}_1) \ldots
\phi_N(\textbf{x}_N).
$$

The factor \\( N! \\) is required to ensure the wavefunction is normalized
(assuming the orbitals \\( \phi_i \\) are normalized also). Incidentally, such
a wavefunction is appropriate to describe a *boson* wavefunction which obeys
the Pauli principle for bosons. But we are interested in electrons, which are
fermions, so the wavefunction should change sign. Since the permuted list
contains all terms in pairs, it should be clear to you that for the
wavefunction to change sign every term must be *subtracted* from its permuted
partner if we want the wavefunction to change sign. The result is

## Antisymmetric orbital-product wavefunction

$$
\Phi(\textbf{x}_1\ldots\textbf{x}_{N})
=
\frac{1}{\sqrt{N!}}
\sum_u^{N!} \sigma_u P_u
\phi_1(\textbf{x}_1) \ldots
\phi_N(\textbf{x}_N).
$$

The \\( \sigma_u \\) is either +1 or -1 depending on whether
the permutation \\( P_u \\) if even or odd. The whole wavefunction
is **antisymmetrized**.

Note that *any* wavefunction can be symmetrized or antisymmetrized,
not just the Hartree orbital-product wavefunction, as we have done.

## Determinant wavefunction

Finally, the antisymmetrized orbital-product wavefunction can be written
in terms of a determinant like this

$$
\Psi(\textbf{x}_1\ldots\textbf{x}_{N})
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

This is called a **single determinant wavefunction**. It forms the basis
of many methods for approximately solving the Schrodinger equation.

