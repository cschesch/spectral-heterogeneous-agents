# Spectral Methods for Heterogeneous-Agent Models - PSE Master Thesis

In this repository, you can find the code for the Master Thesis _"Continuous-Time Methods for Heterogeneous-Agent Models in Macroeconomics: a Spectral Approach"_, which I wrote in 2022 for the Master in Analysis and Policy in Economics at the Paris School of Economics, under the supervision of Prof. Daniel Cohen and Prof. Tobias Broer. You can find the thesis and the corresponding slides on this repository.

## Abstract

To be added.

## Code Structure

There are six pieces of code, all written in Python and saved as Jupyter Notebooks:
\begin{enumerate}
* `backend`: contains various helper functions, notably for manipulating and assembling differentiation matrices, that are used in all other codes of this project
* `two_state`: code for the two-income Hugget model which is solved in Section 4 and used for the benchmark of Section 8
* `two_state_weakly_binding`: code for the two-income model with a weakly binding credit constraint, in which the pseudospectral solution to the KF equation is not too terrible
* `diffusion`: code for the diffusive income Hugget model solved in Section 5
* `life_cycle`: code for the life-cycle model solved in Section 6
* `slow_transitions`: code for the Power law model and transition speed analysis from Section 7

To run without modification, all code should be put into a folder titled `code`, next to which one should create two folders called `figures` and `tables` to collect the output. The only slightly esoteric dependency used is [DmSuite](https://github.com/labrosse/dmsuite), which you can simply download using [Pip](https://pypi.org/project/dmsuite/).

If you have any questions on the code or the Thesis itself, feel free to message me at `c.schesch@gmail.com'.
