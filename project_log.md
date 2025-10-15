# Project Log — Merton Consumption-Investment Model

## 2025-09-22
- Created repo structure
- Added project_log.md
- Read Merton 1971
- Next: Read Merton 1961

## 2025-09-23
- Read Merton 1961 
- Started write up of the model and recapped establishing the SDE from first principles 
- Next: simulations with fixed consumption, plot sample paths and Read about Jacobi Bellman.

## 2025-10-06
### restart point
- The last two weeks I have researched how HJB is derived from first principles. How it can be applied to stochastic control problems
- I also started programming a solver for the HJB which would allow me to visualise solutions to merton optimisation problems with non CRRA utilities. 
- I encountered non-convergence issues that prompt me to deepen my understanding of finite-difference schemes such that policy iteration actually converges. 
### Log. 
- Researched upwinding and stability writing up a small document on the effects of upwinding on forwards and backwards Euler schemes. Understood the idea of Von-Neumann stability calculations. Concretely, in Von-Neumann stability calculations you assume that a solution to the difference equation can be decomposed into fourier modes with a growth coefficient that needs to be controlled. Didn't analyse convergence or numerical dispersion which can occur in backward euler schemes with central-differences despite unconditional convergence. 
- Did not find the root cause for the non-convergence of the policy iteration loop of the HJB solver, however. 
- Next: Come up with a policy iteration toy-model to see if there might be a problem there. 

## 2025-10-07
- tried to come up with a toy model that would show how policy iteration works in practice. Failed to come up with anything that wasn't bang-bang or with complicated state controls. 
- Found that LQR problems are the canonical example 
- Interogated Ai about why this is the case which yielded a number of interesting difficulties when solving optimal control problems. It became increasingly evident that the merton problem was actually non-trivial. 
- Found very recent papers talking about FDM schemes and policy iteration for the merton problem with non-Hara utilities that suggest again the non-triviality of the project. 
- Next: implement toy policy iteration model for LQR followed by a bit of an analysis of the merton problem (viscocity solutions etc.) to see if the project is salvagable. 

## 2025-10-15
- The last week I have been working intermittently on a toy model for policy iteration: the 1D LQR optimal control problem.
- After solving a simple problem by hand, I proceeded to try and develop a finite difference solver for the problem. 
- Implicit scheme for the PDE was robust without a policy iteration loop (effectively keeping the control constant at zero). The behaviour of the state variable was correctly approximated. 
- With a policy iteration optimal control loop, we experienced serious divergences. I used forward differences in the hope it would be sufficiently numerically robust for initial testing. The divergences were so extreme they led to overflow errors.
- I implemented an upwind scheme in order to mitigate the instabilities. Non-convergence of the objective function is still a problem however. It may be an implementation error
- Next: Understand whether the behaviour is a numerical instability or an implementation error. 
- Pause: The project's scope is extending far beyond what was initially intended. In order to stop it being an interminable time sync, I have decided to move onto my next two project and return once those are finished. It will also keep my motivation higher. 

## Notes & References
- https://www.math.chalmers.se/~donnerda/StochasticControl.pdf
- Merton, R.C., 1971. “Optimum Consumption and Portfolio Rules in a Continuous-Time Model”
- Merton, R.C., 1969 "Lifetime portfolio Selection under Uncertainty"
- Numerical methods: finite difference, dynamic programming, Monte Carlo