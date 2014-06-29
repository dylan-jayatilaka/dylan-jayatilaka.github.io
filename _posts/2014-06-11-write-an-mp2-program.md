---
layout: post
title: "Write an MP2 program"
description: "programming, quantum chemistry, MP2"
category: articles
tags: [programming, MP2, quantum chemistry, Foo]
modified: 201-06-07
image:
  feature: so-simple-sample-image-3.jpg
  credit: Michael Rose
  creditlink: http://mademistakes.com
comments: false
share: true
---

First some theory.

Well, not theory but the relevant formulas.

According to Head-Gordon, Pople and Frisch (1988) CPL 153 p. 503 the formula
for the MP2 correlation energy is

$$
E_\textrm{MP2} =
\frac{1}{2}
\sum_{i,j,a,b}
\frac{2(ia|jb)^2 + [(ia|jb)-(ib|ja)]^2}{\epsilon_i + \epsilon_j - \epsilon_a - \epsilon_b}.
$$

Here the \\( \epsilon_p \\) are molecular orbital energies, 
and the indices \\( i \\) and \\( j \\) stand for 
occupied molecular orbitals \\( \phi_i \\) and \\( \phi_j \\), 
while indices \\( a \\) and \\( b \\) stand for unoccupied orbitals
\\( \phi_a \\) and \\( \phi_b \\). The two electron integrals are

$$
(pq|rs) = \int \phi_p(1)\phi_q(1) r_{12}^{-1} \phi_r(2) \phi_s(2)
$$

These are obtained from the atomic orbital integrals \\( (\mu\nu|\kappa\lambda) \\)
through a “four index transform”

$$
(pq|rs) = 
\sum_{\mu,\nu,\kappa,\lambda}
          (\mu\nu|\kappa\lambda) c_{\mu p} c_{\nu q} c_{\kappa r} c_{\lambda s}.
$$

The coefficients \\( \textbf{c} \\) are the matrix of the molecular orbital
coefficients in the atomic orbital basis while. It seems we don’t actually need
these if we have the corresponding molecular orbital energies.

## Get ready

To write the program we need to locate where the integrals are. In a
typical program made by scientists there is no “integrated development
environment”. Therefore in unix you would use the `grep` command with the
word `integral` in the `foofiles/` source directory. If you try that you will
get a lot of output. On reflection this is unreasonable: much of quantum
chemistry has to do with integrals. The output can be “pioed”
through the `less` pager

````
   cd foofiles
   grep integral | less
````

After searching you come across the routines `.FOCK:make_ERI_integrals(v)`.
Investigating further in the `molecule.fock.foo` file we see from the
documentation that this `v`  is declared as a a four dimensional array 
`v :: MAT4{REAL}` 

```

   make_MO_ERI_integrals(v)
   ! Calculate "v" the electron repulsion integrals (ERI's) in the MO basis
     v :: MAT4{REAL}, OUT
     ...
```

Clearly `v` holds the two electron electron repulsion integrals (ERIs).
()In a practical program there would be too many of these integrals to
hold in an array, but we do it here just for teaching purposes).

## Housekeeping

In a perfect world we would expect to call the routine above, just as we
did in the in the “Hello World” program. The routine would simply work and
returned the integrals. If we *actually* do that, our program will crash. 

Why?

Because there is some “set-up” to do. For example, 

* What molecule do we want to treat? 

* What basis set do to use? 

* We should do an SCF calculation beforehand for the orbitals and energies!
  ()If you are reading previous posts, you may recall that the orbital energies
  are stored in a variable `orbital_energies`).

So we want to add our MP2 calculation program to the end of a standard SCF calculation. 
We can find an appropriate input file from the tests/` folder. The test job in folder
`h2o_rhf_cc-pVDZ` is fine. The `stdin` file from this folder can be copied to the
`tonto` folder or wherever you want to` run the program.

## Starting to write

To write the program it is always good to have a starting template.
Since we actually need to run an SCF calculation beforehand we shouldwe should start by modifying the
`run_molecule.exe` program. That, of course is in the `run_molecule.foo` file.

So we start by adding our code to the end of that program. We should probably rename in to
something like `run_molecule_mp2.foo` before starting.

## The Answer

At this point I should give you answer. 

But perhaps you can do this as an exercise?






