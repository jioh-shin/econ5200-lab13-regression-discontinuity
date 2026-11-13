# Regression Discontinuity: Bandwidths, Manipulation and Close Elections

## Objective
In this lab, I studied how bandwidth selection and manipulation affect regression discontinuity (RD) estimates and applied RD to close US House elections.

## Methodology
- Simulated a grant program with a true treatment effect of 8 percentage points at the cutoff.
- Compared a global quadratic regression with a local linear regression using a data-driven bandwidth of 16.1.
- Repeated the simulation 300 times to compare estimation errors across different bandwidths.
- Tested for manipulation of the running variable using a density test and checked covariate continuity around the cutoff.
- Applied RD to close US House elections using the setting from Lee, Moretti and Butler (2004).
- Wrote my own local linear RD estimator using a triangular kernel and compared its results with the `rdrobust` package.

## Key Findings
- **Bandwidth selection:** The global quadratic model estimated a treatment effect of 0.0357, while the local linear model estimated 0.0789, which was much closer to the true effect of 0.08.
- **Simulation results:** Across 300 simulations, a bandwidth of 20 produced the lowest root mean squared error (RMSE).
- **Manipulation test:** The density test gave a p-value of 0.0022 when units moved across the cutoff, indicating evidence of manipulation.
- **Close elections:** I estimated that a district represented by a Democrat who barely won had an ADA score 46.491 points higher than a district where a Democrat barely lost.
- **Custom estimator:** I implemented a local linear RD estimator with triangular kernel weights and checked its estimates against `rdrobust`.

Overall, this lab helped me understand why bandwidth choice and checking the assumptions around the cutoff matter when interpreting RD estimates.
