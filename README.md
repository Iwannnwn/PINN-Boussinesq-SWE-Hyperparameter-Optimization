# PINN-SWE Hyperparameter Optimization

This repository contains Physics-Informed Neural Network (PINN) experiments for the Shallow Water Equations (SWE). The project focuses on comparing baseline PINN training with hyperparameter optimization methods such as Bayesian Optimization (BO) and BOHB across several shallow-water flow scenarios.

## Overview

The notebooks in `sourcecode/` model two primary variables:

- `h`: water depth.
- `u`: flow velocity.

The experiments consider three benchmark problems for Boussinesq-type shallow water flow:

- Wet-wet dam break.
- Wet-dry dam break.
- Undular bore.

These benchmark scenarios are adapted from the Boussinesq-type equation test cases discussed in Magdalena et al. (2024).

> Magdalena, I., Haloho, D. N., & Adityawan, M. B. (2024). *Numerical approaches for Boussinesq type equations with its application in Kampar River, Indonesia*. **Mathematics and Computers in Simulation**, 225, 820–834.


## Project Structure

```text
.
|-- sourcecode/      # Main experiment notebooks
|-- best_models/     # Best models, parameters, training histories, studies, and trial logs
|-- figures/         # Loss history, water depth, and velocity visualizations
|-- README.md
|-- requirements.txt
`-- .gitignore
```

## Installation

Python 3.10 or 3.11 is recommended for better TensorFlow compatibility.

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

On Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## Usage

1. Activate the virtual environment.
2. Start JupyterLab or Jupyter Notebook.
3. Open a notebook from `sourcecode/` based on the scenario or optimization method you want to run.

```bash
jupyter lab
```

Example notebooks:

- `sourcecode/riset-shallow-water-wetwet-dam-break.ipynb`
- `sourcecode/riset-shallow-water-wetdry-dam-break.ipynb`
- `sourcecode/riset-shallow-water-undular-bore.ipynb`
- `sourcecode/riset-shallow-water-bayesian-optimization-wetwet.ipynb`
- `sourcecode/riset-shallow-water-bohb-wet-wet.ipynb`

## Experiment Artifacts

The `best_models/` directory stores training and optimization artifacts, including:

- Keras models for `h_model` and `u_model`.
- `best_params.json` files.
- Training histories in `.pkl` format.
- Optuna study and trial histories in `.pkl` and `.csv` formats.

The `figures/` directory stores experiment visualizations for:

- Loss history.
- Water depth.
- Velocity.

## Notes

Some notebooks may take a long time to run, especially hyperparameter optimization experiments. Before rerunning experiments, check the output paths to avoid overwriting artifacts you still want to keep.

## Citation

If you use this repository, please cite:

```bibtex
@article{Viadinguroho2026,
  author  = {Raden Aurelius Andhika Viadinguroho and Triwanto and Vincent Sie and Bandung Arry Sanjoyo and Chairul Imron and Didik Khusnul Arif},
  title   = {A Bayesian Optimization hyperparameter tuning of Physics-Informed Neural Network for Boussinesq-type Shallow Water Equation},
  year    = {2026}
}
```
