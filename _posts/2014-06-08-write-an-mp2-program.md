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

According to Head-Gordon et al (1988) the formula for the MP2 correlation
energy is

$$
E_\textrm{MP2} = 
\frac{1}{2}
\sum_{ijab}
\frac{2(ia|jb)^2 + [(ia|jb)-(ib|ja)]^2}{\epsilon_i + \epsilon_j - \epsilon_a - \epsilon_b}
$$

In the above the $\epsilon_p$ are molecular orbital energies, and the indices
$i$ and $j$ stand for occupied molecular orbitals $\phi_i$ and $\phi_j$, while $a$ and
$b$ stand for unoccupied orbitals $\phi_a$ and $\phi_b$. The two electron
integrals are

$$
(pq|rs) = \int \phi_p(1)\phi_q(1) r_{12}^{-1} \phi_r(2) \phi_s(2)
$$

These are obtained from the atomic orbital integrals \\( (\mu\nu|\kappa\lambda) \\) 
through a four index transform

$$
(pq|rs) = \sum_{\mu\nu\kappa\lambda}
          (\mu\nu|\kappa\lambda) c_{\mu p} c_{\nu q} c_{\kappa r} c_{\lambda s}
$$

The coefficients \\( )\textbf{c} \\) are the matrix of the molecular orbital
coefficients in the atomic orbital basis while. It seems we don’t actually need
these if we have the corresponding molecular orbital energies.

## Get ready

To write the program we need to locate where the integrals are. Normally you
would try an use the unix `grep` command with the word `integral` in the
`foofiles/` source directory. If you try that you will get a lot of output. On
reflection that is not unreasonable since much of quantum chemistry has to do
with integrals. After piping the output through less

~~~
   cd foofiles
   grep integral | less
~~~

After some searching you may come across the routine `.FOCK:make_ERI_integrals(v)` and
`.FOCK:make_MO_ERI_integrals(v)`. Looking further at these routines we see that the second
one produces a four dimensional array `v :: MAT4{REAL}`. From the documentation
these hold the integrals that are required.

## Housekeeping

In a perfect world we would expect to call that routine, using a template like 
in the “Hello Tonto World” program, and be returned the integrals we need. If
we actually do that, the program will crash. Why would that happen? Well, clearly
there is some set-up to do. For example, what molecule do we want to treat?
What basis set to use? And finally, should we actually do an SCF calculation beforehand
to get the molecular orbitals? And after that, we still need the orbital energies.
You might recall from the post on objects that these are stored in `orbital_energies`.

Once this is realised, we see that we actually want to add our MP2 calculation to
the end of a standard SCF calculation. Looking in the `tests/` folsderf we finda simple
one for water, say `h2o_rhf_cc-pVDZ`. We should use that input file. And rather than
starting with the “Hellow Tonto World” program we should start by modifying the
`run_molecule.exe` program. That, of course is in the `run_molecule.foo` file.

So we start by adding our code to the end of that program. We should probably rename in to
something like `run_molecule_mp2.foo` before starting.

## The Answer

At this point I would give you answer, but perhaps you can do this as an exercise.






