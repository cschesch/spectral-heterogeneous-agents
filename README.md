# Pseudospectral Methods for Continuous-Time Heterogeneous-Agent Models

In this repository, you can find the code for the Working Paper- _"Pseudospectral Methods for Continuous-Time Heterogeneous-Agent Models"_, currently under review at the Journal of Economic Dynamics and Control.

## Abstract

Abstract We propose a pseudospectral method to solve heterogeneous-agent models in continuous time. The solution is approximated as a sum of smooth global basis functions, in our case polynomials represented by their values at Chebyshev nodes. We illustrate the method by applying it to a Krusell-Smith model. It solves the differential equations characterizing the steady-state efficiently and precisely, despite using only very few nodes. System dynamics are then automatically differentiated to simulate a linearized model. The full solution is very fast and uses only standard software. A benchmark against finite differences shows at pseudospectral methods achieve far greater precision for a given number of nodes and for a given runtime. We conclude by discussing the methods' applicability, which is promising for smooth multi-dimensional models.

## Code

There are six pieces of code, all written in Python and saved as Jupyter Notebooks:
* `backend`: contains various helper functions, notably for manipulating and assembling differentiation matrices, that are used in all other codes of this project
* `two_state`: code for the two-income Hugget model which is solved in Sections 3 and 4, and used for the static benchmark of Section 6
* `krusell_smith`: code for the two-income Krusell-Smith model which is solved in Section 5 and used for the Den Hann error calculation of Section 6
* `two_state_weakly_binding`: code for the two-income model with a weakly binding credit constraint in Appendix A
* `diffusion`: code for the diffusive income Hugget model solved in Appendix B
* `power_law`: code for the power law model and transition speed analysis in Appendix C
* `life_cycle`: code for the life-cycle model solved in Appendix D

To run without modification, all code should be put into a folder titled `code`, next to which one should create two folders called `figures` and `tables` to collect the output.

Beyond the standard Numpy and Scipy, there are only two important dependencies:
* [DmSuite](https://github.com/labrosse/dmsuite), to compute pseudospectral differentiation matrices, which you can download using [Pip](https://pypi.org/project/dmsuite/)
* [JAX](https://github.com/google/jax/), to automatically differentiate system dynamics for the linearized simulation, which you can also download using [Pip](https://pypi.org/project/jax/)

If you have any questions on the code or the paper itself, feel free to message me at c.schesch@gmail.com.