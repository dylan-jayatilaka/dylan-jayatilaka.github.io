---
layout: post
title: "Polarizability and hyperpolarizability as Hartree-Fock energy derivatives"
description: "Calculating the polarizability and hyperpolarizability in Hartree-Fock theory"
category: articles
tags: [polarizability, hyperpolarizability, response properties, energy derivatives]
modified: 2014-11-04
image:
  feature: vincent-van-gough-the-starry-night-1889.jpg
  credit: Vincent van Gough - The Starry Night - Museum of Modern Art, New York
comments: false
share: true
---

In the previous post I was interested in how the force constants change with an
applied field. In order to deal with that question, the dipole moment and
polarizability were defined as electric field derivatives.

In this post I expand on where these definitions come from, and how such
polarizabilities may be calculated -- at least, within Hartree-Fock theory.

## Helmann-Feynman theorem

The dipole moment and  polarizability definitions ultimately arise from the
[Helmann-Feynman](http://en.wikipedia.org/wiki/Hellmann%E2%80%93Feynman_theorem) 
theorem.

The Helmann-Feynman theorem states that if \\( \lambda \\) is a parameter on
which the Hamiltonian depends then

$$
\boxed{
\displaystyle\pd{E}{\lambda} = \braopket{\Psi}{\displaystyle\pd{H}{\lambda}}{\Psi}
}
$$

The parameter \\( \lambda \\) may be

* The coordinate of a particular nucleus (in which case the left-hand-side
  represents the force on that nucleus along that coordinate), or 

* It may represent a component of an applied electric field (in which case the
  left-hand side represents a component of the dipole moment).

*Proof*

The proof is trivial:

$$
\begin{align}
\displaystyle\pd{E}{\lambda}
&=
\displaystyle\pd{}{\lambda}\braopket{\Psi}{H}{\Psi}
\\
&=
  \braopket{\Psi}{\displaystyle\pd{H}{\lambda}}{\Psi}
+ \braopket{\displaystyle\pd{\Psi}{\lambda}}{H}{\Psi}
+ \braopket{\Psi}{H}{\displaystyle\pd{\Psi}{\lambda}}
\\
&=
  \braopket{\Psi}{\displaystyle\pd{H}{\lambda}}{\Psi}
+ E\braket{\displaystyle\pd{\Psi}{\lambda}}{\Psi}
+ E\braket{\Psi}{\displaystyle\pd{\Psi}{\lambda}}
\\
&=
  \braopket{\Psi}{\displaystyle{H}{\lambda}}{\Psi}
+ E \underbrace{\displaystyle\pd{}{\lambda}\braket{\Psi}{\Psi}}\sub{= 0}.
\end{align}
$$

The last term is zero because of the normalization condition \\( \braket{\Psi}{\Psi} = 1 \\).

## Dipole and polarizabilities as energy derivatives

In order to understand how the dipole moment arises from the
Helmann-Feynman theorem we need to know what the Hamiltonian
for a system looks like in the presence of an electric field.









