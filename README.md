pushnplay
=========

Linux cartwall player

Prerequisites:
--------------
  * gstreamer-1.0 or 0.10 (development packages)
  * GTK-3.x (development packages)
  * [jackd](http://jackaudio.org)
  * make and optionally autotools


Compile:
--------
There are two ways to compile pushnplay.

First, the plain and simple approach without autotools:

  * For gstreamer-1.0, run
    `cd gstreamer && make -f Makefile.simple`

  * For gstreamer-0.10, run
    `cd gstreamer && make OLDGSTREAMER=1 -f Makefile.simple`

For packagers, there's the more sophisticated autotools-based approach:

    ./autogen.sh
    ./configure

configure will automatically build against gstreamer-1.0 if it can
be found, else it will build against gstreamer-0.10.

If you want to explicitly specify which version of gstreamer to build
against you can pass `--with-old-gstreamer` or `--without-old-gstreamer` to
configure:


  * For gstreamer-1.0:
    `./configure --without-old-gstreamer`

  * For gstreamer-0.10:
    `./configure --with-old-gstreamer`

Then run:
    make
    make install

You don't have to install pushnplay, you can also run the binary from
the build directory.

Running
-------
You need to provide a session file, either by specifying `-c` or in
`~/.pushnplay`. An example version of the required format is provided in
`sessionfile-example`
