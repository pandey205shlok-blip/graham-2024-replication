# graham-2024-replication
BEEM136: replication of Graham (2024), Tables I–II, with a specification sensitivity extension.
# Graham (2024): Replication and Specification Extension

BEEM136 — Research Methods I

## Original paper and replication source

Bryan S. Graham (2024), “Sparse Network Asymptotics for Logistic
Regression Under Possible Misspecification,” Econometrica,
92(6), 1837–1868.

Paper DOI: https://doi.org/10.3982/ECTA19051

Original replication package:
https://doi.org/10.5281/zenodo.12811612

This repository documents my course replication and extension.
The original research and supplied replication code are Graham's work.
This repository was created separately; it is not a GitHub fork of
the author's replication package.

## Scope

I reproduced the empirical illustration and calibrated Monte Carlo
experiment associated with Tables I and II.

I did not attempt the additional experiments in Tables III and IV.

The empirical estimation sample contains 351 firms, 39 banks,
and 13,689 possible firm-bank pairs.

## Replication results

The principal regression and Monte Carlo outputs agree with the
published tables to their displayed precision.

For nominal 95% confidence intervals, simulated coverage was:

| Method | Design 1 | Design 2 | Design 3 |
| --- | ---: | ---: | ---: |
| Sparse | 0.9280 | 0.9306 | 0.9044 |
| Dense | 0.5256 | 0.5266 | 0.5052 |

Sparse intervals perform substantially better in these experiments,
but their coverage remains below the nominal 95% level.

## My extension

I removed the interaction between log bank assets and log firm
assets while keeping the same sample and remaining regressors.

| Distance result | Original | Without size interaction |
| --- | ---: | ---: |
| Coefficient | -0.166291 | -0.173043 |
| Sparse standard error | 0.042295 | 0.039286 |
| Observations | 13,689 | 13,689 |

The negative association between distance and lending persists under
this alternative specification. This is a specification sensitivity
check, not evidence of a causal effect.

## Software and workflow

The analysis uses Python and Jupyter Notebook, with the author's
ipt and netrics packages and scientific Python dependencies.

Local setup involved changing author-specific paths, installing
dependencies, and running cells in their required order.

The workflow is:
1. Load packages and the Excel input.
2. Construct firm-bank pairs and regressors.
3. Remove firms or banks with missing regressor data.
4. Estimate the original model with dense and sparse standard errors.
5. Run 5,000 Monte Carlo replications for each of three designs.
6. Summarise the simulation results.
7. Estimate the no-interaction extension and compare results.

## Repository status

Repository preparation is in progress. The executed notebook,
comparison output, exact environment information, and detailed
execution instructions will be added next.

Raw data and local pickle backups are not currently included.
Data access and redistribution terms must be checked before sharing
data-containing files.

Local backups allow results to be restored without rerunning the
simulation. These are convenience files, not a substitute for
documenting reproduction from the original inputs.
