.. _pyfhmdot: https://nokx5.github.io/golden-python

Limits
======

According to my experience dealing with **T-DMRG** algorithm, the 
limits of those simulations come from the so called maximal bond dimension 
:math:\chi. Of course, this dimension is reached when the entanglement 
of the particles in the system exceeds the ability of the matrix product 
state to describe them. Thus a good criterion to stop the simulation 
would theoreticaly be once we reach the bond dimension -- because the 
matrix product state is not able to describe the system within the 
wished precision anymore. In practice, this arises to early and one could 
track the precision lost long after the maximal bond dimension was reached.

Furthermore, running simulations with increased bond dimension can give
information to the physicist how much the system changes under increase
of information within the system. However, this means running the same 
simulation multiple times over the same physical space.

In our case, we prefered reaching the limits (largest bond dimension 
possible) and see how far one could dig in the many body world. Here is a list 
of maximal bond dimension set within a quantum number representation. Please 
note that the total bond dimensions can reach multiple times this value (in 
my case a factor 8):

* spin half system : chi=2600
* spin one system : chi=1000
* spin four system (ladders) : chi=620

The total bond dimension corresponds to the total singular values that we keep 
in the system. Since the original formulation of DMRG, the density matrix is the 
central reason of those simulations. Remember, the singular values squared corresponds to 
the eigenvalues of the system in density formulation form.