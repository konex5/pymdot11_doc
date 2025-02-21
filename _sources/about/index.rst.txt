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