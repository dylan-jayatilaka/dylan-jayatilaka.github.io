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

This is a post for my second year Phys Chem students but it may have
tidbits of interest to others.

Particle-in-a-box models are great for seeing how quantum works.

Particle-in-a-box models are not just toy models, either. For example:

* The images above show the probability density waves of a surface electron
  trapped in a “ring” of iron atoms placed on a copper surface by [scanning
  tunneling microscopy (STM)](http://en.wikipedia.org/wiki/Scanning_tunneling_microscope).
  The shapes of these waves are well modelled by an electron trapped in a
  disk-shaped box.

* The particle-on-a-ring model has also been used by my colleague
  Pierre-Francois Loos to develop [insight into electron correlation](http://arxiv.org/abs/1302.6661).

* Later in this post I will show how such models can be used to calculate
  conduction of an electron “through” a series of barriers e.g. for
  designing nanoelectronic devices.

## For students ##

To understand these notes you need to know basic calculus (derivatives and
integrals) and you need to understand the basics of complex numbers. If you do
not, bail out here, and come back after you know.

Scattered through this post are some questions. Carefully study these questions
and their answers. The exam questions will be very similar, if not identical.

The later material on transmission through multiple barriers is not
examinable and for interest only.

## Srategy for solving particle-in-a-box problems

Particle in a box problems are those for a single particle moving
in one dimension subject to a piecewise constant potential energy i.e.
a potential energy that looks like the following function:

<figure>
   <img src="/images/piecewise-constant-potential.jpg">
</figure>

From looking at this picture you can see that the particle experiences
different “constant” energies at different points along the axis.
In this case the barrier

The strategy for solving these problems is always the same.

1. Write down the
   [Hamiltonian](http://en.wikipedia.org/wiki/Hamiltonian_(quantum_mechanics)#The_Schr.C3.B6dinger_Hamiltonian)
   for the problem and hence the Schrodinger equation for the unknown energies
   and wavefunctions.

2. Find the general solutions in each region where the potential is
   constant. The general solutions in each region are *always* of the
   form \\( \psi(x) = A e^{B x}\\) where \\( A \\) and \\(B\\), \\(C\\) are
   (possibly complex) unknown constants to be found. For free or unbound
   particles \\(B\\) *must* be complex. For bound electronts \\(B\\)
   must be real.

3. Find as many of the unknown coefficients as possible by making sure that
   the solutions are continuous and smooth (see Rule 2 below). At the end
   of the problem there will be only one unknown constant which can
   be found by the normalization condition.

A pretty good graphic for illustrating this procedure is shown at the
hyperphysics site here.

You probably have not seen quantum mechanics before and a freaking out.
Don’t worry. Contrary to what you might have thought, you don’t yet know
everything and you have to learn more. So relax and read the summarized
key points on QM below and then see if you can do the questions below.

## Free electron in one dimension

Now we get to the meat.

<figure>
   <img src="/images/meat-on-the-bone.jpg">
</figure>

**Q9**. *Solve the Schrodinger equation for an electron moving freely in one dimension*.

*Strategy*. The strategy for solving these problems was given above. The
Schrodinger equation for the free particle was written down in Q5. But before
applying this strategy and solving the equation let’s think what answer we
might expect. Actually, since the electron can move freely, we would expect
that it can have ... any energy it likes ... as long as it is positive. Also,
we expect that an electron moving freely should be located ... well, anywhere
it likes ... meaning to say that the probability of finding it at any position
is equally likely.

*Answer*

From Q5 the Schrodinger equation for the free electron is

$$
  -\frac{\hbar^2}{2m_e}\frac{d^2\psi}{dx^2} = E \psi
$$

From the strategy we know the solution of this equation is always of the form
\\( \psi(x) = A e^{i k x} \\). Note that the constant \\( i k \\) is explicitly
complex, so that \\( k \\) is a real number. To find the unknown numbers
\\( A \\) and \\(k \\) we substitute this general form into the
left hand side of the equation and simplify:

$$
\begin{align}
\textrm{LHS}
& = -\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} \psi(x) \\
& = -\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} A e^{i k x} \\
& = -\frac{\hbar^2}{2 m_e} \frac{d}{dx} \frac{d}{dx} A e^{i k x} \\
& = -\frac{\hbar^2}{2 m_e} \frac{d}{dx} A (ik) e^{i k x} \\
& = -\frac{\hbar^2}{2 m_e} A (ik)^2 e^{i k x} \\
& =  \frac{\hbar^2}{2 m_e} k^2 A e^{i k x} \\
& =  \frac{\hbar^2 k^2}{2 m_e} \psi(x) \\
& =  E \psi(x) \\
& =  RHS
$$

This shows that \\( \psi(x) = A e^{i k x} \\) is indeed a solution of our
Schrodinger equation provided that

$$
E = \frac{\hbar^2 k^2}{2 m_e}.
$$

The problem is solved. Note that as we expected:

* \\( E \\) is positive regardless of whether the arbitrary
  constant \\( k \\) is positive or negative (since the square of an arbitrary
  number is always positive).

* The probability of fiding the electron an any position is
  \\( \psi^*(x)\psi(x) = A^* e^{-i k x} A e^{i k x} = |A|^2 \\) and
  does not depend on \\( x \\) i.e. the probability of finding
  the particle at one place or another is the same i.e. the particle
  is located everywhere with equal probability.

**Q10**. *Show that the free electron wavefunction has momentum \\( \hbar k \\)*

*Stretegy*

*Answer*.

To show this, we need to demonstrate that \\( \psi(x) \\) is an eigenfunction
of momentum

$$
\begin{align}
\hat{p} \psi(x) & = -i \hbar \frac{d}{dx} e^{i k x}  \\
                & = -i \hbar (i k) e^{i k x} \\
                & = \hbar k e^{i k x}
\end{align}
$$

This is an eigenevlaue equation with eigenvalue \\( \hbar k \\). Apparently the
momentum of a free electron \\( p_e \\) must equal \\( \hbar k \\)









