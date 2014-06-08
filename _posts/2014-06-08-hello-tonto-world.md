---
layout: post
title: "Hello Tonto World"
description: "tonto programming"
category: articles
tags: [tonto, programming, basic Foo]
modified: 201-06-07
image:
  feature: so-simple-sample-image-3.jpg
  credit: Michael Rose
  creditlink: http://mademistakes.com
comments: false
share: true
---

This is what the “Hello World” program looks like in Tonto

~~~ fortran
program run_HELLO_TONTO_WORLD

   implicit none

   ! Macro to create Tonto system object
   ! Start MPI-parallel stuff too (if needed)
   TONTO_CREATE

   ! Start timer
   std_time.start_timing

   ! Initialise standard I/O files.
   ! Always have this.
   stderr.create_stderr; stderr.open
    stdin.create_stdin;   stdin.open
   stdout.create_stdout; stdout.open

   ! Do it
   stdout.text(“Hello Tonto World”)


   ! Memory report
   TONTO_REPORT

   ! Clean-up files
   TEXTFILE:destroy(stdout)
   TEXTFILE:destroy(stdin)
   TEXTFILE:destroy(stderr)

   ! Clean-up tonto system
   TONTO_DESTROY

end
~~~

This file appears with all the other executable programs in the `runfiles`
folder. 

To compile an type `make run_hello_tonto_world.exe`. You have to do this after
typing `make` to ensure the library is compiled (this step needs to be done
only once). 





