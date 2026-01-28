# 1D Shallow Water Equations Simulation

This project implements a numerical solution for 1D Shallow Water Equations using the PyMPDATA library. Jupyter Notebook (project.ipynb) performs the simulation, visualizes the results, and verifies the stability of the solution.

The project is automated using **GitHub Actions** generating report as a **artifact**.

## Description

The main goal of the simulation is to analyze the behavior of a fluid over a given bathymetry (bottom topography). The mathematical model is based on a system of partial differential equations describing the behavior of the fluid column height ($h$) and momentum ($uh$).

#### Project include:

- Numerical Integrator: Utilization of the MPDATA (Multidimensional Positive Definite Advection Transport Algorithm) via the PyMPDATA wrapper.

- Stability Analysis: Comparison of results for different time steps ($dt$) and spatial steps ($dx$) to verify convergence and solution stability.

- Mass Balance: Verification of fluid volume conservation within the domain (taking boundary conditions into account).

- Visualization: Generation of fluid profile plots and flow animations.

## Results

Below is a visualization of the simulation results, showing the different shapes of the free surface over the given bathymetrys.

<img width="1303" height="872" alt="profil_u" src="https://github.com/user-attachments/assets/9f457fbe-e230-4333-b610-9cb8933ac2ad" />


The project also calculates the relative error of the simulation when changing the grid resolution to assess the quality of the numerical solution (e.g., an error magnitude of 0.04%).

## Requirements

The project is written in Python. The following libraries are required:

- numpy – numerical computations

- matplotlib – data visualization

- PyMPDATA – differential equation solver

- open_atmos_jupyter_utils – helper tools for Jupyter visualization

## Local Installation & Usage

To run the project on your local machine (unfortunately, the simulation script takes a lot of time to execute):

Clone the repository:

```bash
git clone https://github.com/Michau-H/shallow-water.git
cd project-name
```

Install dependencies:
It is recommended to use a virtual environment (venv or conda).
```bash
pip install numpy matplotlib PyMPDATA open_atmos_jupyter_utils
```

Run the Jupyter Notebook:
```bash
jupyter notebook project.ipynb
```

## GitHub Actions

The project uses a workflow defined in a .yaml file to automate processes. The main tasks performed by GitHub Actions include:

- Environment Setup: Automatic installation of Python and required libraries.

- Notebook Execution: Running project.ipynb in batch mode (e.g., using papermill or nbconvert) to ensure the code executes without errors.

- Generate artifact with report (in Polish)
