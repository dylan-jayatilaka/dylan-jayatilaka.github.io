---
layout: post
title: "Designing circulant Hamiltonians for quantum computing"
description: "The Schrodinger equation is solved for several one dimensional cases"
category: articles
tags: [Circulant matrix, Quantum Computing, Unitary transformation, Discrete Fourier transform, Parr]
modified: 2014-09-21
image:
  feature: samuel-monnier-patternmond.jpg
  credit: Samuel Monnier
  creditlink: http://www.algorithmic-worlds.net/blog/blog.php?Post=20110201
comments: false
share: true
---

The other day [Jingbo Wang](http://www.uwa.edu.au/people/jingbo.wang) from our
Physics department asked me about circulant Hamiltonians.

I had previously come across circulant orbitals from the work of
[Bob Parr](http://www.jstor.org/stable/10245).

Circulant orbitals are non-canonical Hartree-Fock or density functional theory
(DFT) [molecular orbitals](http://en.wikipedia.org/wiki/Molecular_orbital)
which have been transformed unitarily in order to have a density
as close as possible to the electron density divided by the number of
electrons. The name arises from the fact that circulant orbitals transform the
[effective Hamiltonian](http://en.wikipedia.org/wiki/Hartree%E2%80%93Fock_method#Mathematical_formulation)
into a Hermitian
[circulant matrix](http://en.wikipedia.org/wiki/Circulant_matrix) -- that is a matrix
where the rows (or columns) are shifted by a unit cyclic permutation.

I was told by Jingbo that such circulant Hamiltonians are really useful
for performing [quantum computations](http://en.wikipedia.org/wiki/Quantum_computer).

## What this is about

The purpose of this blog is to trivially generalize the work of Bob Parr
to show that *any* group of quantum states can be unitarily mixed to
ensure that the Hamiltonian has a circulant structure in the new basis. The
structure depends only on the actual energies of the states involved.

There are two use cases for the final result:

* Given a general circulant matrix, what are the eigenavlues of a
  physical system needed to construct it?

* Given a real system which gives certain eigenvalues, what circuant
  matrix fesults from it, and can it be used to do any quantum computation?

In order actually *make* a real device (at least!) two serious problems need to
be addressed:

* How do we design a molecule or system with appropriate excited state energies?

* How do we introduce a coherent excited state into the so-designed system at
  an initial time, make sure errors and noise are corrected, and probe it at a
  later time.

I was assured that the error correction part of the second problem
[is soluble](http://en.wikipedia.org/wiki/Quantum_error_correction).

## The circulant basis

We begin by introducing the circulant basis. It is a discrete Fourier
transform of a set of system eigenstates.

So: Let \\( \hat{H} \\) be some physical Hamiltonian with eigenstates
\\( E_n\\) and with corresponding orthonormal eigenstates \\( \Psi_n \\),
\\( n=1,\ldots,N \\). Then we have as usual

$$
\braopket{\Psi_m}{\hat{H}}{\Psi_n} = \delta\sub{mn}
$$

The circulant basis is *defined* by the transformation

$$
\Phi_I
=
\frac{1}{\sqrt{N}}
\sum\sub{l=1}^N \Psi_l \omega^{(I-1)(l-1)}, \ \ \ \omega = \exp(2\pi i/N)
$$

In other words, \\(\Phi_I\\) is a discrete Fourier transform of a finite set
of eigenstates. \\( \omega \\) is an \\(N\\)-th root of unity, \\( \omega^N = 1 \\).

*Theorem*

The circulant transformation is unitary

*Proof*

Since the definition of a unitary transformation is that is preserves
orthonormality, we only need to show that the new basis \\( \Phi_I \\) is also
orthonormal, i.e. that \\( \braket{\Phi_I}{\Phi_J} = \delta\sub{IJ} \\).

$$
\begin{align}
\braket{\Phi_I}{\Phi_J}
& =
\frac{1}{N}
\sum\sub{l=1}^N \sum\sub{m=1}^N
\omega^{-(I-1)(l-1)}
\omega^{ (J-1)(m-1)}
\underbrace{\braket{\Psi_l}{\Psi_m}}\sub{\delta\sub{lm}}
\\
& =
\frac{1}{N}
\sum\sub{l=1}^N
\omega^{-(I-1)(l-1)}
\omega^{ (J-1)(l-1)}
\\
& =
\frac{1}{N}
\sum\sub{l=1}^N
\omega^{ (J-I)(l-1)}
\end{align}
$$

Now there are two cases. When \\( I=J \\) the summand is always equal to one
and the right hand side is equal to 1. When \\( I\neq J \\) the summation
is a geometric series with initial term 1 and ratio \\( \omega \\), so
the sum is given by \\( (1-\omega^n)/(1-\omega) \\), which is zero since
\\( \omega \\) is an \\(N\\)-th root of unity.


## The Hamiltonian in the circulant basis

*Theorem*

$$
\boxed{
H\sub{IJ}
=
\displaystyle
\frac{1}{N}
\sum\sub{l=1}^N
\omega^{(J-I)(l-1)}
E_l
}
$$

*Proof*

Just substitute in the definitions for the circulant states.

$$
\begin{align}
H\sub{IJ}
& =
\frac{1}{N}
\sum\sub{l=1}^N \sum\sub{m=1}^N
\omega^{-(I-1)(l-1)}
\omega^{ (J-1)(m-1)}
\underbrace{\braopket{\Psi_l}{\hat{H}}{\Psi_m}}\sub{E_l\delta\sub{lm}}
\\
& =
\frac{1}{N}
\sum\sub{l=1}^N
\omega^{-(I-1)(l-1)}
E_l
\end{align}
$$

## The Hamiltonian in the circulant basis is a circulant matrix

A [circulant matrix](http://en.wikipedia.org/wiki/Circulant_matrix) has rows
(or columns) which are 1-cyclic permutations of the previous row (or column)
e.g.

$$
\left(
\begin{array}{cccc}
1 & 2 & 3 & 4 \\
4 & 1 & 2 & 3 \\
3 & 4 & 1 & 2 \\
2 & 3 & 4 & 1 \\
\end{array}
\right)
$$

Or in other words \\( H\sub{IJ} = H\sub{I+1,J+1} \\) where the indices are
taken modulo \\( N \\) the size of the matrix. The circulant matrix
is actually only defined by one row or column.

*Theorem*

The Hamiltonian in the circulant basis is a circulant matrix

*Proof*

Obvious by direct inspection. Also we define:

$$
H\sub{IJ} = \frac{1}{N} \sum\sub{l=1}^N \omega_l^{(K-1)(l-1)} E_l \equiv H\sub{K}
$$

The latter is the defining vector for the circulant matrix.

## Designing a Hamiltonian with a certain circulant structure

By “designing” the matrix we mean choosing the energy eigenvalues for the
Hamiltonian in order to achieve a desired circulant structure. We do not mean
actually finding a real physical system with these eigenvalues. That is a much
more difficult task alluded to in the introduction.

Obtaining the eigenvalues associated with a given circulant matrix is actually
fairly trivial. All that is requited is to take the inverse discrete Fourier
transform of the defining vector of the circulant matrix.

*Theorem*

$$
\boxed{
E_m
=
\displaystyle
\sum\sub{K=1}^N H\sub{K} \omega^{-(m-1)(K-1)}
}
$$

*Proof*

Substitute the definition of the defining vector.

$$
\begin{align}
\textrm{RHS}
& =
\frac{1}{N}
\sum\sub{K=1}^N \sum\sub{l=1}^N
\omega^{ (K-1)(l-1)} E_l
\omega^{-(m-1)(K-1)}
\\
& =
\frac{1}{N}
\sum\sub{K=1}^N \sum\sub{l=1}^N
\underbrace{\omega^{ (l-m)(K-1)}}\sub{N\delta\sub{lm}}
E_l
\\
& =
E_m
\end{align}
$$

## Where to now?

I don’t really know, but here were some ideas from the discussion after the talk
I gave in physics:

1. Do some accurate [quantum chemical](http://en.wikipedia.org/wiki/Quantum_chemistry) 
   calculations on real systems, find their energies \\( E_m \\) and from them
   find the circulant matrix \\( H_K \\). Can anything be done with this
   matrix? This approach seems a bit *ad hoc*.

2. Take some examples of circulant matrices known to be useful for
   quantum computing. Find the energy eigenvalues \\( E_m \\)
   corresponding to this system. Try to construct a real system,
   perhaps a real molecule, perhaps a quantum dot or other one dimensional
   system with the required energy levels.

   - An [earlier post](http://dylan-jayatilaka.net/articles/particles-in-boxes/)
     shows how the eigenvalues of a one dimensional system can be
     systematically computed, in general. This approach could be used
     to rationally design such a “quantum line” system with the desired
     eigenvalues.
 
   - Alternatively, use approach 1. to develop some familiarity with the
     type of systems giving rise to certain energy levels.
 
   - Jingbo noted that, using localized basis functions, some Hamiltonians
     *naturally* have a circulant structure e.g. benzene. One is reminded of the
     [Huckel type theories](http://en.wikipedia.org/wiki/H%C3%BCckel_method).
     Initially I agreed. However, I now think that the Hamiltonians with these
     connectivities are *one electron effective Hamiltonians* -- they are not
     actual real Hamiltonians which model the dynamics of real multi-electron
     wavefunctions -- except possibly for the motion of one electron excited
     from the highest occupied molecular orbital (HOMO). It is not clear that
     the excited states of such effective systems will have the same circulant
     structure. However, the idea deserves further consideration because it
     could give insight into how the connectivity of atoms in a molecules 
     affects its circulant structure. This could be probed by more accurate
     quantum chemical calculations.








