Sumo
====

.. image:: https://travis-ci.org/SMTG-UCL/sumo.svg?branch=master
    :target: https://travis-ci.org/SMTG-UCL/sumo

.. image:: https://readthedocs.org/projects/sumo/badge/?version=latest
    :target: http://sumo.readthedocs.io/en/latest/?badge=latest
    :alt: Documentation Status

Sumo is a Python toolkit for plotting and analysis of ab initio
solid-state calculation data,
built on existing Python packages from the solid-state
chemistry/physics community.
It is hoped that these command-line tools will bring some of the
benefits of these libraries to a wider user-base while providing
publication-ready plotting (powered by Matplotlib_.)

The main features include:

1. An extensive framework for generating high-symmetry k-point paths.

   - Crystallographic spacegroups are determined using Spglib_.
   - Conventional crystallographic paths are built in as well as interfaces to
     the SeeK-path_ and
     Pymatgen_ implementations.

2. Plotting scripts for electronic and phonon band structures, density
   of states, and optical absorption diagrams.

   - VASP calculations are imported using Pymatgen_.
   - The Phonopy_ framework is supported for phonon band structures.

3. Analysis scripts to calculate parabolic and non-parabolic band
   effective masses.

   - Curve fitting is performed using `Scipy <https://www.scipy.org>`_.

The code currently only supports VASP calculations, however, we would
like to add support for additional solid-state codes in future
releases. Code contributions to interface with these packages are
welcome.

Sumo is free to use, however, we ask that you cite the code if you use
it in your research. See the "contributing" section for information
about reporting bugs and getting involved.

Usage
-----

Sumo is intended to be used via the command-line, however, a
fully-documented python API is also provided. A manual, including
tutorials and API documentation, is `available online
<http://sumo.readthedocs.io/en/latest/>`_. Additionally, the built-in
help (``-h``) option for each command provides a summary of the
available options.

A guide to using each command can be found on the
`Tutorial page <http://sumo.readthedocs.io/en/latest/tutorials.html>`_.

For a preview of the functionality of sumo, see the
`Gallery <http://sumo.readthedocs.io/en/latest/gallery.html>`_.

Currently, the scripts provided are:

- ``sumo-kgen``: For generating VASP KPOINTS files along high-symmetry
  k-point paths.
- ``sumo-bandplot``: For plotting publication-ready electronic band
  structure diagrams.
- ``sumo-dosplot``: For plotting publication-ready electronic density of
  states diagrams.
- ``sumo-optplot``: For plotting publication-ready optical absorption
  diagrams.
- ``sumo-phonon-bandplot``: For plotting publication-ready phonon band
  structure diagrams.
- ``sumo-bandstats``: For calculating electron and hole effective masses
  from a band structure.


Installation
------------

Sumo is a Python 3 package and requires a
`typical scientific Python stack <https://www.scipy.org/about.html>`_;
we recommend using your main package manager if possible
(e.g. apt, Homebrew), or Anaconda to install Python 3 with setuptools.
It is a good idea to also use this package manager to install
Numpy and Matplotlib, as building them with setuptools can be troublesome.
Sumo can then be installed using the Python package manager "Pip",
which will automatically setup other Python packages as required:

.. code-block:: bash

    pip3 install --user sumo

If this is your first entry to the scientific Python ecosystem, be
aware that the full stack including Scipy with need several hundred MB
of disk space.

To build the documentation, download the package source and install with
extra dependencies from the package directory:

.. code-block:: bash

    pip3 install --user .[docs]
    cd docs
    make html


Developer installation
~~~~~~~~~~~~~~~~~~~~~~

Developers may prefer to install using ``pip3 install --user -e .``
which creates an "editable" local installation. Instead of copying files,
this creates links to the source folder so that that tweaks to the
code in your source folder will be immediately reflected on the PATH.


Tests
~~~~~

To ensure the code has been installed correctly, the unittests can be
run (from the root directory of the project) using::

  python3 -m unittest discover tests


License
-------

Sumo is made available under the MIT License.

  
Detailed requirements
---------------------

Sumo is currently compatible with Python 3.5+ and relies on a number of
open-source python packages, specifically:

- Pymatgen_ (version >= 2017.12.30)
- Numpy_
- Scipy_
- Matplotlib_
- Spglib_
- Phonopy_
- SeeK-path_
- `H5py <https://www.h5py.org>`_

.. _matplotlib: https://matplotlib.org
.. _numpy: http://www.numpy.org 
.. _phonopy: https://atztogo.github.io/phonopy
.. _pymatgen: http://pymatgen.org
.. _scipy: https://www.scipy.org
.. _seek-path: https://github.com/giovannipizzi/seekpath
.. _spglib: https://atztogo.github.io/spglib


Contributing
------------

Bugs reports and feature requests
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

There are probably still some bugs. If you think you've found
one, please report it on the `Issue Tracker
<https://github.com/SMTG-UCL/sumo/issues>`_.
This is also the place to propose ideas for new features or ask
questions about the design of Sumo.
Poor documentation is considered a bug, but please be as specific as
possible when asking for improvements.

Code contributions
~~~~~~~~~~~~~~~~~~

We welcome your help in improving and extending the package with your
own contributions. This is managed through Github pull requests;
for external contributions we prefer the
`"fork and pull" <https://guides.github.com/activities/forking/>`__
workflow while core developers use branches in the main repository:

   1. First open an Issue to discuss the proposed contribution. This
      discussion might include how the changes fit Sumo's scope and a
      general technical approach.
   2. Make your own project fork and implement the changes
      there. Please keep your code style compliant with PEP8.
   3. Open a pull request to merge the changes into the main
      project. A more detailed discussion can take place there before
      the changes are accepted.
