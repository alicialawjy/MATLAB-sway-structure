# Modelling of a Sway Structure
The Finite Element (FE) Method is a very powerful mathematical technique used to solve complex systems of partial differential equations. When applied with respect to structural analysis of trusses and frames, the method:
1. breaks the structure down into a limited and countable number of elements, 
2. reformulates the governing differential euqations (equilibrium, constitutive and kinematic), and finally 
3. assembles the elements to obtain the full structure again. 
This allows us to build up a matrix of simultaneous algebraic equations that can now be solved. 

Using this concept, these procedures are applied to the codes contained in the classes: 
- ‘TRUSS’ saved in **TRUSS.m**, and 
- ‘FRAMES’ saved in **FRAMES.m**, 
under the functions ‘assemble’ and ‘solve’ within these respective classes. 

Script **Radius.m** contains the function that calculates the maximum and minimum sway displacement (i.e. how much the structure has moved) for both Truss and Frame systems.

Script **Qn1_rcond.m** is used to determine rcond value when different number of cross bracings (i.e diagonal elements) are added to a Truss system.
- Background: rcond is known as the reciprocal condition number. It is a scale-invariant measure of how close a given matrix is to the set of singular matrices. 
- Computationally, if the rcond is smaller than the machine precison, epsilon = 1 x 10-15, the matrix is considered badly conditioned and the structure is statically unstable.
- This script is used to determine the number of cross bracings required to achieve a statically structure, aka. the limit where the rcond > epsilon.

Script **CourseworkScript.m** is used to run through different possible design combinations for both Truss and Frame systems to identify the most optimal structure and configuration. It considers:
- Economy: material quantity and costs,
- Displacement: how much the system moves, and
- Factor of Safety: how safe the structure is.

To look at the final results and findings, see **Computational Report.pdf** for the full report.