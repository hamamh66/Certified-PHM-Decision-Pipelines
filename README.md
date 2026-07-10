# Certified PHM Decision Pipelines

Companion implementation for **risk assessment of AI-enabled prognostic decision pipelines**. The repository provides a reproducible notebook for auditing target reconstructibility, policy-branch reachability, conformal under-escalation risk, and harm-based maintenance thresholds.

## Overview

The framework treats the complete prognostic decision pipeline

\[
\mathcal{P}=(g,\hat{f},\sigma,\Psi)
\]

as the object of risk assessment:

1. **Health-indicator construction** \(g\)
2. **Predictive model** \(\hat{f}\)
3. **Uncertainty estimation** \(\sigma\)
4. **Maintenance decision policy** \(\Psi\)

Four complementary certificates are evaluated:

| Certificate | Purpose |
|---|---|
| C1 — Target reconstructibility | Detects circular prediction when a constructed target is recoverable from retained constituents |
| C2 — Distributional reachability | Verifies that safety-critical policy branches are operationally reachable |
| C3 — Conformal risk control | Bounds expected under-escalation risk on an ordered maintenance-action lattice |
| C4 — Harm-based thresholds | Derives intervention thresholds from an explicit asymmetric-harm objective |

## Repository contents

- `Certified_PHM_Pipelines_v0.2.ipynb` — executable companion notebook
- `Outputs/Certified_PHM_Pipelines/tables/` — generated CSV tables
- `Outputs/Certified_PHM_Pipelines/figures/` — generated publication-quality figures

The output directories are created automatically when the notebook is executed.

## Main experiments

The notebook includes:

- a deterministic synthetic turbofan-like degradation cohort;
- injected functional target leakage;
- empirical verification that feature-only KS split checks cannot detect functional leakage;
- live and degenerate uncertainty estimators;
- marginal branch-reachability auditing with exact Clopper–Pearson bounds;
- conformal risk calibration over repeated train/calibration/test splits;
- upward and downward override experiments;
- variational maintenance-threshold derivation;
- reproducible export of all tables and figures.

## Requirements

The notebook uses:

- Python 3.12
- NumPy
- pandas
- SciPy
- scikit-learn
- Matplotlib

It can be executed in Google Colab or in a local Jupyter environment.

## Running the notebook

### Google Colab

1. Upload the notebook to Colab.
2. Run all cells in order.
3. Authorize Google Drive access when prompted.
4. Results will be written to:

```text
MyDrive/Outputs/Certified_PHM_Pipelines/
```

### Local execution

Run the notebook in Jupyter Notebook or JupyterLab. Results will be written to:

```text
./Outputs/Certified_PHM_Pipelines/
```

## Reproducibility

The experiments use a fixed random seed:

```python
SEED = 42
```

All generated tables and figures are persisted automatically. The notebook is designed to reproduce the reported certificate outcomes across compatible software environments.

## Scope

The current notebook uses a controlled synthetic cohort so that degradation state, required maintenance tier, and implanted faults are exactly known. It is intended for methodological verification and fault-injection analysis. Real-data benchmark extensions can replace the cohort generator while retaining the same certification workflow.

## Citation

Please cite the associated manuscript when using this repository:

> *Risk Assessment of AI-Enabled Prognostic Decision Pipelines: Leakage, Reachability, Conformal Risk Control, and Harm-Based Maintenance Thresholds.*

A complete bibliographic citation will be added after publication.

## License

A repository license should be selected before public release. The MIT License is suitable for broad reuse of the code, while dataset-specific licenses must be respected for future benchmark integrations.

## Authors

Yazeed Yasin Ghadi, Rahma Zayoud, Abdullah J. Alzahrani, Tehseen Mazhar, Sghaier Guizani, and Habib Hamam.
