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

The particle-in-a-box models are great for seeing how
QM works and remains relevant:

* The images above show the probability density waves of a surface electron
  trapped in a “ring” of iron atoms placed on a copper surface by [scanning
  tunneling microscopy (STM)](http://en.wikipedia.org/wiki/Scanning_tunneling_microscope). 
  The shapes of these waves are well modelled by an electron trapped in a
  disk-shaped box.

* The particle-on-a-ring model has also been used by my colleague
  Pierre-Francois Loos to develop [insight into electron correlation](http://arxiv.org/abs/1302.6661).

## For students ##

Scattered through this post and at the end are some examples and questions.
The examples have answers. You would be well advised to study the answers and
attempt the questions. Nudge-nudge wink-wink.


## Quick review of QM

There two main rules to quantum mechanics:

1. **Any experimental measurement is represented by an operator**

   - An operator is a function of the coordinates and momenta of the particles in the system.
   - The momenta are replaced by a derivatives with respect to the particle coordinates times
     \\( -i\hbar/2m \\) (where \\( m \\) is the mass of the particle and \\( \hbar \\) is
     Planck’s constant divided by \\( 2\pi \\) ).
   - Operators are sometimes represented by a symbol with a hat on top e.g. like \\( \hat{A} \\).
     Sometimes we forget the hat if it is clear it is an operator.

2. **The result of any measurement is an eigenvalue of the operator describing the experiment**

   - An eigenvalue of an operator \\( \hat{A} \\) is any real number \\( a \\) which
     obeys an *eigenvalue equation* i.e. \\( \hat{A} \psi = a \psi \\).
   - An eigenvalue equation is a *differential equation* i.e. an equation involving derivatives.
     The unknown quantities to be determined in this equation are the
     *wavefunction* \\( \psi \\) and the eigenvalue \\( a \\).
   - Since an experiment can yield a many differenet results, the corresponding eigenvalue equation
     for the operator for that experiment also has many different eigenvalues and solutions.
     Each eigenvalue \\( a \\) and its wavefunction \\( \psi \\) are paired together.

## Examples

The following are examples of questions that may be asked in the exam.

**Q1**. *Write down the momentum operator of an electron in one dimension*

**A1**.

*Strategy*. Use rule 1 of quantum mechanics.

The momentum operator of an electron in one dimension is 
\\( \hat{p} = -i\hbar \frac{d}{dx} \\).


**Q2**. *Write down the momentum operator of an electron in three dimensions*

**A2**.

*Strategy*. To do this we have to realize that the momentum in three dimensions
is a vector. So we have to write down a vector with three conponents. Each
component is defined like in A1.

The momentum opertor is given by

$$
\hat{\B{p}} = -i \hbar
\left(
\begin{array}{c}
\partial/\partial x \\
\partial/\partial y \\
\partial/\partial z \\
\end{array}
\right)
$$

Note

* A boldface symbol for \\( \B{p| \\) is used to represent a vector.

* The partial derivative symbol \\( \partial \\) ius used whenever there is
  more than one variable involved like in thermodynamics. 

* Also note that sometimes the \\( x \\), \\( y \\) and \\( z \\) coordinates
  are written as \\( r_1 \\), \\( r_2 \\), \\( r_3 \\)

$$
\hat{\B{p}} = -i \hbar
\left(
\begin{array}{c}
\partial/\partial r_1 \\
\partial/\partial r_2 \\
\partial/\partial r_3 \\
\end{array}
\right)
$$

**Q3**. *Write down the definition of the angular momentum operator 
\\( \hat{\B{l}} \\) given that the angular momentum is defined by*

$$
\B{l} = \B{r} \times \B{p} =
\left(
\begin{array}{c}
r_2 p_3 - r_3 p_2 \\
r_3 p_1 - r_1 p_3 \\
r_1 p_2 - r_2 p_1
\end{array}
\right)
$$

**A3**.

*Strategy*. Substitute the definition of the momentum operator (A2) into the
expression for \\( \B{l} \\).

The expression for the angular momentum operator is:
$$
\hat{\B{l}} =
-i\hbar
\left(
\begin{array}{c}
r_2 \pd{}{r_3} - r_3 \pd{}{r_2} \\
r_3 \pd{}{r_1} - r_1 \pd{}{r_3} \\
r_1 \pd{}{r_2} - r_2 \pd{}{r_1}
\end{array}
\right)
$$


**Q4**. *Write down the equation which determines the experimental values of
an electron’s momentum in one dimension.*

**A4**.

*Strategy*. Use rule 2 of quantum mechanics. Write down the eigenvalue equation
for the momentum operator of the elctron.

The allowed experimental values \\( a \\) of the electron momentum in one
dimension are determined by solving the following eigenvalue equation:

$$
\underbrace{\left( -i \hbar \frac{d}{dx} \right)}_{\hat{p}_e} \psi(x) = a \psi(x).
$$


**Q5**. *Write down the equation which determines the experimental energies of an
electron moving freely in one dimension. Note that the 
[(kinetic) energy of a free particle](http://en.wikipedia.org/wiki/Kinetic_energy#Newtonian_kinetic_energy)
is given in terms its momentum by the equation \\( p^2/2m \\) where \\( m \\)
is the mass of the particle.*

**A5**.

*Strategy*. To do this question we need the formula for the energy in terms of
the free electrons position and momentum. Luckily that is given to us. Next we
do the usual substitution for the electron momentum. Then we use rule 2 and
write down the eigenvalue equation.

The allowed experimental energies \\( E \\) are obtained by solving
the following eigenvalue equation, 

$$
\hat{H} \psi(x) = E \psi(x).
$$

Note that this usually means first finding the unknown wave function
\\( \psi \\) corresponding to each unknown allowed energy value \\( E \\).

Note that \\( \hat{H} \\) is the energy operator or *hamiltonian* for the
electron written in terms of position coordinates and momenta. In this case it
is the same as the kinetic energy,

$$
  \begin{align}
  \hat{H} & = \frac{p^2}{2m_e} \\
          & = -\frac{\hbar^2}{2m_e}\frac{d^2}{dx^2}
  \end{align}
$$

The right hand side is the kinetic energy of the electron, obtained by
substituting \\( p = -i\hbar d/dx \\) (see rule 1 above) in the equation for
kinetic energy \\( p^2/2m_e \\); \\(x \\) and \\( m_e \\) are the position
coordinate and mass of the electron, respectively.


**Q6**. *Write down the equation for the allowed energy levels of the hydrogen atom in one dimension.*

**A6**.

*Strategy*. We need to write down the total energy of an electron and a proton
in one dimension. The total energy is comprised of the kinetic energy of
each particle. Hence it depends on the momentum of the electron \\( p_e \\) and
the momentum of the proton \\( p_p). The total energy also depends of the
electrical attraction between the proton and the electron which depends
on the (inverse) distance between the two particles according to Coulomb’s
Law. This involves the
coordinates of the electron and the proton, respectively \\( x_e \\)
and \\( x_p \\)

The hydrogen atom involves an electron and a proton.
The allowed energies \\( E \\) for an electron and proton moving in one
dimension are determined by the following eigenvalue equation:

$$
\hat{H} \psi(x_p,x_e) = E \psi(x_p,x_e)
$$

where \\( \hat{H} \\) is the total energy operator or *hamiltonian*
for the system, given by

$$
\begin{align}
\hat{H} & = \frac{p^2_p}{2m_p} + \frac{p^2_e}{2m_e} + \frac{1}{4\pi\epsilon_0}\frac{1}{|x_p - x_e|} \\
        & = -\frac{\hbar^2}{2m_p}\frac{d^2}{dx_p^2}
            -\frac{\hbar^2}{2m_e}\frac{d^2}{dx_e^2}
            -\frac{1}{4\pi\epsilon_0}\frac{1}{|x_p - x_e|}.
\end{align}
$$

* The first term is the kinetic energy of the proton.
* The second term is the kinetic energy of the electron.
* The third term is the (negative!) attraction energy of the electron for the proton.
* \\(x_p \\) and \\( x_e \\) are the position coordinates of the proton and electron, respectively.
* The wavefunction \\( \psi \\) is a function of these two coordinates.

**Q7**. *Is the equation \\( \hat{P}^2 \psi = \hat{P}\psi \\) an eigenvalue equation?*

**A7**.

Yes it is an eigenvalue equation! If we set \\( \phi = \hat{P}\psi \\) it can
be written as \\( \hat{P}\phi = \phi = 1\phi \\). This is an eigenvalue equation
for \\( \phi \\) with eigenvalue equal to 1. Note: Any old operator
will *not* obey such an equation i.e. such an operator \\( \hat{P} \\) must be
somewhat *special* ... if it even exists.

## Free electron in one dimension

Let’s try and solve the equation for an electron moving freely (i.e. not
subject to any forces) on the x axis, question Q 4.

Before solving the equation let’s think what answer we might expect. Actually, since
the electron can move freely, we would expect that it can have ... any energy it likes,
as long as it is positive.

Now let’s do the problem. Look at the equation in Q 4. Notice that it has the
form \\( \mbox{derivative of } \psi = C \psi \\) where \\( C \\) is a constant.
The solution of this differential equation is an exponential (it looks like a
first order kinetic equation). Based on this we try \\( \psi = A e^{B x} \\)
(where \\( A \\) and \\( B \\) are arbitrary constants) into the eigenvalue
equation. The left hand side becomes:

$$
\begin{align}
-\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} \psi(x)
& =
-\frac{\hbar^2}{2 m_e} \frac{d^2}{dx^2} C e^{B x}
\\
& =
-\frac{\hbar^2}{2 m_e} C B^2 e^{B x}
\\
& =
-\frac{B^2\hbar^2}{2 m_e} \psi(x)
\end{align}
$$

In the second line we used the fact that \\( d^2/dx^2 e^{B x} = B^2 e^{B x} \\).
Comparing this with the definition of an eigenvalue equation shows that
our guess \\( \psi(x) = C e^{B x} \\) is a solution of the eigenvalue
equation with energy

$$
E = -\frac{B^2\hbar^2}{2 m_e}
$$

How does this compare with our initial expectation? Well, since \\( k \\)
is an arbitrary constant this shows that the energy can be any
*negative* number. But this does not make sense! Energy must be positive!

In order to get a positive energy we should try and reverse the sign
in the above equation. Luckily this is easy to do if we choose the
constant \\( B \\) to be a purely complex number e.g. \\( B = i k \\) 
where \\( k \\) is a real number. Then the energy becomes positive and 
the solutions are

$$
\begin{align}
\psi(x) & = A e^{i k x}
E       & = \frac{k^2\hbar^2}{2 m_e}
\end{align}
$$

Q 7. *Show that the free electron wavefunction has momentum \\( \hbar k \\)*

A 7.

To show this, we need to demonstrate that \\( \psi(x) \\) is an eigenfunction
of momentum

$$
\begin{align}
\hat{p} \psi(x) & = -i \hbar \frac{d}{dx} e^{i k x}  \\
                & = -i \hbar (i k) e^{i k x} \\
                & = \hbar k e^{i k x} 
\end{align}
$$

This is an eignevlaue equation with eigenvalue \\( \hbar k \\). Apparently the
momentum of a free electron \\( p_e \\) must equal \\( \hbar k \\)


## Discussion of the free electron solutions

We see that if we follow the rules of QM then the wavefunction for
the free electron is a complex function. But is it a *wavefunction*?
Does it look like a wave? According to de Moivre’s theorem we can write

$$
\psi(x) = A e^{i k x} = A \left( \cos (k x) + i \sin (k x) \right).
$$

So the complex function \\( \psi(x) \\) looks like a complex sum
of sinusoidal waves. In fact, if this complex wave has wavelength 
\\( \lambda \\) it is easy to see that 

$$
k = \frac{2\pi}{\lambda}
$$

because in the space of one wavelength from \\(x = 0 \\) until \\(x = \lambda \\)
the argument of the \\( \cos \\) or \\( \sin \\) wave undergoes one circular
cycle of angle \\( 2\pi \\).








