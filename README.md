# Notebooks: 2D SU(N) gauge theory from independent plaquettes via holonomies

Notebooks and scripts used to produce the numerical results of the paper

> **Sampling SU(N) gauge theory on a 2D lattice from independent plaquettes via
> holonomies and corner reweighting**
> Javad Komijani, [arXiv:2610.09147](https://arxiv.org/abs/2610.09147)

## Requirements

The notebooks were run with

- [lattice_ml](https://github.com/jkomijani/lattice_ml) **v0.2.0**
  (commit [`843f412`](https://github.com/jkomijani/lattice_ml/commit/843f4121e1a0182de480678e6859733f8eaa6d71))
- [normflow](https://github.com/jkomijani/normflow) **v3.0.0**
  (commit [`6f824df`](https://github.com/jkomijani/normflow/commit/6f824df1f2b26134b737c3aafc77779ec1b0ca28))

together with PyTorch, NumPy, and Matplotlib. To install exactly these versions:

    pip install -r requirements.txt

The plots use `matplotlib` with `text.usetex = True`, which requires a working
LaTeX installation; set it to `False` in the cell that imports `matplotlib` otherwise.

## Contents

| Path | Produces |
|---|---|
| `notebooks/su2/SU2_2D_holonomy_2x2_beta2.ipynb` | SU(2), 2×2, β = 2: row of Table I, panel of the SU(2) Wilson-loop figure |
| `notebooks/su2/SU2_2D_holonomy_2x2_beta8.ipynb` | SU(2), 2×2, β = 8 |
| `notebooks/su2/SU2_2D_holonomy_32x32_beta4.ipynb` | SU(2), 32×32, β = 4 |
| `notebooks/su2/SU2_2D_holonomy_32x32_beta8.ipynb` | SU(2), 32×32, β = 8 |
| `notebooks/su3/SU3_2D_holonomy_2x2_beta3.ipynb` | SU(3), 2×2, β = 3: row of Table I, panel of the SU(3) Wilson-loop figure |
| `notebooks/su3/SU3_2D_holonomy_2x2_beta12.ipynb` | SU(3), 2×2, β = 12 |
| `notebooks/su3/SU3_2D_holonomy_32x32_beta6.ipynb` | SU(3), 32×32, β = 6 |
| `notebooks/su3/SU3_2D_holonomy_32x32_beta12.ipynb` | SU(3), 32×32, β = 12 |
| `notebooks/corner_sampler/su3_group_commutator_selflearning.ipynb` | Training of the SU(3) conditional sampler of (X, Y) given the group commutator Z |
| `analysis/analyze_pulls.py` | Figure of the normalized deviations between NF and HMC Wilson loops (data embedded in the script) |

Each lattice notebook trains (or loads) the single-plaquette normalizing flow,
samples plaquettes independently with an accept/reject step, builds the link
configurations via holonomies with the corner weights, and compares Wilson loops
with an independent HMC run. The stored outputs are those reported in the paper.
