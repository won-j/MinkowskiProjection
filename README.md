# Supplementary materials for "Projection onto Minkowski Sums with Application to Constrained Learning" to appear in ICML 2019 by Kenneth Lange, Joong-Ho Won, and Jason Xu

## Overview
- SLEP MATLAB toolbox (SLEP-master.zip)
    - MATLAB toolbox consisting of functions for sparse regression, especially the proximity operator for $\ell_{1,2}$-overlapping group lasso.
- SparseReg MATLAB toolbox (SparseReg-0.0.2.zip)
    - MATLAB toolbox consisting of functions for sparse regression, especially ADMM for constrained lasso.
- overlappinggroup subdirectory
    - Contains MATLAB code to reproduce the results in Section 4.1. See below for further details.
- constrainedlasso subdirectory
    - Contains MATLAB code to reproduce the results in Section 4.2. See below for further details.

## Code & Data
### Requirements
- MATLAB code
   - SLEP toolbox
	  - Version 4.1 is included in these supplementary materials as a .zip file. This version of the toolbox can also be downloded from https://github.com/jiayuzhou/SLEP. The original link http://www.yelab.net/software/SLEP appears to be dead.
   - SparseReg toolbox
      - Version 0.0.2 is included in these supplementary materials as a .zip file.  The latest version of the toolbox can be downloaded from https://github.com/Hua-Zhou/SparseReg
   - Gurobi optimization software
      - Gurobi can be downloaded from http://www.gurobi.com/
      - Free academic licenses are available
- MATLAB code 
   - The overlappinggroup/ subdirectory contains five .m files. sim1.m is the main simulation loop. grplasso_prox.m is the Minkowski projection based code for computing proximity operator for the overlapping group lasso penalty. This code calls minkowski_proj.m, for which getLqDiskProjections.m provides the required projections to the summand sets. grpprox_obj.m computes the value of the objective function for the proximity operator (Moreau-Yosida smoothing).
   - The constrainedlasso/ subdirectory contains four .m files. sim1.m is the main simulation loop for the zero-sum constrained lasso. sim2.m is the main simulation loop for the nonnegative lasso. Both files call classo_proxgrad.m, which implements the proximal gradient descent for the constrained lasso based on the Minkowski projection. This in turn calls minkowski_proj.m. The required projections to the summands are hard-coded in sim1.m and sim2.m.

### Simulations
- Make sure that Gurobi was installed successfully, and that the directories for the SparseReg toolbox and Gurobi have been added to MATLAB's search paths.

### Acknowledgment
- This document and the simulation loops were modified from the Supplementary Material for "Algorithms for Fitting the Constrained Lasso" by Brian Gaines, Juhyun Kim and Hua Zhou, available at https://doi.org/10.1080/10618600.2018.1473777




