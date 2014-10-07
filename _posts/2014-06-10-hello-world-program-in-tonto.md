---
layout: post
title: "Hello World"
description: "The Hello World program in Tonto"
category: articles
tags: [hello world, tonto, programming, basic Foo]
modified: 201-06-07
image:
  feature: pieter-bruegel-landscape-with-the-flight-into-egypt.jpg
  credit: Peter the Elder Bruegel - Landscape with the Flight into Egypt - The Courtald Institute of Art
  creditlink: http://www.artandarchitecture.org.uk/images/gallery/6b06f360.html
comments: false
share: true
---

This is what the “Hello World” program looks like in Tonto

{% highlight ruby %}
   program run_HELLO_WORLD

      implicit none

      ! Macro to create Tonto system object
      ! Start MPI-parallel stuff too (if needed)
      TONTO_CREATE

      ! Start timer
      std_time.start_timing

      ! Initialise standard I/O.
      stdout.create_stdout
      stdout.open

      ! Do it
      stdout.text(“Hello World”)

      ! Memory report
      TONTO_REPORT

      ! Clean-up files
      stdout.destroy

      ! Clean-up tonto system
      TONTO_DESTROY

   end
{% endhighlight %}

To compile the program type `make run_hello_world.exe`.

Now, if this seems like a lot of work to print out “Hello World” remember that
the Tonto library is fully self contained: there are no external libraries or
dependencies, there are no hidden operations or code.

Other points to note:

* The program name includes a `run_` prefix before the name `HELLO_WORLD` all
  in capitals. This is requied.

* Comments appear after an exclamation mark. (Note: The highlighting of code
  within comments, and in the code is not always correct because I use the
  ruby language highlighter for the moment).

* There is a lot of “set up”  and "clean up” which occurs, controlled via
  macro commands such as `TONTO_START` and `TONTO_DESTROY` respectively. These
  are required.

* The code uses standard dot notation to pass messages to objects e.g. the
  `“Hello World”` is passed to the the `stdout` textfile object.

* `TONTO_REPORT` produces optional timing, memory use, or call stack
   backtrace --- if compiled with special switches.

* If this seems annoying, remember that Tonto is self-contained
  and nothing is hidden or farmed off to libraries.

* You can explicitly clean-up objects via `stdout.destroy` but you don’t
  have to. It may help in places where you want high efficiency.

