---
layout: post
title: "Science with objects"
description: 
category: articles
tags: [objects, scientific programming, how to program, basic Foo]
modified: 201-06-07
image:
  feature: so-simple-sample-image-3.jpg
  credit: Michael Rose
  creditlink: http://mademistakes.com
comments: false
share: true
---

We’d better start with this definition of my own:

> An object in computer science is a **collection of labeled data**
> together with actions or **methods** you can perform on that data.
> The methods are collected together in one place called a **class** or
> **module**.

Sometimes methods are also called messages i.e. you pass messages to the
object to ask it to perform an action. These methods or messages may
involving other objects of different type which may also change. An
object may also be called an abstract data type.

## Dot notation

Any number may be regarded as an object.

That’s because a particular number is a datum, and we can perform
actions on it e.g adding or multiplying it by another number. If collect
together these routines we have defined a class.

The example code snippets below demonstrate a near universal notation,
called “dot notation”, which I illustrate on numbers:

~~~ fortran
   a,b :: INT

   a = 1
   a.plus(1)

   b = 2
   b.times(3)
~~~

Here the variable `a` is set to `1`. `a` and `b` are integer variables
as seen by the declaration `a,b :: INT`.  Then a message is sent to it
via a dot followed by `plus(1)`. The intention of the message is that
the value of `a` is incremented by the number `1`. Presumably the value
of `a` is `2` after this method is applied. Likewise, the number `b` is
set to `2` and then the operations `times(3)` is performed on it,
resulting in a value of `6`. For those of you who like quantum
mechanics, this is nothing other than the application an operator,
except the operator comes *after* the entity on which the action is
performed.

All of this might seem rather trivial. But consider this example:

~~~ fortran
   m :: MAT{REAL}(3,3)
   eigenvalues  :: VEC{REAL}(3)
   eigenvectors :: MAT{REAL}(3,3)
   i,j :: INT

   do i = 1,3
   do j = 1,3
      m(i,j) = i + j
   end
   end

   m.solve_eigenproblem(eigenvalues,eigenvectors)
~~~

Look closely.

It does not require much imagination to guess that `m` is a
\\(3\times3\\) matrix of `REAL` numbers, as is `eigenvectors`.
`eigenvectors` is a 3-dimensional real vector.

Next come a couple of `do` statements. These are a loops. Meaning that
the integer variables `i` and `j` independently cycle from `1` to `3`
and the matrix `m` is set so its \\(i,j\\)-th element is `i+j`.

The next part is more interesting: a message is sent to to the matrix
`m` to please `solve_eigenproblem(eigenectors,eigenvalues)`. Again it
does not take much to guess that `eigenvalues` are the list of
eigenvalues, while `eigenvectors` holds the matrix of eigenvector
coefficients.

All this is cute, but has anything really been achieved? Isn’t this just
a familiar subroutine call? Well yes. But notice how the object-message
makes it clear what the entity actually being “acted on” is, and what
the inputs or output are.

## A leap

Let me now give a final example which quantum chemists will recognize.
It is slightly changed from the Tonto code base. It is written in the
`Foo` language, as are all the above examples. This is a big leap from
the previous examples, but you know enough to unravel it.

~~~ fortran
   usual_scf ::: recursive
   ! Do an SCF calculation. The .molecular_orbitals,
   ! .orbital_energies, and .density_matrix are produced as results.
      self :: MOLECULE

   ENSURE(self.basis_info_made,"no basis info")
   ENSURE(self.atom.created,   "no atom list")
   ENSURE(self.scfdata.created,"no scfdata")

      self.initialize_scf

      self.put_scf_banner_and_options
      self.put_scf_table_header

      do

         self.update_molecular_orbitals
         self.make_scf_density_matrix
         self.make_fock_matrix
         self.update_scfdata
         self.update_scfdata_error
         self.put_scf_table_body

         if (self.scfdata.scf_done) exit

      end

      self.put_scf_results
      self.cleanup_scf

   end
~~~

Look carefully.

It is clearly an SCF subroutine called `usual_scf` (for those who are
not familiar with quantum chemistry, the SCF procedure is the one which
yeilds the molecular orbitals for a molecule, from which the
Hartree-Fock or density functional theory energy may be calculated). The
declaration indicates that `usual_scf` is recursive i.e. it calles itself.

There are descriptive comments following the routine name, following the
exclamation marks, describing the results. They seem reasonable except
for the do in front of soke of the terms.

Next, a variable called `self` is declared. It is not an integer, or a
real, or matrix as we have seen before, but a `MOLECULE`. We don’t know
exactly what this `MOLECULE` is, but working by analogy it wpuld seem
reasnable that is is comprised of data --- probably quite a lot of data
since a molecule is a compicated object. One might speculate that,
stored in this variable of type `MOLECULE` are the types of atoms in it,
and perhaps their positions. Notice that you can work all this out by
intuition and by the naming of the entity. I don’t want to rub it in,
but I did stress the importance of naming things properly in a previous
post.

What is the actual data that comprises the `self` variable of type
`MOLECULE`? Where is it defined? We don’t get that information here,
obviously.

Let me inform you that the type `MOLECULE` is defined in the `types.foo`
file along with all the other types in the Tonto system.

Let me also tell you that `self` is in fact a *hidden argument* to this
routine. In other words, to the routine called `usual_scf` requires
`self` as an argument. In Fortran it might be called like this in
another part of the library:

~~~ fortran
   usual_scf(self)
~~~

In actual fact is called like this

~~~ fortran
   self.usual_scf
~~~

or even more succinctly like this

~~~ fortran
   .usual_scf
~~~

Pause on this a moment. I am saying that `self` is the object to which the
message `usual_scf` is passed to. That is, the SCF calculation is
performed on `self` itself. Perhaps this helps to explain the initially
rather cryptic name. In any case, the appearance of a single dot after
an empty space signifies the presence of a hidden `self` variable. Apart
from anything this leads to less typing.

## Removing your `self`

Let’s rewrite the above SCF routine without the unnecessary `self.`
prefix.

~~~ fortran
   usual_scf ::: recursive
   ! Do an SCF calculation. The .molecular_orbitals,
   ! .orbital_energies, and .density_matrix are produced as results.
      self :: MOLECULE

   ENSURE(.basis_info_made,"no basis info")
   ENSURE(.atom.created,   "no atom list")
   ENSURE(.scfdata.created,"no scfdata")

      .initialize_scf

      .put_scf_banner_and_options
      .put_scf_table_header

      do

         .update_molecular_orbitals
         .make_scf_density_matrix
         .make_fock_matrix
         .update_scfdata
         .update_scfdata_error
         .put_scf_table_body

         if (.scfdata.scf_done) exit

      end

      .put_scf_results
      .cleanup_scf

   end
~~~

Now the routine reads like a dot-point list of things to do. It is
really extremely readable. Indeed, It may seem hard to believe that this
is a working program --- perhaps even more unbelievable that this is
essentially just syntactically modified Fortran. (Much of the bad
reputation has come from the style of coding that scientists use: it is
not the language itself these days).

Furthermore, if we revisit the comments at the start of the routine it
finally becomes clear why the dots appear before `.molecular_orbitals`,
`.orbital_energies` and `.density_matrix`. These are messages passed to
te `self` variable to return certain entities. You can guess what they
are. These are in fact part of the data components which comprise the
definition of a `MOLECULE`

## Complex numbers as objects

If you have understood all of this, test yourself with the following
example.

We are going to define a complex number type, as follows, in the
`types.foo` file. (We don’t actually need to do thisbecause complex
numbers are built-in, but this is an exercise)

~~~ fortran
begin type COMPLEX_NUMBER

   a :: REAL
   ! The real part

   b :: REAL
   ! The complex part

end type
~~~

Now you know how to define a **derived type** comprised of built-in
types, in this case two `REAL` number types. A derived type may be
comparised of any previously defined derived type or built-in type.

What is the purpose of the following method? I will tell you that the
rouine is not correct. Can you find the bug?

~~~ fortran
module COMPLEX_NUMBER

contains

   to_product_with(z2) result (res)
   ! What do I do?

      self :: IN
      z2 :: COMPLEX_NUMBER, IN
      res :: COMPLEX_NUMBER

      z_1 :: COMPLEX_NUMBER

      z_1   = self
      res.a = z1.a z2.a + z1.b z2.b
      res.b = z1.a z2.b + z1.b z2.a

   end

end
~~~

## What all the fuss is about

This has been a long post but the key idea is just this:

> The power of using objects lies in their organizing ability

In particular

1. **All methods pertaining to an object are found in the corresponding
   module**. This is helpful because duplication of code is eliminated.
   Consider the case of a program written by many contributors *not*
   written in object oriented way. The chances are that the different
   authors write many duplicated routines. In particular domains, much
   hard work has been expended to make libraries of, for example, linear
   algebra and array routines. However, in other fields this effort is
   almost non-existent. Consider the case of quantum chemistry, for
   example, with it’s plethora of programs. Consider the wasted and
   duplicated efforts of so many smart people!

2. **Organizing programs in an object oriented way facilitates program
   evolution**. Let’s illustrate this again with examples from quantum
   chemistry.

   - How easy would it be to make use of the *integrals* in
     this program in another one? Perhaps it isn’t hard if they have
     been written to a file ... perhaps.

   - What if now you wanted to use *some* of the integrals and not
     others? Perhaps you want to calculate the energy contributions from
     a particular region to gain some physical insight?

   - What if now you have a new and *better way* of calculating the
     integrals. Perhaps you have discovered that gaussian basis
     functions with complex exponents work much better. How easy would
     it be to slot those integras into the code? After all, it would not
     be desirable to rewrite *everything in the original program.

   In general all of these tasks would be difficult to do unless the
   data used was well separated from the other parts of the program,
   and all actions on those data are **encapulated** in one place. But
   this is precisely the idea behind the object oriented approach.
   Indeed, as we saw, not only are all the methods which act on the same
   data collected in the same module --- the data object on which the
   methods are applied are always the first argument in any routine.

3. **It is easier to maintain an object oriented program**. If you have
   understood the above argument you should be able to provide reasons
   for this. As a matter of fact, it is well documented that during the
   life cycle of a program **much more effort goes into maintenance and
   bug fixing that into the original writing!** If this is accepted then
   it follows that much is gained by using objects.


## Proof of the pudding

The arguments given above may well seem like preaching. Some others may
think that the idea behind object oriented methods is just the concept
of a library --- organizing routines acting on the same data in one
place. This is correct: object orientation is just the library concept
on steroids. In a later post I hope to illustrate how easy it is to
write code in a well-designed quantum chemistry package.




