---
layout: post
title: "Molecular properties in the crystalline environment"
description: "Change in frequency and geometry, and dipole derivatives in crystals"
category: articles
tags: [crystals, X-ray structure, quatum chemistry, response properties, energy derivatives, force constants, dipole moment derivatives]
modified: 2014-11-04
image:
  feature: snowflakes.jpg
  credit: Snowflakest
comments: false
share: true
---

**Situation**

[Sajesh Thomas](https://www.socrates.uwa.edu.au/Staff/StaffProfile.aspx?Person=SajeshThomas)
posed these questions to me, based on his research directed by
[Mark Spackman](http://www.uwa.edu.au/people/mark.spackman).

* How can we estimate the vibrational frequencies of a molecule when it is
  embedded in a crystal?

* How much does the molecular geometry change from the gas phase?

* What other properties can we calculated for the embeded molecule?



**Context**

The electron density distribution (EDD) had been derived for several
[host-guest complexes](http://en.wikipedia.org/wiki/Host%E2%80%93guest_chemistry)
via X-ray diffraction. From this EDD, Sajesh could calculate the
electrostatic potential and the electic fields at any point in the crystal ---
including at sites within the embedded molecule.

**Initial approach**

Sajesh’s approach was to optimize the geometry of the molecule in the presence
of these experimentally derived fields using a
[quantum chemistry](http://en.wikipedia.org/wiki/Quantum_chemistry) program such
as [Gaussian](http://www.gaussian.com/). But the problem was that, one the
fields were applied, the molecule would rotate out of its experimentally
determined position.

**Solution**

During beers last Friday night we came up with a solution based on a Taylor
expansion of the energy. Using the quantum chemistry programs to obtain various
energy derivatives, the outcome is that we can estimate

* The gas-phase molecular geometry
* The change in the force constants due to the external electric fields
* The molecular dipole moment derivatives (with additional assumptions)

## Notation

In order to understand the solution some notation has to be introduced.

The most important quantity is the generalized molecular potential
energy surface \\( E(\B{R},\B{F}) \\):

* \\( \B{R} = (R\sub{I\alpha}) \\) are the nuclear coordinates
* \\( \B{F} = (F\sub{I\alpha}) \\) are the external electric fields
* Capital roman letters \\( I, I=1\ldots N\sub{n} \\) refer to atom indices
* Greek letters \\(\alpha \\) are cartesian coordinates

The coordinates \\(\color{red} \B{R}^c \\) and fields \\( \color{red}\B{F}^c \\) refer
refer to experimental in-crystal cooordinates and fields, respectively.
Note that below we will always use:

* \\( \color{red}\textrm{red for experimental data} \\),

* \\( \color{green} \textrm{green for quantum chemical data} \\).

The coordinates \\( \B{R}^e \\) refers to gas phase equilibrium coordinates
and are to be determined.

To make the Taylor expansions less cluttered understand a
[repeated index summation convention](http://en.wikipedia.org/wiki/Einstein_notation) 
is used.

For the same reason, partial derivative symbols are eliminated, as follows:

* Positional derivatives of the molecular energy \\( E \\) are written as

$$
\begin{align}
{\color{green}E\sub{I\alpha}}
& =
\frac{\partial E}{\partial R\sub{I\alpha}} 
& & {\onenote{Gradient/Force}}
\\
{\color{green}E\sub{I\alpha J\beta}}
& =
\frac{\partial^2 E}{\partial R\sub{I\alpha}\partial R\sub{J\beta}}
& & {\small\onenote{Force constants}, \B{f} = ( E\sub{I\alpha J\beta}} ) .
\\
{\color{green}E\sub{I\alpha J\beta K\gamma}}
& =
\frac{\partial^3 E}{\partial R\sub{I\alpha}\partial R\sub{J\beta} \partial R\sub{K\gamma}}
& & \onenote{Cubic force constants}
\end{align}
$$

* Derivatives involving one electric field are dipole moment derivatives:

$$
\begin{align}
{\color{green}\mu\sub{\delta}}
& =
- \frac{\partial E}{\partial F\sub{\delta}}
& & {\small\onenote{Dipole moment}, \B{\mu} = (\mu\sub{\delta})}
\\
{\color{green}\mu\sub{\delta, I\alpha}}
& =
- \frac{\partial^2 E} {\partial F\sub{\delta} \partial R\sub{I\alpha}}
& & \twonote{Dipole moment derivative}{Atomic polar tensor}
\\
{\color{green}\mu\sub{\delta, I\alpha J\beta}}
& =
- \frac{\partial^3 E}{\partial F\sub{\delta} \partial R\sub{I\alpha} \partial R\sub{J\beta}}
& & \onenote{Dipole moment second derivative}
\end{align}
$$

* Derivatives involving two electric fields are polarizability derivatives:

$$
\begin{align}
{\color{green}\alpha\sub{\delta\epsilon}}
& =
- \frac{\partial^2 E}{\partial F\sub{\delta}F\sub{\epsilon}}
& & {\small\onenote{polarizability}, \B{\alpha} = (\alpha\sub{\delta\epsilon})}
\\
{\color{green}\alpha\sub{\delta\epsilon, I\alpha}}
& =
- \frac{\partial^3 E} {\partial F\sub{\delta} \partial F\sub{\epsilon} \partial R\sub{I\alpha}}
& & \onenote{Polarizability derivative}
\end{align}
$$

*Importantly, all of these quantities may be evaluated using quantum chemistry
program packages, if not directly, then by using finite differences*.

Some of these quantities may also be estimated from experimental information
using the input of quantum chemical information --- the essence of the
original approach to the problems.


## Gas phase structure from crystal

We expand \\( E\sub{I\alpha}({\color{red}\B{R}^c},{\color{red}
\B{F}^c}) \\) around the gas phase geometry with zero field,

$$
\underbrace{E\sub{I\alpha}(\B{R}^e,\B{0})}\sub{\B{0}}
- {\color{green}\mu\sub{\delta, I\alpha}}(\B{R}^e,\B{0}) {\color{red} F^c\sub{\delta}}
+ {\color{green}E\sub{I\alpha J\beta}}(\B{R}^e,\B{0})
  ({\color{red}R^c\sub{J\beta}}-R^e\sub{J\beta})
= 0.
$$

The first term on the LHS is zero because it is the gradient at the equilibrium
geometry. The last term on the LHS is the cartesian force constant matrix at the
equilibrium geometry. This term, and the second term, the dipole moment derivatives,
may be obtained from *ab initio* caculations, so are colored green. Therefore
these are \\( 3N\sub{n}\times 3N\sub{n} \\) linear equations for the gas phase
equilibrium geometry,

$$
\boxed{
  {\color{green}\mu\sub{\delta, I\alpha}}(\B{R}^e,\B{0}) {\color{red} F^c\sub{\delta}}
+ {\color{green}E\sub{I\alpha J\beta}}(\B{R}^e,\B{0}) {\color{red}R^c\sub{J\beta}}
= {\color{green}E\sub{I\alpha J\beta}}(\B{R}^e,\B{0})
  R^e\sub{J\beta}
}
$$

Note that we could have chosen to expand around the experimental geometry.
We chose to use the gas pjase geometry because quantum chemistry methods
are much better validated under these conditions.

## Change in the harmonic frequency

To evaluate the change in the harmonic frequency we need to estimate the force
constant matrix at the crystal geometry when external fields are applied, i.e.
we need \\( E\sub{I\alpha J\beta}({\color{red}\B{R}^c},{\color{red}\B{F}^c})\\)
which may be evaluated by the following expansion

$$
\boxed{
E\sub{I\alpha J\beta}({\color{red}\B{R}^c},{\color{red}\B{F}^c})
=
{\color{green}E\sub{I\alpha J\beta}}({\color{red}\B{R}^c},\B{0})
+
{\color{green}\mu\sub{\delta,I\alpha J\beta}}({\color{red}\B{R}^c},\B{0})
{\color{red} F^c\sub{\delta}}
}
$$

Note that the actual force constants involve coupling terms between the
atom coordinates of the embedded molecule and those in the environment.
Therefore the above formula is only a best first-order approximation for
treating the molecule as a separate entity in the crystal. Intuitively
one might expect that the lower frequency modes to be most affected
by these separability considerations.

## Dipole derivatives from local fields

The molecular dipole moment derivatives are fundamental molecular
properties related to the intensities for fundamental vibrational
transitions. The following argument shows that they are related
directly to the local crystal fields.

By definition a molecule in the crystal is at a stationary point i.e.
there are no forces on its nuclei,

$$
E\sub{I\alpha}({\color{red}\B{R}^c},{\color{red} \B{F}^c}) = 0.
$$

Expanding the left hand side in a Taylor series around the crystal
geometry at zero field strength gives,

$$
\boxed{
{\color{green}E\sub{I\alpha}}({\color{red}\B{R}^c},\B{0})
- \mu\sub{\delta, I\alpha}({\color{red}\B{R}^c},\B{0}) {\color{red} F^c\sub{\delta}} = 0.
}
$$

These are \\( 3 N\sub{n} \\) equations in the \\( 9 N\sub{n} \\) unknown molecular
dipole moment derivatives \\( \mu\sub{\delta, I\alpha}(\B{R}^c,\B{0}) \\).
(Note that the dipole derivatives here pertain to the *experimental crystal
geometry* not to the gas phase). Therefore it is not possible to determine
these quantities  from a single experiment unless some of the unknown
coefficients are known to be zero by symmetry --- for example the molecule is
linear or uncharged.

### ... Reduction in the number of unknowns

Actually, there are only \\( 9 N\sub{n} - 6 \\) unknown molecular dipole moment
derivatives (or \\( 9 N\sub{n} - 5 \\) for linear molecules) as the following
argument shows.

For an uncharged molecule the dipole moment does not depend on the coordinate
system i.e. \\( \B{\mu}(\B{R},\B{F}) = \B{\mu}(\B{R}+\B{\Delta},\B{F}) \\)
where \\( \B{\Delta} \\) is a constant shift applied to all nuclear
coordinates. From this we can deduce the relation

$$
\sum\sub{I=1}^{N_n} \mu\sub{\delta,I\alpha} = 0
$$

which provide three extra conditions on the dipole moment derivatives.
A further three conditions could also be obtained (two for linear molecules)
if the dipole moment of the molecule is known.

These conditions should not be used if the molecule has acquired a charge.

In order to determine the dipole moment derivatives some additional models
are required to reduce the number of unknowns. 

### ... Local charge model for dipole derivatives

Suppose that the dipole moment in the molecule at different geometries is well
modelled by fixed atomic charges \\( q_I \\) at each atomic site \\( I \\),

$$
\mu\sub{\delta} = \sum\sub{I=1}^{N_n} q_I R\sub{I\delta}.
$$

This is not a good model because it does not account for the change
in the charges with change in geometry. Such charges are also called
[Born effective charges](http://quantumwise.com/documents/tutorials/latest/Polarization/index.html/chap.born.html#sect1.born.theory). 
Nevertheless, it is straightforward to
show that the atomic charges in this may be approximated at the trace of of the
dipole moment derivatives, which in this case are better known as the
[atomic polar tensors](http://dx.doi.org/10.1063/1.1681972),

$$
q\sub{I}^2 = \frac{1}{9} \mu\sub{\delta,I\alpha} \mu\sub{\delta,I\alpha}.
$$

The important thing to note is that this model reduces the number of unknown
dipole derivatives to just \\( N_n \\) effective charges \\( q\sub{I} \\). With
the translational and rotational conditions on the dipole derivatives, we now
have an *overdetermined systems of equations* which can be solved by least
squares. Without the translation and rotational constraints these equations read:

$$
\boxed{
\B{q}
=
\textrm{argmin}\sub{\B{q}}\,
\displaystyle\sum\sub{I}
\vert {\color{green}\B{E\sub{I}}}({\color{red}\B{R}^c},\B{0}) - q\sub{I} {\color{red} \B{F}^c} \vert^2.
}
$$

### ... Are the local fields reasonable?

This can easily be tested by evaluating how different the predicted and
actual forces are at the nuclear centers,

$$
\boxed{
{\color{green}E\sub{I\alpha}}({\color{red}\B{R}^c},\B{0})
\stackrel{\small ?}{=}
{\color{green}\mu\sub{\delta, I}}({\color{red}\B{R}^c},\B{0}) {\color{red} F^c\sub{\delta}}
}
$$


## Acknowledgement

These notes grew directly out of a conversation with Sajesh Thomas
and Marcus Kettner.

Some of the ideas go back to a memorable conversation with
[Kersti Hermansson](http://www.teoroo.kemi.uu.se/wp/?doing_wp_cron=1415592936.3213880062103271484375)
at the third European Charge Density Meeting (ECDM) conference in
[Sandbjerg Estate](http://en.wikipedia.org/wiki/Sandbjerg), where apart from
this we discussed the islands around Stockholm in the summer. 

Of course, all of this is based on the ideas of
[A. David Buckingham](http://dx.doi.org/10.1002/9780470143582.ch2), the
master of molecular properties.









