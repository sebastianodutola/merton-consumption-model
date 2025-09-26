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

---

## Learning Goals
- [ ] Understand stochastic calculus essentials (Ito's lemma, SDEs)
- [ ] Understand the Hamilton-Jacobi-Bellman (HJB) equation
- [ ] Learn numerical methods for solving HJB equations
- [ ] Understand optimal consumption-investment strategies in continuous-time finance

---

# Merton Project 5-Day Sprint Checklist

## Day 1 — 2025-09-22 ✅
- [x] Read Merton (1971) paper
- [o] Take structured notes in `notebooks/merton_notes.ipynb`
- [o] Sketch intuition diagrams (wealth evolution, consumption-investment trade-offs)
- [x] Add end-of-day log entry in `project_log.md`

## Day 2 — 2025-09-23
- [ ] Implement baseline wealth SDE: `dW_t = (r W_t + π_t(μ-r) - C_t) dt + π_t σ dB_t`
- [ ] Run simple simulations with fixed consumption/investment
- [ ] Plot sample paths of wealth evolution
- [ ] Log progress in `project_log.md`

## Day 3 — 2025-09-24
- [ ] Set up Hamilton-Jacobi-Bellman (HJB) equation
- [ ] Implement numerical solver (finite difference / dynamic programming)
- [ ] Test solver with simple parameters
- [ ] Visualize optimal consumption/investment strategies
- [ ] Log findings in `project_log.md`

## Day 4 — 2025-09-25
- [ ] Generate Monte Carlo simulations of wealth evolution
- [ ] Compare strategies under different parameters: risk aversion, horizon, volatility
- [ ] Plot consumption vs wealth, portfolio allocations, wealth paths
- [ ] Debug discrepancies between HJB solution and simulations
- [ ] Update notebook with plots and results

## Day 5 — 2025-09-26
- [ ] Introduce constraints (e.g., no borrowing, discrete-time steps)
- [ ] Optional: extend to multi-asset or stochastic interest rate
- [ ] Clean up code in `src/`
- [ ] Finalize notebooks and visualizations
- [ ] Update `README.md` with project overview, methodology, key plots
- [ ] Add final project log entry

## Notes & References
- https://www.math.chalmers.se/~donnerda/StochasticControl.pdf
- Merton, R.C., 1971. “Optimum Consumption and Portfolio Rules in a Continuous-Time Model”
- Merton, R.C., 1969 "Lifetime portfolio Selection under Uncertainty"
- Numerical methods: finite difference, dynamic programming, Monte Carlo