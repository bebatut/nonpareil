Install Nonpareil
====================

System requirements
-------------------

**Nonpareil binary**: Nonpareil requires a C++ compiler. It has been tested on
64-bit machines with GCC versions >=4.2.1, running Mac OSX and Red Hat Linux.

**Nonpareil MPI**: If you want to compile Nonpareil with MPI support, you will
need OpenMPI_ (v > 1.4.3 tested). Other implementations of MPI could work, but
are yet untested.

**Nonpareil utilities**: Requires R_. No additional libraries are necessary.

Compilation
-----------

1. **Get the source**

   Clone the repository from GitHub_::

      git clone git://github.com/lmrodriguezr/nonpareil.git

   If you don't have git_, you can also download the TAR-Ball_ and unpack it
   with::

      tar zxvf nonpareil.tar.gz

2. **Compile**

   Change directory into the newly created folder, and compile Nonpareil::

      cd nonpareil
      make

   If you want to compile Nonpareil MPI (see also :doc:`mpi`), just run::
      
      make nonpareil-mpi

   In either case, you can specify the C++ compiler to be used setting the
   ``cpp`` or ``mpicpp`` variables, respectively. For example::
      
      make cpp=/usr/local/bin/g++ nonpareil # This compiles nonpareil with /usr/local/bin/g++
      make mpicpp=/usr/local/bin/mpic++ nonpareil-mpi # This compiles nonpareil-mpi with /usr/local/bin/mpic++

3. **Install**

   If you want to make Nonpareil available system-wide, just run::

      sudo make install

   If you don't have superuser privileges and/or want to install Nonpareil in a
   location other than ``/usr/local``, simply set the prefix, for example::
      
      make prefix=$HOME/apps install

   You can also change the location of ``R``, if it's not in the ``$PATH`` or
   you want to use a non-standard installation::

      make prefix=$HOME R=~/bin/R install

   Other variables you can set explicitly for the ``install`` target are
   ``bindir`` (binaries directory) and ``mandir`` (documentation directory).


.. _R: http://www.r-project.org/
.. _git: http://git-scm.com/
.. _GitHub: https://github.com/lmrodriguezr/nonpareil
.. _OpenMPI: http://www.open-mpi.org/
.. _TAR-Ball: https://github.com/lmrodriguezr/nonpareil/tarball/master
