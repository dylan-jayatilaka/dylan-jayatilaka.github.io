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

To understand these notes you need to

* Know basic calculus (derivatives and integrals) and you need to understand
  the basics of complex numbers. If you do not, bail out here, and come back
  after you know.

* Second, you should read the previous [super quick intro to quantum
  mechanics](http://dylan-jayatilaka.net/articles/super-quick-summary-of-qm/)

Scattered through this and the previous post are some questions. Carefully
study these questions and their answers. The exam questions will be very
similar, if not identical.

The later material on transmission through multiple barriers is not
examinable. I present it because it could be useful if you are interested
in, for example, modelling energy levels and conduction through molecules
(Prof. George Koutsantonis is interested in making such “molecular wires”).

## What is a particle-in-a-box problem?

Particle in a box problems are those for a single particle moving
in one dimension subject to a piecewise constant potential energy i.e.
a potential energy that looks like the following function:

<figure>
   <img src="/images/piecewise-constant-potential.jpg">
</figure>

From looking at this picture you can see that the particle experiences
different “constant” energies at different points along the axis. In fact,
if we wanted to write this potential in “maths” it would be this:

$$
V(x) =
\left\{
\begin{array}{cl}
V_0 & \textrm{for } x<x_1     \\
V_1 & \textrm{for } x_1<x<x_2 \\
V_2 & \textrm{for } x>x_2
\end{array}
\right.
$$

In this case the article seems to encounter a kind of “step barrier”.
Of course, other shapes for \\( V(x) \\) are possible and each leads
to a different problem.

## Strategy for solving particle-in-a-box problems

The strategy for solving these one dimensional problems is always the same:

1. Write down the
   [Hamiltonian](http://en.wikipedia.org/wiki/Hamiltonian_(quantum_mechanics)#The_Schr.C3.B6dinger_Hamiltonian)
   for the problem, 
   
   $$
   \hat{H} = -\displaystyle\frac{\hbar^2}{2m} \frac{d^2}{dx^2} + V(x)
   $$

   and hence the Schrodinger equation \\( \hat{H}\psi = E\psi \\) for the
   unknown energies \\( E \\) and unknown wavefunctions \\( \psi \\).

2. Write down the general solution in each region where the potential is
   constant. The general solutions in each region is *always* of the
   form \\( \psi(x) = A e^{B x}\\) where \\( A \\) and \\(B\\), \\(C\\) are
   (possibly complex) unknown constants to be found. To save time you can
   learn these possible cases to be applied in different regions where
   the potential is constant:

   - For free or unbound particles \\( \psi(x) = A e^{i k x} \\).
     A free particle is one where the energy \\( E \\) is greater than the
     largest value of the potential \\( V(x) \\) i.e. the particle has enough
     energy to overcome any barrier.

   - For bound electrons where the energy of the particle is *less* than
     the energy of the barrier, \\( \psi(x) = A e^{-\alpha x} + B e^{+\beta x} \\).

   - For bound electrons where the energy of the particle is *greater* than
     the energy of the barrier, \\( \psi(x) = A \sin kx + B \cos kx \\).

3. Find the unknown constants in the wavefunction(s) by making sure that
   the solutions are continuous and smooth - see Rule 1 of quantum mechanics in
   the [previous post](http://dylan-jayatilaka.net/articles/super-quick-summary-of-qm/`). 
   At the end of the problem there will usually only one unknown constant left
   which can be found by the normalization condition if needed.

A pretty good graphic for illustrating this procedure is shown at the
[hyperphysics site here](http://hyperphysics.phy-astr.gsu.edu/hbase/quantum/pfbox.html).

**Q10**. *What is the basic strategy for solving particle in a box problems?
You do not need to list the possible general solutions for each case*.

## Free electron in one dimension

Now we get to the meat.

<figure>
   <img src="/images/meat-on-the-bone.jpg">
</figure>

**Q9**. *Solve the Schrodinger equation for an electron moving freely in one dimension*.

*Strategy* 

The strategy for solving these problems was given above. The Schrodinger
equation for the free particle was written down in Q5 in the last post. But
before applying this strategy and solving the equation let’s think what answer
we might expect. Actually, since the electron can move freely, we would expect
that it can have ... any energy it likes ... as long as it is positive. Also,
we expect that an electron moving freely should be located ... well, anywhere
it likes ... meaning to say that the probability of finding it at any position
is equally likely.

*Answer*

From Q5 the Schrodinger equation for the free electron is

$$
  -\frac{\hbar^2}{2m_e}\frac{d^2\psi}{dx^2} = E \psi
$$

From the strategy we know a possible solution of this equation is
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
& =  \frac{\hbar^2 k^2}{2 m_e} \psi(x)
  =  E\, \psi(x) 
\end{align}
$$

This shows that \\( \psi(x) = A e^{i k x} \\) is indeed a solution of our
Schrodinger equation provided that

$$
E = \frac{\hbar^2 k^2}{2 m_e}.
$$

Actually, you can check that \\( \psi(x) = B e^{-i k x} \\) with the
opposite value of \\( k \\) is also a solution to the same equation
with the *same* energy. You can see this by doing the above algebra
again with \\( k \\) replaced with \\( - k \\). Since the operator
\\( \hat{H} \\) acts on each solution separately, you can see that

$$
\psi(x) = A e^{i k x} + B e^{-i k x}.
$$

is *also* a solution. The meaning of these two different solutions
is discussed in the next problem. But Q9 is now solved!

Note:

* The last equation illustrates an important point about quantum mechanics: if
  we have more than one solution, we can take a linear combination of them like
  above and still get the same solution! This is the idea behind 
  [hybrid atomic orbitals](http://en.wikipedia.org/wiki/Orbital_hybridisation) 
  in the valence bond theory of chemical bonding. In that theory, linear
  combinations of (nearly equal energy) s and p orbitals are used to explain
  the geometry of bonding around a central atom.

Note that as we expected:

* \\( E \\) is positive regardless of whether the arbitrary
  constant \\( k \\) is positive or negative (since the square of an arbitrary
  number is always positive).

* The probability of fiding the electron an any position is
  \\( \psi^{\ast}(x) \psi(x) = A^{\ast} e^{-i k x} A e^{i k x} = |A|^2 \\) and
  does not depend on \\( x \\) i.e. the probability of finding
  the particle at one place or another is the same i.e. the particle
  is located everywhere with equal probability.

**Q10**. *Show that the free electron wavefunction \\( \psi = A e^{i k x} \\)
has momentum \\( \hbar k \\)*

*Strategy* 

According to the rules of QM, a wavefunction has a certain momentum if it is an
eigenfunction of the corresponding operator. Hence we need to show that 
\\( \psi(x) \\) is an eigenfunction of the momentum \\( \hat{p} \\).

*Answer*

We evaluate \\( \hat{p}\psi(x) \\) for the wavefunction in Q9:

$$
\begin{align}
\hat{p} \psi(x) & = -i \hbar \frac{d}{dx} A e^{i k x}  \\
                & = -i \hbar (i k) A e^{i k x} \\
                & = \hbar k \psi(x)
\end{align}
$$

This is an eigenvalue equation with eigenvalue \\( \hbar k \\). Therefore the
momentum of a free electron with wave function \\( \psi(x) = e^{i k x} \\)
is \\( \hbar k \\). 

Note that there are two values of the momentum \\( p_e = \pm \hbar k \\)
corresponding to the wavefunctions \\( \psi(x) = e^{\pm i k x} \\). The positive
(or negative) values correspond to a wave moving in the positive (or negative)
directions respectively.

Note also that the unknown constant \\( A \\) can not be determined by
the normalization condition: normalization ony applied to bound states.

## Particle in a box

**Q11**. *Solve the Schrodinger equation for an electron in a box of length
\\( L \\) which starts at the origin (the potential is infite outside the box)*.

*Strategy* 

Draw a picture and apply the given strategy above. Note that the the
wavefunction \\( \psi(x) = 0 \\) outside the box; if not we would get infinity
appearing in the equation \\( \hat{H}\psi(x) = E\psi(x) \\) when \\(x \\) is
outside the box.

*Answer*

The potential \\( V(x) \\) looks like below (along with the solutions which we
have yet to find).

<figure>
   <img src="/images/p-in-infinite-box.jpg">
</figure>

According to the strategy we should try wavefunctions of the form
\\( \psi(x) = A \sin k x + B \cos k x \\). Substituting in the Schrodinger
equation we get

$$
\begin{align}
\textrm{LHS}
& = -\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} \psi(x) \\
& = -\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} \left( A \sin kx + B \cos kx \right) \\
& = -\frac{\hbar^2}{2 m_e} \frac{d}{dx} \frac{d}{dx} \left( A \sin kx + B \cos kx \right) \\
& = -\frac{\hbar^2}{2 m_e} \frac{d}{dx} \left(A k \cos kx - B k \sin kx \right) \\
& = -\frac{\hbar^2}{2 m_e} \left(-A k^2 \sin kx - B k^2 \cos kx \right) \\
& =  \frac{\hbar^2}{2 m_e} k^2 \left(A \sin kx + B \cos kx \right) \\
& =  \frac{\hbar^2 k^2}{2 m_e} \psi(x)
  =  E\, \psi(x) 
\end{align}
$$

So as before we see that \\( \psi(x) = A \sin k x + B \cos k x \\) is a solution
of the Schrodinger equation with

$$
E = \frac{\hbar^2 k^2}{2 m_e}.
$$

In fact this solution would be acceptable as an answer to the “free particle”
problem. The difference is now that we have to apply the boundary conditions on
the wavefunction, which are from the picture:

$$
\begin{align}
\psi(0) & = 0 \ \ \subnote{at $x = 0$}\\
\psi(L) & = 0 \ \ \subnote{at $x = L$}
\end{align}
$$

* Substituting \\( \psi(x) \\) in the first equation above determines the value
  of the unknown constant \\( B \\) as follows:

  $$
  \begin{align}
  \psi(0) & = A \sin k 0 + B \cos k 0 \\
          & = A \sin 0 + B \cos 0 \\
          & = A \times 0 + B \times 1 \\
          & = B \\
          & = 0
  \end{align}
  $$

  Here we used the standard values of \\( \sin 0 = 0 \\) and \\( \cos 0 = 1 \\).
  Therefore we have figured out that \\( \psi(x) = A \sin k x \\).

* Now we apply the second boundary condition and see what we get:

  $$
  \begin{align}
  \psi(L) & = A \sin k L \\
          & = \sin k L \\
          & = 0
  \end{align}
  $$

  This equation has solutions only when the angle \\( k L = n \pi \\) radians where
  \\( n = 1, 2, \ldots \\). Note that the value \\( n = 0 \\) leads to a a wavefunction
  \\( \psi(x) = 0 \\) which has no area underneath it i.e. it is unnormalizable and therefore
  doesn’t obey the rules for an allowed wavefunction. Likewise although 
  \\( n = -1, -2, -3, \ldots \\) are also solutions of the above equation, they
  do not lead to different wavefunction solutions since 
  \\( \psi(x) = \sin kx = \sin (-kx) \\) due to the properties of the sine function.

The last boundary condition equation gives a value for the unknown \\( k \\)
constant which means it determines the allowed energy eigenvalues:

$$
E = \frac{\hbar^2 k^2}{2 m_e} 
  = \frac{\hbar^2}{2 m_e}\frac{(n\pi)^2}{L^2}, \ \ n = 1, 2, 3, \ldots
$$

Corresponding to wavefunction \\( \psi(x) = A \sin \displaystyle\frac{n \pi}{L} x \\).

To find the unknown constant \\( A \\) we must normalize the wavefunction,

$$
\int_0^L \psi^\ast(x) \psi(x) dx
  = \int_0^L A^2 \sin^2 \frac{n\pi}{L} x 
  = 1
$$

From which we get:

$$
A  = \left( \int_0^L \sin^2 \frac{n\pi}{L} x \right)^{1/2}
$$

We can evaluate this integral by looking up tables if we like.
The important thing is not the answer but *how* to get it.

## Particle in a half infinite box

**Q11**. *Solve the Schrodinger equation for an electron in a box of length
\\( L \\) which starts at the origin. The potential is infinite to the left
of the box, and has a given value \\( V_0 \\) to the right. The energy of the
electron is less than \\( V_0 \\)*.

*Strategy*.

First draw a picture of the potential. It looks similar like the previous
question, except that to the right, the height of the box is \\( V_0 \\) and
not infinite. The wavefunction to the left of the box is zero as explained
in the previous question. There are two other wavefunctions \\(\psi\sub\s{in} \\) and
\\(\psi\sub\s{out}\\) for the inside and outside of the box respectively. These
two wavefunctions need to be “joined” at the boundary to make a “smooth”
wavefunction. Inside the box, the wavefunction s the same as before,
\\( \psi\sub\s{in}(x) = A \sin k x \\). Outside the box, according
to strategy above, the wavefunction outside the box is
\\( \psi\sub\s{out}(x) = A e^{-\alpha x} + B e^{\alpha x} \\).
However the part \\( B e^{\alpha X } \\) gets bigger as \\(x \\) gets larger 
and so if constant \\( B \\) is not zero the wavefunction would have an
infinite area underneath it i.e. it would be unnormalizable.
Therefore the wavefunction outside the box is
\\( \psi(x)\sub\s{out}(x) = A e^{-\alpha x} \\). Now we substitute
\\(\psi\sub\s{in}\\) and \\(\psi\sub\s{out}\\) into the Schrodinger equation
and apply the boundary conditions to get the answer.

*Answer*

* Exactly as before, we substitut \\( \psi\sub\s{in} \\) into the
  Schrodinger equation to get

  $$
  E = \frac{\hbar^2 k^2}{2 m_e}      \ \ \subnote{inside the box}.
  $$

* Outside the box i.e. for \\( 0 < x < L \\) we have a slightly different
  Schrodinger equation:
  
  $$
  \hat{H}\psi\sub\s{out}(x)
  = \left[ -frac{\hbar}^2}{2 m_e}\frac{d^2}{dx^2} + V_0\right] \psi\sub\s{out}(x)
  = E\, \psi\sub\s{out}(x)
  $$
  
  Substituting \\( \psi\sub\s{out}(x) = A e^{-\alpha x} \\) into the LHS
  gives
  
  $$
  \begin{align}
  \textrm{LHS}
  & = -\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} \psi\sub\s{out}(x) \\
  & = -\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} \left( A e^{-\alpha x}) \\
  & = -\frac{\hbar^2}{2 m_e} \frac{d}{dx} \frac{d}{dx} \left( A e^{-alpha x} \right) \\
  & = -\frac{\hbar^2}{2 m_e} \frac{d}{dx} \left(A (-\alpha) e^{-\alpha x} \right) \\
  & = -\frac{\hbar^2}{2 m_e} \left(A \alpha^2 e^{-a\lpha x}\right) \\
  & = -\frac{\hbar^2}{2 m_e} \alpha^2 \left( A e^{-\alpha x} \right) \\
  & = -\frac{\hbar^2 \alpha^2}{2 m_e} \psi\sub\s{out}(x)
  \end{align}
  $$
  
  Therefore
  
  $$
  \hat{H}\psi\sub\s{out}(x)
  = \left[ -\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} + V_0 \right] \psi\sub\s{out}(x)
  = \left[ -\frac{\hbar^2 \alpha^2}{2 m_e}         + V_0 \right] \psi(x)
  = E\,\psi\sub\s{out}(x).
  $$
  
  So we get *another* equation for the energy,
  
  $$
  E = -\frac{\hbar^2 \alpha^2}{2 m_e} + V_0 \ \ \subnote{outside box}
  $$









