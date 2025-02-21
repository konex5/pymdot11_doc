.. _pyfhmdot: https://nokx5.github.io/golden-python

========================================
Welcome to the `pyfhmdot`_ project!
========================================

|CILinuxBadge|_ |CIDarwinBadge|_ |DocBadge|_ |LicenseBadge|_

.. |CILinuxBadge| image:: https://github.com/nokx5/pyfhmdot/workflows/CI-linux/badge.svg
.. _CILinuxBadge: https://github.com/nokx5/pyfhmdot/actions/workflows/ci-linux.yml
.. |CIDarwinBadge| image:: https://github.com/nokx5/pyfhmdot/workflows/CI-darwin/badge.svg
.. _CIDarwinBadge: https://github.com/nokx5/pyfhmdot/actions/workflows/ci-darwin.yml
.. |DocBadge| image:: https://github.com/nokx5/pyfhmdot/workflows/doc-api/badge.svg
.. _DocBadge: https://nokx5.github.io/pyfhmdot
.. |LicenseBadge| image:: http://img.shields.io/badge/license-MIT-blue.svg
.. _LicenseBadge: https://github.com/nokx5/pyfhmdot/blob/master/LICENSE

This project consists in giving a nice gate application interface to
the python layer in a way one can chain them easily. Please find below
the documentation `here <https://nokx5.github.io/pyfhmdot>`_ and the
source code `there <https://github.com/nokx5/pyfhmdot>`_.

.. warning:: **NOTE:** the project is developed using the nix ❄️
             packaging manager, but everything can be compiled by
             hand.

The dependency
==============

* mdot (C++) -- `Optional`
* fhmdot (C++/pybind11) -- `Optional`
* numpy
* scipy
* h5py

About
=====

The DMRG simulations within this project have the specificity to provide quantum
number conservation algorithm without any quantum number representation. This makes
the simulation closer to the task of the computer and avoid reshuffeling the different
blocs. 

Furthermore, the project was built with the idea to be able to go down to the
C++ level at any time (with **mdot** and **fhmdot**). Theoretically, one could improve by implementing :

* a parallel algorithm on the different blocs and in theory even chain the operations.
* a static allocation of the blocs (nightmare to implement).

In practice, most DMRG developers are simply happy when the code works and for this reason, everything 
is available in pure python.

Use the software
================

Open python and invoke

.. code:: python

    >>> from pyfhmdot.models.pyoperators import single_operator
    
    >>> single_operator("sh_sz_u1", 1 / 2.) # sz is a pauli matrix
    {(0, 0): array([[0.5]]), (1, 1): array([[-0.5]])}

    >>> single_operator("sh_sy_u1", 1 / 2.) # sy is a pauli matrix
    {(0, 1): array([[0.-0.5j]]), (1, 0): array([[0.+0.5j]])}


Install the software
--------------------

You can use pip but the optional dependencies would need to be compiled by hand from C++.
Start by cloning all dependencies in the same folder. You can clone
`git repository <https://github.com/nokx5/pyfhmdot>`_ locally.

=============
Code Snippets
=============

.. code:: shell

    black .

    nixpkgs-fmt .

    pip install $(cat requirements.txt) # works for pure python only

    pip list --format=freeze | sed 's/==/>=/g' > requirements.txt

    python -m pytest -k "not bronze"

=======
License
=======

You may copy, distribute and modify the software provided that
modifications are described and licensed for free under the `MIT
<https://opensource.org/licenses/MIT>`_.
