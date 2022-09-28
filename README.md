# Spectral Methods for Heterogeneous-Agent Models - PSE Master Thesis

In this repository, you can find the code for the Master Thesis _"Continuous-Time Methods for Heterogeneous-Agent Models in Macroeconomics: a Spectral Approach"_, which I wrote in 2022 for the Master in Analysis and Policy in Economics at the Paris School of Economics, under the supervision of Prof. Daniel Cohen and Prof. Tobias Broer. You can find the Thesis and the accompanying slides on this repository.

## Abstract

 Over the last decades, the attention received by heterogeneous-agent models has only been rivalled by the considerable difficulties macroeconomists encountered in solving them numerically. Achdou et al. (2021)’s hallmark contribution recast these models in continuous-time, describing them as coupled Hamilton-Jacobi-Bellman and Kolmogorov Forward partial differential equations, which can then be solved very quickly using (upwind) finite differences. In their footsteps, we propose to solve continuous-time heterogeneous-agent models using (pseudo-)spectral methods, which represent the solution as a sum of global basis functions, e.g. Chebyshev polynomials.
 
In a Hugget model with two incomes and credit-constrained savings, the smoothness of the value function means that a good approximation can be obtained using few collocation nodes. Solving for the stationary distribution is more involved because the Dirac mass of agents at the borrowing constraint cannot be represented spectrally, so that a hybrid scheme combining a smooth spectral domain and a Dirac-like finite volume domain has to be employed. Benchmarks show that this outperforms a pure finite difference approach, with precise estimations taking less than 1/10th of a second.

To illustrate the added value of the pseudospectral approach in higher-dimensional problems, we extend it to diffusive income and then to a life-cycle. Each time, the smoothness of the spectral solution to the HJB equation means that relatively few nodes in each dimension yield a precise solution. The resulting savings function can then be interpolated to a high definition grid to quickly & easily solve for the stationary distribution using finite volumes.

Finally, we show that the pseudospectral approach can be useful to solve savings problems over a large value range by applying it to a model with power law income. The finite volume discretization of the Kolmogorov Forward Equation yields a discretized transition rate matrix whose eigenvalues can be computed to study the puzzle of "slow transitions", formulated in Gabaix et al. (2016) for incomes, in a model incorporating both income and wealth inequality.

## Code

There are six pieces of code, all written in Python and saved as Jupyter Notebooks:
* `backend`: contains various helper functions, notably for manipulating and assembling differentiation matrices, that are used in all other codes of this project
* `two_state`: code for the two-income Hugget model which is solved in Section 4 and used for the benchmark of Section 8
* `two_state_weakly_binding`: code for the two-income model with a weakly binding credit constraint, in which the pseudospectral solution to the KF equation is not too terrible
* `diffusion`: code for the diffusive income Hugget model solved in Section 5
* `life_cycle`: code for the life-cycle model solved in Section 6
* `slow_transitions`: code for the Power law model and transition speed analysis from Section 7

To run without modification, all code should be put into a folder titled `code`, next to which one should create two folders called `figures` and `tables` to collect the output. The only slightly esoteric dependency used is [DmSuite](https://github.com/labrosse/dmsuite), which you can simply download using [Pip](https://pypi.org/project/dmsuite/).

If you have any questions on the code or the Thesis itself, feel free to message me at c.schesch@gmail.com.
