---
layout: post
title: "Why two electrons per orbital?"
description: "The antisymmetrizer operator"
category: articles
tags: [CHEM2002, electrons, spin, spinorbital, pauli principle]
modified: 2014-11-04
image:
  feature: rene-magritte-decalcomania.jpg
  credit: Rene Magritte - Decalcomania
  creditlink: http://www.algorithmic-worlds.net/blog/blog.php?Post=20110201
comments: false
share: true
---

Electron are negatively charged and repel each other.

How is it possible that within atoms and molecules they suddenly turn
schizophrenic and two of them occupy the same orbital?

Frankly, this is nuts.

I have never encountered a simple, vivid and correct explanation which makes
this contradiction acceptable. On the contrary, in basic chemistry, we simply
*assert* that the electrons “fill-up” the orbitals that way with “opposite spin”.

But how does that *explain* anything? 

What has spin got to do with any of this?

## Electrons are four dimensional

**The real answer is that electrons actually inhabit their own special four
dimensional space**.

This fourth dimension is special:

* Unlike normal 3D space where \\( x \\), \\( y \\) and \\( z \\) may take any
  value in the range \\(-\infty \\) to \\( +\infty \\), the extra fourth dimension
  is bound to the surface a *complex two dimensional circle*. 

* The fourth coordinate is actually a kind of “wrapped up” line; and like any
  circle it is described by two complex numbers, say \\( a \\) and \\( b \\).
  These numbers are not independent but are connected by the equation
  \\( |a|^2 + |b|^2 = 1\\).

* Indeed, since the extra dimension is a circle, one should actually think of
  it as comprised of two sub-dimensions. The numbers \\( a \\) and \\( b \\)
  are its coordinates along two abstract unit-vector directions which we usually
  call \\( \ket{\uparrow} \\) and \\( \ket{\downarrow} \\) (though probably
  should be called \\( \ket{\uparrow} \\) and \\(\ket{\rightarrow}\\)). 
   
* The spin coordinates \\( a \\) and \\( b \\) are analogous to the numbers 
  \\( x \\), \\( y \\) and \\(z\\) describing distances along along the three
  dimensional unit-vector axes \\( \ket{\B{e}\sub{x}}\\),
  \\(\ket{\B{e}\sub{y}}\\) and \\( \ket{\B{e}\sub{z}}\\).

In a later post I will show that this extra fourth dimension is used to
describe how the wavefunction of the electron changes when it is rotated in
three dimensional space. For this reason, the extra dimension is called the
electron [**spin**](http://en.wikipedia.org/wiki/Spin_(physics)). Because this
fourth dimension is unique to electrons, it is often called an *internal degree
of freedom*.

In contrast, the \\( x \\), \\( y \\) and \\(z \\) coordinates which are common
to all particles are *external degrees of freedom*: these coordinates arise from
*translating* the particle in space.

All this is a lot to take in; it is worth re-reading the previous paragraphs!

## Time is not the fourth dimension!

To avoid any confusion, I should say that the fourth dimension we are talking
about is *not* the time dimension; spin is a completely different *additional*
dimension. Time is a plain old dimension like the other three spatial coordinates.

## The spin of other particles

As a matter of fact, every fundamental particle has its own private wrapped up
“spin” dimension attached to it -- although the “size” of this dimension (two
in the case of an electron) may be different for different particles.

* For example, the photon has three spin components, two of which correspond to
  its *helicity*, used to describe its polarization.

* Protons and neutrons have an extra fourth dimension with two sub-dimensions,
  exactly like electrons.

In any case the extra private wrapped-up dimension describes how the particle
behaves when it rotates, and so the extra dimension is always called spin.

## Why are spin coordinates so different to position coordinates?

Why do all particles have the same \\( x \\), \\( y \\) and \\( z \\)
coordinates to describe translation, but different coordinates to describe how
they rotate? 

Another way to ask this is: why are the external degrees of freedom always the
same for every particle, but the internal degrees of freedom may be different?

The answer is that it just happens translations are easier to describe
mathematically than rotations. There is only one way to describe translations for
a wavefunction, and that is with three corrdinates. By contrast, since rotations
are more complicated (I hope you agree!) the way an object can behave
under rotations can possibly display more variation.

Personally I think the distinction between internal and external degrees of
freedom is not an important one. In either case, the electrons “coordinates”,
whatever they are, are used to describe how its *wavefunction changes when you
translate or rotate it*.

## Why can’t we “see” spin like position?

When you look at things, your eyes register different positions when
an object has different \\( x \\), \\(y \\) and \\( z\\) coordinates when
photons of arbitrary polarization scatters from that particle into your eyes.

If sources of light were generally available which could detect helically
polarized light, and if our eyes were adapted to such polarized light,
we might actually be able to “see” a particle differently according to what
spin it has.

Sadly, our eyes do **not** have this ability.

What luck that we have instruments to probe things where our eyes fail us!

## Why the extra dimension makes sense

Nevertheless, it is not immediately obvious that electrons have their own extra
fourth dimension.

The evidence for it came from atomic electronic structure.

From an elementary perspective it seems as if the electrons just occupy the
same orbital as they “fill up”. But it only *looks* like there are two
electrons per orbital.

**In actual fact, each electron is in its own four dimensional spinorbital**.

A spinorbital is just a normal orbital three dimensional orbital
(wavefunction) extended into the fourth dimension.

Now two key points:

1. The spinorbital notion allows to explain why two electrons occupy an orbital
   because an orbital is a 3D concept. It looks to us as if they are in the
   same orbital, but in fact they are in different spinorbitals. They are
   actually in different 4D “positions”.

2. This spinorbital idea also allows to explain *why* two electrons would even
   want to be in the same 3D orbital. The reason is that in this way they can
   both get close to the positively charged nucleus in 3D to which they are
   attracted. However, at the same time they are away from each other *in the
   fourth dimension* if they are in different spinorbitals. (It is worth noting
   that the electrical repulsion between the electrons is not reduced because the
   electrons have a different fourth dimension, since repulsion operates only
   in 3D)

We represent this different location in the fourth direction by an
up- or down-arrow corresponding to the fact that they are (more or less) on
different axes the spin circle. But you already know about the up- and down-
arrows. 

So the answer to the riddle “why do electrons occupy the same orbital”
is that “they don’t”. They stay away from each other, while still maintaining
their mutually close distance (in 3D space) to the positively charged nucleus.

Without invoking the extra dimension, it is very hard to reconcile why
electrons should actually occupy the same region of space. In fact, it took
Pauli quite some time to come to this conclusion himself.

## Antisymmetry and electron spin

Previously we derived the fact that the wavefunction for identical particles 
[either reverses sign or stays the same](http://dylan-jayatilaka.net/articles/the-determinant-wavefunction/).
If the former, the particle was called *fermion* if the latter, a *boson*.

For fermions, the change is sign or antisymmetry was called the *Pauli principle*.

Now: rotating two electrons around their common midpoint is the same as swapping
their positions. Swapping is more complicated than rotating when there are more
than two electrons. 

Nevertheless, using the case of just two electrons, one might expect that there
is a connection between a particles spin (i.e. how the wavefunction behaves
when rotated) and whether it is a fermion or boson (i.e. how the wavefunction
behaves when the coordinates are swapped).

This is in fact the case.

Pauli received the Nobel Prize for proving that, if a particle has a spin
quantum number which is a half integer, a wavefunction involving two of those
particles must reverse sign whenever the coordinates of those particles are
swapped. This is known as the
[spin-statistics theorem](http://en.wikipedia.org/wiki/Spin%E2%80%93statistics_theorem) 
and it has to be one of the deep facts of the universe. T

Unfortunately, the proof of this theorem by Pauli is rather complicated and it
involves ideas from relativistic quantum mechanics and field theory.

I think the general view is that Pauli has **not** actually proved this theorem
but merely shown that it follows from other sensible assumptions made in
quantum mechanics. This is a rather unsatisfactory state of affairs, and
[Richard Feynman](http://en.wikipedia.org/wiki/Richard_Feynman) said so.

Perhaps you can find an alternative, simple explanation?

## Matter-like particles

In fact, all *matter-like* particles must obey the antisymmetry principle.

That is because the antisymmetry principle demands particles have a zero
probability of occupying the same region of space, exactly as one would
expect for “solid” particles. Such solid particle simply *can’t* occupy the
same space at any time (remembering that by “space” we include the particles
internal fourth dimension).

By contrast, it seems we can cross as many laser beams as we like, proving that
the same does not hold for particles of light. We conclude that light particles
must be bosons and that bosons are **not** matter-like.

## A vivid example

<figure class="half">
    <img src="/images/anders-krisar-by-christian-larsen-yatzer-2013.jpg" alt="image">
    <img src="/images/rene-magritte-les-liasons-dangerous-1935.jpg"      alt="image">
    <figcaption>Untitled, Krisar (2013); Les Liasons Dangerous, Magritte (1935)</figcaption>
</figure>

All of this is rather abstract.

In the hopes of making the essential idea clearer in class, I have tried the
following demonstration.

* **I ask two boys to stand up in the same rows of the lecture theatre seats
  near the front -- where the seats are never occupied -- and move towards each
  other**. Of course, they are unable to pass each other. These two boys are
  supposed to represent two electrons of the same spin coordinate. Since they
  have the same spin coordinate they cannot “pass” each other (they are trapped
  between the rows).

* **Next I ask a boy and a girl in different but consecutive rows of
  seats to move towards each other**. When they are about to cross I shout out
  “stop”. At this point, the rest of the students (who are clustered at the
  back of the theatre) can see that the girl and the boy are roughly “on top”
  of each other. They *look* as if they are occupying the same space, but are
  actually on different rows. This is exactly analogous to the case of two
  electrons with different spin being able to cohabit the same three dimensional
  position.








