.. _pyfhmdot: https://konex5.github.io/pymdot11_doc

========================================
Welcome to the `pyfhmdot`_ project!
========================================

 |DocBadge|_ |LicenseBadge|_

.. |DocBadge| image:: https://github.com/konex5/pymdot11_doc/workflows/doc-api/badge.svg
.. _DocBadge: https://konex5.github.io/pymdot11_doc
.. |LicenseBadge| image:: http://img.shields.io/badge/license-MIT-blue.svg
.. _LicenseBadge: https://github.com/konex5/pyfhmdot/blob/master/LICENSE

This project consists in giving a nice gate application interface to
the python layer in a way one can chain them easily. Please find below
the documentation `here <https://konex5.github.io/pymdot11_doc>`_ and the
source code `there <https://github.com/konex5/pymdot11>`_.

.. warning:: **NOTE:** the project is developed using the nix ❄️
             packaging manager, but everything can be compiled by
             hand.

The dependency
==============

* mdot (C++/pybind11) -- `Optional`
* numpy
* scipy
* h5py


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

You can use `pip <https://python.com>`_ but the optional dependencies would need to be compiled by hand from C++.
Start by cloning all dependencies locally using
`git repository <https://github.com/konex5/pyfhmdot>`_.

=============
Code Snippets
=============

.. code:: shell

    pip install $(cat requirements.txt) # works for pure python only

    pip list --format=freeze | sed 's/==/>=/g' > requirements.txt

    python -m pytest -k "not test"

===================
Build Documentation
===================

.. code:: shell

    cd docs

    make html

    browse build-target/html/index.html

=======
License
=======

You may copy, distribute and modify the software provided that
modifications are described and licensed for free under the `MIT
<https://opensource.org/licenses/MIT>`_.
