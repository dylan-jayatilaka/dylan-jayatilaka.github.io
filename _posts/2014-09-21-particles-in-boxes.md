---
layout: post
title: "Particles in boxes"
description: "The Schrodinger equation is solved for several one dimensional cases"
category: articles
tags: [chem2002, schrodinger equation, particle in a box]
modified: 2014-09-21
image:
  feature: quantum-corral.png
  credit: Confinement of electrons to quantum corrals on a metal surface - Crommie, Lutz and Eigler (1993) Science 262, pp. 218-220
  creditlink: http://www.sciencemag.org/content/262/5131/218.abstract?sid=9e2fb1df-03ed-44fe-bd4d-fbc6fdd5b720
comments: false
share: true
---

This is a post for my second year Phys Chem students, though it may be
of interest to others.

Here I explain how to solve the one dimensional Schrodinger equation for
various potentials i.e. the classic particle-in-a-box models.

The particle-in-a-box models are great for seeing in a simple way how
QM works, and they have relevance:

* For example, the images above show the probability density of surface
  electrons trapped in a circular box made of iron atoms placed on a copper
  surface by scanning tunneling microscopy (STM). The shapes of these waves are
  very much like those for an electron trapped in a disk.

* The particle-on-a-ring model has also been used by my colleague
  Pierre-Francois Loos to develop [insight into electron correlation](http://arxiv.org/abs/1302.6661)

For the students: 

Scattered through this post and at the end are some examples, questions, and
exercises. You would be well advised to attempt them. Nudge-nudge wink-wink.


## One paragraph review of QM

There are only two rules to quantum mechanics:

1. *Any experimental measurement is represented by an operator*.
   - An operator is a function of the coordinates and momenta of the particles in the system.
   - The momenta are replaced by a derivatives with respect to the particle coordinates times
     \\( -i\hbar/2m \\) (where \\( m \\) is the mass of the particle and \\( \hbar \\) is
     Planck’s constant divided by \\( 2\pi \\) ).
   - Operators are sometimes represented by a symbol with a hat on top e.g. like \\( \hat{A} \\).
     Sometimes we forget the hat if it is clear it is an operator.

2. *The results of any experimental measurement must be an eigenvalue of the operator describing the experiment*
   - An eigenvalue of an operator \\( \hat{A} \\) is any real number \\( a \\) which
     obeys an *eigenvalue equation* i.e. \\( \hat{A} \psi = a \psi \\).
   - An eigenvalue equation is a *differential equation* i.e. an equation involving derivatives.
     The unknown quantities to be determined in this equation are the
     *wavefunction* \\( \psi \\) and the eigenvalue \\( a \\).
   - Since an experiment can yield a many differenet results, the corresponding eigenvalue equation
     for the operator for that experiment also has many different eigenvalues and solutions.
     Each eigenvalue \\( a \\) and its wavefunction \\( \psi \\) are paired together.

Example. The momentum of an electron in one dimension is \\( p = -i\frac{\hbar}{2 m_e} \frac{d}{dx} \\)
where \\( m_e \\) is the mass of the electron.

Example. The momentum of a proton in three dimension is the vector 

$$
\B{p} = -i\frac{\hbar}{2 m_p} 
\left()
\begin{array}{c}
\partial/\partial x \\
\partial/\partial y \\
\partial/\partial z \\
\end{array}
\right)
$$

where \\( m_p \\) is the mass of the proton.

Example. The allowed experimental values \\( a \\) of the electron momentum in one dimension
(moving freely) are determined by solving the following eigenvalue equation

$$
\left( -i\frac{\hbar}{2 m_e} \frac{d}{dx} \right) \psi(x) = a \psi(x).
$$




