---
layout: post
title: "Super quick summary of QM"
description: "Quick summary of quantum mechanics"
category: articles
tags: [chem2002, quantum mechanics, wavefunctions, operators, measurement, eigenvalues]
modified: 2014-09-21
image:
  feature: quantum-corral.png
  credit: Confinement of electrons to quantum corrals on a metal surface - Crommie, Lutz and Eigler (1993) Science 262, pp. 218-220
  creditlink: http://www.sciencemag.org/content/262/5131/218.abstract?sid=9e2fb1df-03ed-44fe-bd4d-fbc6fdd5b720
comments: false
share: true
---

This is a post for my second year Phys Chem students.

The purpose of this post is to write down briefly the main ideas and rules of
Quantum mechanics.

Now Quantum mechanics is usually quite baffling and perhaps intruiguing
when you first encounter it. On common question that is encountered is
“Why do I need to know this?” or more briefly “So what?”.

Here is the answer.

You need to understand how quantum mechanics works because quantum
mechanics allows you to in-principle calculate everything about chemistry
(molecular properties, reaction rates) from equations [without having to do
experiments](http://www.brainyquote.com/quotes/quotes/p/pauldirac279318.html).

That’s big. 

In my opinion, these days, every organic chemist should do a simple QM
calculation to test out assumptions about their reaction scheme sites before
going into the lab for some pain. Of course, these QM calcs are done on a
computer - not with pen and paper. So you could just learn to use the
program. But in that case you would have no idea how the calculations work i.e.
you will be just a monkey.

No-one wants to employ a monkey.

<figure>
   <img src="/images/thoughtful-bonobo.jpg">
</figure>

So let’s get started.

## The hyperphysics web site

A really great web site which uses the concept-map idea
and covers the material of the second-year Phys Chem QM
lectures almost perfectly can be found
[here](http://hyperphysics.phy-astr.gsu.edu/hbase/quacon.html#quacon).
Take a [click](http://hyperphysics.phy-astr.gsu.edu/hbase/quacon.html#quacon),
I highly recommend it.

## The Rules of Quantum Mechanics

There are only few rules to quantum mechanics.

But the rules do require some explanation.

Here they are:

1. **The state of a system is described by a wavefunction**

   - The wavefunction is a function of the coordinates of the particles in the
     system. It is usually given the symbol \\( \psi \\)

   - \\( \psi \\) must be continuous i.e. have no “gaps” in it

   - The derivative of \\( \psi \\) must also be continuous i.e. the
     wavefunction must be smooth (except at points where the interaction energy
     becomes infinite - so called singularities)

   - \\( \psi \\) for bound ie. stable states must be
     [normalizable](http://hyperphysics.phy-astr.gsu.edu/hbase/quantum/qm.html#c5)
     i.e. \\( \int |\psi|^2 \\) must exist and must equal one; this is called
     normalization of the wavefunction. The reson is that \\( |\psi(\B{x})|^2 \\) 
     is the probability of finding the particles at given positions \\(\B{x}\\).

2. **Any experimental measurement is represented by an operator**

   - An [operator](http://en.wikipedia.org/wiki/Operator_(physics)#Linear_operators_in_wave_mechanics)
     is a function of the coordinates and momenta of the particles in the
     system.

   - The momenta (which in classical mechanics is written as \\( \B{p} \\) and is equal
     to mass times velocity \\( m\B{v}\\)) is in quantum mechanics equal to a derivatives
     with respect to the particle coordinates times \\( -i\hbar/2m \\) where
     \\( m \\) is the mass of the particle and \\( \hbar \\) is Planck’s
     constant divided by \\( 2\pi \\). This is very different!

   - Operators are sometimes represented by a symbol with a hat on top e.g. like \\( \hat{A} \\).
     Sometimes we forget the hat if it is clear it is an operator.

3. **The result of any measurement is an eigenvalue of the operator describing
   the experiment, and after the measurement the system is completely described
   by the wavefunction corresponding to that eigenvalue**

   - An eigenvalue of an operator \\( \hat{A} \\) is any real number \\( a \\) which
     obeys an [eigenvalue equation](http://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)
     for that operator i.e. \\( \hat{A} \psi = a \psi \\).

   - An eigenvalue equation is a
     [differential equation](http://en.wikipedia.org/wiki/Differential_equation)
     i.e. an equation involving derivatives. The unknown quantities to be
     determined in this equation are the
     [wavefunction](http://en.wikipedia.org/wiki/Wave_function#Position-space_wave_function)
     \\( \psi \\) and the eigenvalue \\( a \\).

   - Example: The [Schrodinger equation]() \\( \hat{H}\psi = E\psi \\) is just
     the eigenvalue equation for the allowed energies \\( E \\) of the system,
     where \\( \hat{H} \\) is the energy operator or
     [Hamiltonian](http://en.wikipedia.org/wiki/Hamiltonian_(quantum_mechanics)#The_Schr.C3.B6dinger_Hamiltonian)
     of the system. The Hamiltonian is (i) the sum of the kinetic energies
     \\( \sum_i p_i^2/2 m_i \\) of every particle and (ii) the potential energy
     of interaction \\( V \\) between the particles. The potential energy depends
     on the positions and momenta of the particles and has to be specified to
     you for each case.

   - There may be many solutions to an eigenvalue equation but not all of them
     are unacceptable (see Rule 1)

   - Since an experiment can yield a many different results, the corresponding
     eigenvalue equation for the operator for that experiment also has many
     different eigenvalues and solutions. Each eigenvalue \\( a \\) and its
     wavefunction \\( \psi \\) are paired together.

   - QM does not predict exactly *which* eigenvalue is obtained from an
     experiment; but if \\( \psi_i \\) is the initial wavefunction before the
     experiment \\( \hat{A} \\) then QM *does* predict

     - That the *probability* of getting result \\( a \\) with wavefunction
       \\( \psi_a \\) is \\( |\int \psi_a^* \psi_i|^2 \\)

     - That the average of many experimental results is given by the
     [expectation value](http://hyperphysics.phy-astr.gsu.edu/hbase/quantum/expect.html)
     \\( \expectation{A} = \int \psi^*_i \hat{A} \psi_i \\).

## Do you get it? Test yourself

The following are examples of questions that may be asked in the exam.

**Q1**. *Write down the momentum operator of an electron in one dimension*

*Strategy*. Use rule 1 of quantum mechanics.

*Answer*. The momentum operator of an electron in one dimension is
\\( \hat{p} = -i\hbar \frac{d}{dx} \\).


**Q2**. *Write down the momentum operator of an electron in three dimensions*

*Strategy*. To do this we have to realize that the momentum in three dimensions
is a vector. So we have to write down a vector with three conponents. Each
component is defined like in A1.

*Answer*. The momentum opertor is given by

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

* A boldface symbol for \\( \B{p} \\) is used to represent a vector and therefore
  a boldface \\( \hat{\B{p}} \\) is vector of derivative operators, as you can see.

* The partial derivative symbol \\( \partial \\) is used whenever there is
  more than one variable involved - like in thermodynamics.

* Note that sometimes the \\( x \\), \\( y \\) and \\( z \\) coordinates
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
\right).
$$

*Strategy*. Substitute the definition of the 3D momentum operator in (Q2) into the
expression for \\( \B{l} \\).

*Answer*. The expression for the angular momentum operator is:

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

*Strategy*. Use rule 2 of quantum mechanics. Write down the eigenvalue equation
for the momentum operator of the elctron.

*Answer*. The allowed experimental values \\( a \\) of the electron momentum in one
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

*Answer*. The allowed experimental energies \\( E \\) are obtained by solving
the following eigenvalue equation,

$$
\hat{H} \psi(x) = E \psi(x).
$$

\\( \hat{H} \\) is the energy operator or *hamiltonian* for the
electron,

$$
  \hat{H} = \frac{\hat{p^2}{2m_e} = -\frac{\hbar^2}{2m_e}\frac{d^2}{dx^2}
$$

The right hand side is obtained by substituting \\( p = -i\hbar d/dx \\).
\\(x \\) and \\( m_e \\) are the position coordinate and mass of the electron,
respectively.

Note:
* To solve this equation to find the allowed energy values
  \\( E \\) means we usually have to first find the unknown wave function
  \\( \psi(x) \\).
* The hamiltonian as a negative sign in it. However it generally has a positive
  value (as energy should!) at any point in space because \\( d^2\psi/dx^2 \\)
  is usually negative; it is generally positive but not always positive everywhere.


**Q6**. *Write down the equation for the allowed energy levels of the hydrogen atom in one dimension.*

*Strategy*. We need to write down the total energy of an electron and a proton
in one dimension. The total energy is comprised of the kinetic energy of
each particle. Hence it depends on the momentum of the electron \\( p_e \\) and
the momentum of the proton \\( p_p \\). The total energy also depends of the
electrical attraction between the proton and the electron which depends
on the (inverse) distance between the two particles according to [Coulomb’s
Law](http://en.wikipedia.org/wiki/Electric_potential_energy#Electrostatic_potential_energy_of_one_point_charge).
The distance between the two particles involves the coordinates of the electron
and the proton, respectively \\( x_e \\) and \\( x_p \\).

*Answer*. The allowed energies \\( E \\) for an electron and proton moving in one
dimension are determined by the following eigenvalue equation:

$$
\hat{H} \psi(x_p,x_e) = E \psi(x_p,x_e)
$$

where \\( \hat{H} \\) is the total energy operator or Hamiltonian
for the system, given by

$$
\begin{alignat}{4}
\hat{H} & = \frac{p^2_p}{2m_p}
        & + \frac{p^2_e}{2m_e} 
        & + \frac{1}{4\pi\epsilon_0}\frac{1}{|x_p - x_e|} \\
        & = \underbrace{-\frac{\hbar^2}{2m_p}\frac{d^2}{dx_p^2}}_{\twonote{Kinetic energy}{of proton}} \ \
        &   \underbrace{-\frac{\hbar^2}{2m_e}\frac{d^2}{dx_e^2}}_{\twonote{Kinetic energy}{of electron}} \ \
        &   \underbrace{-\frac{1}{4\pi\epsilon_0}\frac{1}{|x_p - x_e|}}_{\twonote{Electron-nuclues}{attraction energy}}
\end{alignat}
$$


**Q7**. *Is the equation \\( \hat{P}^2 \psi = \hat{P}\psi \\) an eigenvalue equation?*

*Strategy*. Recall the definition of an eigenvalue equation. Compare it to
the above eigenvalue equation to see if they look similar.

*Answer*. Yes it is an eigenvalue equation! Since, if we set \\( \phi = \hat{P}\psi \\)
it can be written as \\( \hat{P}\phi = \phi = 1\phi \\). This is an eigenvalue
equation for \\( \phi \\) with eigenvalue equal to 1. Note that any old operator
will *not* obey such an equation i.e. such an operator \\( \hat{P} \\) must be
somewhat *special* ... if it even exists.

**Q8**. *Suppose we do an experiment for the total energy \\( E_0 \\) of a
particle and the wavefunction is \\( \psi_0 \\) after the experiment.
(i) What is the probability of measuring energy \\( E_0 \\) again, afterwards?
(ii) What is the probability of measuring a different energy \\( E_1 \\) afterwards? 
(iii) What is the average of many position measurements of the particle?
Assume that the particle is one dimensional.*

*Strategy*. For (i) refer to the last part of Rule 2 and note the normalization
condition. For (ii), the result depends on (i), see below. For (iii) see the last
part of Rule 2 and use the operator \\( x \\) for the particle pisition.


*Answer*.

(i) The probability of obtaining \\( E_0 \\) again is \\( |\int \psi^*_0 \psi_0|^2 \\).
But this is equal to 1 for a bound state by the normalization condition. So we 
would measure \\( E_0 \\) again the second time with probanility 1.

(ii) The probability of getting any other energy is zero since after the first
energy measurement, we always keep getting \\( E_0 \\). Note: this implies
that \\( |\int \psi^*_0 \psi_1|^2 = 0 \\), which can be proved to be true.
The proof is beyond the scope of this course, but relies on the fact that
the eigenvectors are orthogonal.

(iii) The position of a one dimensional particle is given by \\( x \\).
We could put a “hat” on this to indicate it is an operator but it may
be less confusing to leave it off. So the average of the psotion measurements
is \\( \expectation{x} = \int \psi_0 x \psi_0 \\)






