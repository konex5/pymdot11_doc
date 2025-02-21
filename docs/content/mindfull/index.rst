.. _pyfhmdot: https://nokx5.github.io/golden-python

Mindfull
========

According to my experience dealing with **DMRG** algorithm, I was not
convinced by the method.  Indeed, those algorithms require to lose
precision in order to converge for large system sizes.  It is
furthermore frustrating to understand that the *difficult* and
*interesting* systems are anyway limited due to **entanglement
entropy** when eigenvalues are too close to degeneracy. Those **hard
manybody systems** are mainly chaotic studies question.

However, I found the high performance computing coding, the **HPC**
problem of DMRG, quite challenging. I wanted to implement a **quantum
number-less** version based on *quantum number representation*. This
is probably a first step towards optimization. Indeed, no *search*
algorithm is used on any basis, and thus more locality is ensure for
the computer.

Note that I have first implemented a class for tensor representation
for **mps** and **theta** matrices form.  However, one would just need
a tensor library with indices mapped to matrices.  For this reason, I
introduced the concept of **blocs** which can be seen as hierarchical
matrices in multidimensional tensor spaces.  The *blocs* are simply a
map (*std::map*) between tensor indices (*std::tuple*) and a dense
array (*std::vector*).

.. code:: cpp
    
    #include<map>
    #include<tuple>
    #include<vector>

    std::map<std::tuple<int,int,int>,std::vector<double>> mp_blocs;
    std::map<std::tuple<int,int,int,int>,std::vector<double>> theta_blocs;

Note that one could statically allocate those blocs by giving a priori
:math:`a^2 + \chi_\text{max}` maximal dimensions and a set of tuple
*indices* -- and one could replace *std::vector* with *std::array*.
This is in practice hard to implement in procedural languages.

The surprise I got while looking closely to a *hamiltonian matrix product operator* form is 
that it span naturally the space of an *exact diagonalization* problem 
(quite logic indeed). Thus the  `pyfhmdot`_ library provides attempt for
exact diagonalization as well.

Please find,

* a **TDMRG** simulation
* a **0-DMRG** simulation
* a **t-DMRG** simulation on both mixed or pure state
* a **ED** simulation
