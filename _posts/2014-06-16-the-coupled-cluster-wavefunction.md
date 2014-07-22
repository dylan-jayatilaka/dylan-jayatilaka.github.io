---
layout: post
title: "The coupled cluster wavefunction"
description: "The coupled cluster wavefunction"
category: articles
tags: [Coupled cluster, exponential ansatz, size extensivity, separability]
modified: 201-06-07
image:
  feature: regina-valluzzi-transition-to-chaos.jpg
  credit: Regina Valluzzi - Transition to Chaos
  creditlink: http://nerdlypainter.blogspot.com.au/2011/03/archive-february-newsletter-featuring.html
comments: false
share: true
---

The coupled cluster wavefunction provides one of the best general-purpose
approximation schemes for the exact wavefunction.

The coupled cluster wavefunction in an orthonormal basis has the form

$$
\begin{align}
\Psi & = e^{T} \Phi  \\
     & = (1 + T + \textstyle{\frac{1}{2}}T^2 + \textstyle{\frac{1}{6}}T^3 + \ldots) \Phi.
\end{align}
$$

In the above equation:

* \\( \Phi \\) is called the reference determinant, usually taken to be
  the Hartree-Fock determinant.

* The exponential function is expanded in a power series.

* The operator \\( T = \sum_{n=1}^{N} T_n \\) is a sum of excitation operators 
  \\( T_n \\) which for \\( n = 1,2,3,\ldots \\) successively produce
  single, double, triple \\( \ldots \\) replacements of the “occupied”
  spinorbitals in determinant \\( \Phi \\) with new “unoccupied” or “virtual”
  spinorbitals, like this:

$$
T_n \Phi
=
\frac{1}{(n!)^2}
\sum\sub{I\sub{1}\,\ldots\, I\sub{n}}^{N\sub{o}}
\sum\sub{A\sub{1}\,\ldots\, A\sub{n}}^{N\sub{v}}
   t\sub{\, I\sub{1}\,\ldots\, I\sub{n}}^{A\sub{1}\,\ldots\, A\sub{n}}
\Phi\sub{\, I\sub{1}\,\ldots\, I\sub{n}}^{A\sub{1}\,\ldots\, A\sub{n}}
$$

* The quantities \\( t\sub{\, I\sub{1}\,\ldots\, I\sub{n}}^{A\sub{1},\ldots,A\sub{n}} \\)
  are called the cluster amplitudes and are the unknowns to be determined.


* The operators \\( T_1 \\), \\( T_2 \\), \\( T_3 \\), \\(\ldots \\) commute with each other.

* The coupled cluster wavefunction above is exact if an infinite and complete
  set of orbitals is used i.e. if \\( N_v \\) is infinite.

## Coupled cluster approximation schemes

An obvious approximation scheme is (apart from using a finite basis set) to limit
the number of excitation operators \\( T_n \\) used in the expansion of \\( T \\).

In this way we get the following approximations:

* Coupled cluster singles (CCS) if \\( T = T_1 \\). 

  - If the reference \\( \Phi \\) is taken to be a Hartree-Fock determinant
    (either for the ground or excited state) then this yields 
    \\( t_I^A = 0 \\). In other words there is only a trivial solution for the
    CCS equations if the Hartree-Fock determinant is the reference. 
  
  - If the reference determinant is not the Hartree-Fock solution, the energy
    obtained will be higher. (Below I describe how the coefficients are
    determined).


* Coupled cluster doubles (CCD) if \\( T = T_2 \\)

* Coupled cluster singles and doubles (CCSD) if \\( T = T_1 + T_2 \\)

* Coupled cluster singles, doubles and triples (CCSDT) if \\( T = T_1 + T_2 + T_3 \\)

* Coupled cluster singles, doubles, triples and quadruples (CCSDTQ) if \\( T = T_1 + T_2 + T_3 + T_4 \\)

## Finding the coupled cluster energy and amplitudes

To obtain the coupled cluster energy we substitute the corresponding
wavefunction *ansatz* into the Schrodinger equation,

$$
H e^T \Phi = E \Phi.
$$

Then we project or integrate this equation on the left with successively
different subsituted determinants,

$$
\begin{align}
\braket{\Phi}{          H e^T \Phi} & = E \\
\braket{\Phi_I^A}{      H e^T \Phi} & = 0 \\
\braket{\Phi\sub{IJ}^{AB}}{H e^T \Phi} & = 0 \\
\ldots &
\end{align}
$$

The substituted determinants on the left are called “excited determinants” if
the state \\( \Phi \\) is the grouds state Hartree-Fock determinant.
The first and higher exictated determinants yield zero on the right hand side
because the determinants with different spin orbitals in them are orthogonal.

The most important thing to note is that if \\( T_n \\) is limited to a certain
level of excitations, then we only need to project on the left hand side with
determinants to the same level of excitation. This provides a set of non-linear
equations which determine the amplitude coefficients and the first equation
above provides an equation for the energy \\( E \\). Thus if we had 
\\( T_n = T_2 \\) S only the double excited determinant equation above would be
required.

Of course we have to evaluate the rather complex matrix elements in these
equations before obtaining a set of equations which are actually “programmable”
in terms on integrals, but this is just an (important) technicality. 

## Coupled cluster transformed Hamiltonian

There is an equivalent way to find the energy and the amplitudes, and it
involves premultiplying the Schrodinger equation by \\( e^{-T} \\) beforehand,
yeilding the equations

$$
\begin{align}
\braket{\Phi}{    e^{-T}H e^T \Phi} & = E \\
\braket{\Phi_I^A}{e^{-T}H e^T \Phi} & = 0 \\
\braket{\Phi\sub{IJ}^{AB}}{e^{-T}H e^T \Phi} & = 0 \\
\ldots &
\end{align}
$$

It is a rather remarkable fact that the coupled cluster transformed Hamiltonian
\\( \tilde{H} = e^{-T}H e^T \Phi \\) can be evaluated in closed form. We will
have another post on this rather amazing fact.

## The elephant in the room: Why is an exponential function used?

<figure>
   <img src="/images/elephant-in-the-room.jpg">
</figure>

The reason is that the energy of the coupled cluster wavefunction separates
into a sum of subsystem energies when those systems are noninteracting i.e.

$$
E[\Psi] = E_A[\Psi_A] + E_B[\Psi_A].
$$

This is called *size extensivity*. It implies that, for instance, the energy of
\\( n \\) hydrogen molecules separated by a very large distance from each other
will be equal to \\( n \\) times the energy of a single hydrogen molecule. This
is clearly a very useful property to have!

As stated, size extensivity follows from the exponential form of the wavefunction,

$$
\begin{align}
\Psi & = e^{T} \Phi \\
     & = e^{T_A+T_B} \Phi \\
     & = e^{T_A}e^{T_B}\Phi
\end{align}
$$

The final line follows from the fact that the excitation operators
\\( T_A \\) and \\( T_B \\) operate on different sets of orbitals --
those from the two separate systems -- and so the operators commute.
Now if the Hamiltonian splits into two parts for the subsystems,
\\( H = H_A + H_B \\) antisymmetrization between the Hartree
orbitals products can be ignored so that \\( \Phi \approx \Phi_A\Phi_B \\).
This last point is a litlle bit tricky and I should write another post
about it since it brings up interesting points about the
Einstein-Poldolsky-Rosen (EPR) paradox. But if we assume that it holds,
then it implies that

$$
\begin{align}
\Psi & = e^{T_A}e^{T_B}\Phi \\
     & \approx e^{T_A}e^{T_B}\Phi_A\Phi_B \\
     & = e^{T_A}\Phi_A e^{T_B}\Phi_B \\
     & = \Psi_A \Psi_B
\end{align}
$$

The *additivity* of the total energy follows from the *multiplicative*
factorization of \\( \Psi \\) above.

## Why isn’t separability built into QM?

Since the product form of the wavefunction is so essential to the separability
of the wavefunction, I wonder why this behaviour isn’t in some way “built
into” quantum mechanics from the start? After all, the fermion symmetry is
built into the determinant form of the wavefunction; or equivalently,
in second quantization, this same symmetry is built into the anticommutation
relations of the fermion creation and annihilation operators.

Perhaps, dear reader, you might like to think about this. Those who are brave
may attempt to the paper by Arponen (1997) PRA 55 pl 2686 where he attempts
to do just that. If you understand it please explain!

