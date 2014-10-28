---
layout: post
title: "Super quick summary of Quantum Mechanics"
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

The purpose of this post is to write down briefly the main ideas and Rules of
Quantum mechanics.

<figure>
   <img src="/images/rembrandt-moses-with-the-ten-commandments.jpg">
</figure>

Quantum mechanics is hard for two reasons. First, the ideas are strange.
Second, it involves mathematics which is probably new to you. The double
whammy is a killer.

Still, some of you may find quantum mechanics intriguing. If so, you would not
be alone. People still
[argue about it today](http://dylan-jayatilaka.net/articles/quantum-theory-is-wrong/)
even after a hundred years.

## Why?

A common question that is encountered is “Why do I need to know about QM?” or
more briefly “So what?”.

Here is the answer for chemists.

You need to understand how quantum mechanics works because quantum
mechanics allows you to calculate everything about chemistry
(molecular properties, reaction rates) from equations [without having to do
experiments](http://www.brainyquote.com/quotes/quotes/p/pauldirac279318.html).

That’s big.

I reckon these days every organic chemist should do a simple QM calculation to
test out their reaction schemes before going into the lab for some pain. Of
course, these QM calcs are done on a computer - not with pen and paper. So you
could just learn to use the program. But in that case you would have no idea
how the calculations work i.e. you will be just a monkey. No one wants to
employ a monkey. (We *will* teach you how to use these programs in third year).

<figure>
   <img src="/images/small-thoughtful-bonobo.jpg">
</figure>

## Chill

Now I know you probably have not seen quantum mechanics before. Probably
you are freaking out. I want to say: Don’t Worry. QM is hard - but not *that* hard.
Just remember: contrary to what you might have thought, you don’t yet know
everything. You have to learn more. It’s normal to feel that way with new
stuff. So relax. Afterwards, see if you can follow the questions and answers
below. If you’re still confused come and see me.

Let’s get started.

## The hyperphysics web site

A really great web site which takes the standard historical story of QM and
uses the concept-map idea - and incidentally covers nearly exactly the same
material as our Phys Chem QM lectures - can be found
[here](http://hyperphysics.phy-astr.gsu.edu/hbase/quacon.html#quacon).
Do take a [click](http://hyperphysics.phy-astr.gsu.edu/hbase/quacon.html#quacon).

On the other hand, if you keep reading, we skip all that historical
guff and get straight into it.

## The Rules of Quantum Mechanics

There are only few rules to quantum mechanics.

But the rules do require some explanation, as you see!

1. **The state of a system is described by a wavefunction**

   - The wavefunction is a [function](http://en.wikipedia.org/wiki/Function_(mathematics)) 
     of the coordinates of the particles in the system. It is usually given the
     symbol \\( \psi \\)

   - \\( \psi \\) must be continuous i.e. have no “gaps” in it

   - The derivative of \\( \psi \\) must also be continuous i.e. the
     wavefunction must be smooth (except at points where the interaction energy
     becomes infinite - so called singularities)

   - \\( \psi \\) for bound ie. stable states must be
     [normalizable](http://hyperphysics.phy-astr.gsu.edu/hbase/quantum/qm.html#c5)
     i.e. \\( \int |\psi|^2 \\) must exist and must equal one; this is called
     normalization of the wavefunction. The reason is that \\( |\psi(\B{x})|^2 \\)
     is the probability of finding the particles at given positions \\(\B{x}\\).

2. **Any experimental measurement is represented by an operator**

   - An [operator](http://en.wikipedia.org/wiki/Operator_(physics)#Linear_operators_in_wave_mechanics)
     is a function of the coordinates and momenta of the particles in the
     system.

   - The momenta (which in classical mechanics is written as \\( \B{p} \\) and is equal
     to mass times velocity \\(\B{p} = m\B{v}\\)) is in quantum mechanics equal to a derivatives
     with respect to the particle coordinates times \\( i\hbar \\) (where
     \\( \hbar \\) is Planck’s constant divided by \\( 2\pi \\) )
     i.e. in quantum mechanics:

     $$
     \boxed{
     \hat{p} = -i\hbar \displaystyle\frac{d}{dx} \ \ldots \ \textrm{in 1 dimension}
     }
     $$

     This is very different to classical mechanics!

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
     where \\( \hat{H} \\) is the total energy operator or
     [Hamiltonian](http://en.wikipedia.org/wiki/Hamiltonian_(quantum_mechanics)#The_Schr.C3.B6dinger_Hamiltonian)
     of the system:

     $$
     \hat{H} = \underbrace{\sum_i \displaystyle\frac{\hat{p}_i^2}{2 m_i}}_{\twonote{Kinetic energy}{of all particles $i$}}
             + \underbrace{V(\B{x}_1,\B{x}_2,\ldots)}_{\twonote{Potential energy }{of all particles}}
     $$

     The potential energy \\( V \\) depends on the positions and perhaps
     also the momenta of all the particles. It has to be specified to you for
     each problem.

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

**Q0**. *What are the main differences between classical mechanics and quantum mechanics?*

*Answer*

In classical mechanics every particle e.g. like an electron, proton, neutron
has a definite position and a velocity. The way a classical particle moves is
calculated by using
[Newton’s Laws](http://en.wikipedia.org/wiki/Newton’s_laws_of_motion). On the
other hand, in quantum mechanics, particles usually *do not* have a definite
position or velocity. That means in quantum mechanics “particles” are
notparticles at all! They are *spread out* and *distributed* in space in some
way.

<figure>
   <img src="/images/particles-vs-waves.jpg">
</figure>

We can think of quantum particles as little wiggly waves. Such waves do *not*
usually have a definite position. In order to describe the shape of these
wiggly waves we need to use a *function* - specifically a *wavefunction*. An
example might be \\( \psi(x) = \sin x \\). Plotting out this function on a
graph shows the wiggly wave of the quantum particle. The wavefunction describes
everything you can know about the quantum particle. The Schrodinger equation
tells us the shape of the wavefunction which has a definite energy.
Compare this again to a classical particle which can be
descibed by only *six numbers* : three coordinates \\(x \\), \\( y\\) and
\\(z\\) and three velocities \\(v_x\\), \\(v_y\\), and \\(v_z\\). By contrast,
a quantum mechanical particle requires an *infinite number of numbers to
describe it* since it requires the whole shape of the wavefunction in the plotted
graph to be tabulated for you. Either that, or you have to write a mathematical
function such as \\( \psi(x) = \sin x \\) to describe its shape. That’s why
the Schrodinger equation is not a normal equation but a 
[differential equation](http://en.wikipedia.org/wiki/Differential_equation):
this type of equation determines the *shape* of a function, unlike a normal
*algebraic* equation which just uses *numbers* not *functions*.

**Q1**. *Write down the momentum operator of an electron in one dimension*

*Strategy*

Use Rule 1 of quantum mechanics.

*Answer*

The momentum operator of an electron in one dimension is
\\( \hat{p} = -i\hbar \displaystyle\frac{d}{dx} \\).


**Q2**. *Write down the momentum operator of an electron in three dimensions*

*Strategy*

To do this we have to realize that the momentum in three dimensions is a
vector. So we have to write down a vector with three conponents. Each component
is defined like in Q1.

*Answer*

The momentum operator is given by

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

Note:

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

* Even more briefly we can write 

  $$ \hat{\B{p}} = -i \hbar \B{\nabla} $$

  The upside down triangle is called [nabla](http://en.wikipedia.org/wiki/Del) 
  and stands for the vector of derivatives in the three directions, as 
  already written above.

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

*Strategy*.

Substitute the definition of the 3D momentum operator in (Q2) into the
expression for \\( \B{l} \\).

*Answer*

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

*Strategy*

Use Rule 2 of quantum mechanics. Write down the eigenvalue equation
for the momentum operator of the electron.

*Answer*

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

*Strategy*

To do this question we need the formula for the energy in terms of the free
electrons position and momentum. Luckily that is given to us. Next we do the
usual substitution for the electron momentum. Then we use Rule 2 and write down
the eigenvalue equation.

*Answer*

The allowed experimental energies \\( E \\) are obtained by solving the
following eigenvalue equation,

$$
\hat{H} \psi(x) = E \psi(x).
$$

\\( \hat{H} \\) is the energy operator or *Hamiltonian* for the
electron,

$$
\hat{H} = \frac{\hat{p}^2}{2m_e} = -\frac{\hbar^2}{2m_e}\frac{d^2}{dx^2}
$$

The right hand side is obtained by substituting \\( p = -i\hbar
\displaystyle\frac{d}{dx} \\) and \\(x \\) and \\( m_e \\) are the position
coordinate and mass of the electron, respectively.

Note:

* To solve this equation to find the allowed energy values
  \\( E \\) means we usually have to first find the unknown wave function
  \\( \psi(x) \\).

* The Hamiltonian has a negative sign in it. However it’s value  is generally
  positive (as energy should be) at any point in space because
  \\( d^2\psi/dx^2 \\) is usually negative; it is generally positive but
  not *always* positive everywhere.


**Q6**. *Write down the equation for the allowed energy levels of the hydrogen
atom in one dimension. Assume that \\( V(x) \\) is given by the [electrostatic potential energy](http://en.wikipedia.org/wiki/Electric_potential_energy#Electrostatic_potential_energy_of_one_point_charge).*

*Strategy*

We need to write down the total energy of an electron and a proton in one
dimension. The total energy is comprised of the sum of the kinetic energy of
each particle. Hence it depends on the momentum of the electron \\( p_e \\) and
the momentum of the proton \\( p_p \\). The total energy also depends of the
electrical attraction between the proton and the electron which depends
on the (inverse) distance between the two particles according to
[Coulomb’s Law](http://en.wikipedia.org/wiki/Electric_potential_energy#Electrostatic_potential_energy_of_one_point_charge)
as stated in the problem. The distance between the two particles is
\\( |x_p - x_e| \\) and involves the coordinates of the electron and the
proton, respectively \\( x_e \\) and \\( x_p \\).

*Answer*

The allowed energies \\( E \\) for an electron and proton moving in one
dimension are determined by the following eigenvalue equation:

$$
\hat{H} \psi(x_p,x_e) = E \psi(x_p,x_e)
$$

where \\( \hat{H} \\) is the total energy operator or Hamiltonian
for the system, given by

$$
\begin{alignat*}{5}
\hat{H} & = \frac{p^2_p}{2m_p}
      & & + \frac{p^2_e}{2m_e}
        & + \frac{1}{4\pi\epsilon_0}\frac{1}{|x_p - x_e|} \\
        & = \underbrace{-\frac{\hbar^2}{2m_p}\frac{d^2}{dx_p^2}}_{\twonote{Kinetic energy}{of proton}} \ \
      & &   \underbrace{-\frac{\hbar^2}{2m_e}\frac{d^2}{dx_e^2}}_{\twonote{Kinetic energy}{of electron}} \ \
        &   \underbrace{-\frac{1}{4\pi\epsilon_0}\frac{1}{|x_p - x_e|}}_{\twonote{Electron-nuclues}{attraction energy}}
        \\
\end{alignat*}
$$


**Q7**. *Is the equation \\( \hat{P}^2 \psi = \hat{P}\psi \\) an eigenvalue equation?*

*Strategy*

Recall the definition of an eigenvalue equation. Compare it to
the above eigenvalue equation to see if they look similar.

*Answer*

Yes it is an eigenvalue equation! Since, if we set \\( \phi = \hat{P}\psi \\)
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

*Strategy*

For (i) refer to the last part of Rule 2 and note the normalization
condition. For (ii), the result depends on (i), see below. For (iii) see the last
part of Rule 2 and use the operator \\( x \\) for the particle position.


*Answer*

(i) The probability of obtaining \\( E_0 \\) again is \\( |\int \psi^\ast_0 \psi_0|^2 \\).
But this is equal to 1 for a bound state by the normalization condition. So we
would measure \\( E_0 \\) again the second time with probability 1. This is
interesting. It says that once the first measurement is done the second
measurement keeps the wavefunction in the same state. This is known as
the [quantum Zeno effect](http://en.wikipedia.org/wiki/Quantum_Zeno_effect)
and it has been shown experimentally to be true.

(ii) The probability of getting any other energy is zero since after the first
energy measurement, we always keep getting \\( E_0 \\). Note: this implies
that \\( |\int \psi\sub{0}^\ast(x) \psi_1(x) dx|^2 = 0 \\), which can be proved to be true.
The proof is beyond the scope of this course, but relies on the fact that
the eigenvectors are orthogonal.

(iii) The position of a one dimensional particle is given by\( x \\).
We could put a “hat” on this to indicate it is an operator but it may
be less confusing to leave it off. So the average of the position measurements
is \\( \expectation{x} = \int \psi_0(x)\, x\, \psi_0(x) dx \\)






