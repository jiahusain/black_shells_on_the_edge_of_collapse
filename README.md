# Black Shells on the Edge of Collapse

This repository contains the Mathematica notebook, Python/Colab analysis code, and simulation samples used for the paper "Black Shells on the Edge of Collapse".

## Contents

| Path | Summary |
| --- | --- |
| `00 Black Shells Code.nb` | Wolfram Mathematica notebook titled "The Mathematics of Black Shells." It derives and checks the black-shell equations used in the paper, including the general shell mathematics, the linearized stability analysis, and the time-domain black-shell evolution system. It also generates the simulation samples used by the Python analysis. |
| `Thesis_code_7_04_2026.ipynb` | Google Colab notebook for the machine-learning and sensitivity-analysis workflow. It loads the Mathematica-generated HDF5 simulations, builds a merged `master_1000.h5` dataset, applies stability-label tests, trains neural-network models, evaluates Fourier Neural Operator predictions, and produces saliency and Sobol sensitivity analyses. |
| `thesis_code_7_04_2026.py` | Python script export of the Colab notebook. It contains the same pipeline in script form, including HDF5 loading, train/test splitting, stability classification, MLP/FNO modeling, plotting helpers, saliency maps, and extra statistics such as dominant-frequency and phase-shift measures. |
| `sims_mix/` | Directory of Mathematica-generated HDF5 simulation files. The current repository copy contains 1,807 files named `sim_*.h5`; these are the raw samples consumed by the Python/Colab workflow. The analysis code expects each sample to provide simulation data such as the time grid, parameters, and state trajectories. |
| `LICENSE` | MIT License for the repository contents. |
| `README.md` | This repository overview and file guide. |

## Workflow Overview

1. Use `00 Black Shells Code.nb` to derive the equations, run the black-shell evolution simulations, and produce the raw `sim_*.h5` files.
2. Use `Thesis_code_7_04_2026.ipynb` or `thesis_code_7_04_2026.py` to merge simulation samples, label stability outcomes, train predictive models, and generate analysis figures.
3. The `sims_mix/` directory provides the raw sample inputs for the Python workflow.

The Python notebook was developed in Google Colab. If running it elsewhere, update the data path that points to `sims_mix/` and ensure the required scientific Python, PyTorch, TensorFlow, `neuraloperator`, `SALib`, and HDF5 dependencies are available.
