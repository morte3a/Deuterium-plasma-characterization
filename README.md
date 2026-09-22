# Deuterium Plasma Characterization

A computational plasma-physics project for investigating the dependence of fundamental plasma parameters on **plasma density, magnetic field, and temperature** using the [PlasmaPy](https://www.plasmapy.org/) library.

The project uses a deuterium plasma model and combines numerical calculations with log-log visualizations to study characteristic plasma quantities and their physical behavior under different plasma conditions.

---

## Project Overview

The main objective of this project is to develop a computational workflow for calculating and visualizing fundamental plasma parameters using Python and PlasmaPy.

The analysis considers:

* **Density dependence**
* **Magnetic-field dependence**
* **Temperature dependence**

The calculated quantities include:

* Alfvén speed
* Ion inertial length
* Debye length
* Electron plasma frequency
* Gyrofrequency
* Larmor radius
* Thermal speed
* Plasma beta

---

## Plasma Model

The calculations are based on a deuterium plasma consisting of:

* Ion species: **D⁺**
* Electron species: **e⁻**

### Reference conditions

| Parameter            |                      Value |
| -------------------- | -------------------------: |
| Ion density          | $10^{19}\ \mathrm{m^{-3}}$ |
| Ion temperature      |          $10\ \mathrm{eV}$ |
| Electron temperature |          $10\ \mathrm{eV}$ |
| Magnetic field       |            $1\ \mathrm{T}$ |

These reference conditions are used for the baseline plasma characterization and as fixed parameters when varying individual plasma properties.

---

## Parameter Scans

### Density scan

The ion density is varied from:

$$
10^{17} \leq n \leq 10^{21}\ \mathrm{m^{-3}}
$$

using 20 logarithmically spaced points.

The following quantities are investigated:

* Alfvén speed
* Ion inertial length
* Debye length
* Electron plasma angular frequency
* Plasma beta

### Magnetic-field scan

The magnetic field is varied from:

$$
0.1 \leq B \leq 10\ \mathrm{T}
$$

using 20 logarithmically spaced points.

The following quantities are investigated:

* D⁺ gyrofrequency
* Electron gyrofrequency
* D⁺ Larmor radius
* Electron Larmor radius
* Plasma beta

### Temperature scan

The plasma temperature is varied from:

$$
1 \leq T \leq 1000\ \mathrm{eV}
$$

using 20 logarithmically spaced points.

The following quantities are investigated:

* Plasma beta
* D⁺ Larmor radius
* Electron Larmor radius
* D⁺ thermal speed
* Electron thermal speed

---

## Reference Results

For the reference conditions

$$
n = 10^{19}\ \mathrm{m^{-3}}, \qquad
T_i=T_e=10\ \mathrm{eV}, \qquad
B=1\ \mathrm{T},
$$

the calculated quantities include:

| Quantity                          |                               Value |
| --------------------------------- | ----------------------------------: |
| Alfvén speed                      |      $4.88\times10^6\ \mathrm{m/s}$ |
| Ion inertial length               |     $1.02\times10^{-1}\ \mathrm{m}$ |
| Debye length                      |     $7.43\times10^{-6}\ \mathrm{m}$ |
| Electron plasma angular frequency | $1.78\times10^{11}\ \mathrm{rad/s}$ |
| D⁺ thermal speed                  |      $3.10\times10^4\ \mathrm{m/s}$ |
| Electron thermal speed            |      $1.88\times10^6\ \mathrm{m/s}$ |
| D⁺ Larmor radius                  |     $6.46\times10^{-4}\ \mathrm{m}$ |
| Electron Larmor radius            |     $1.07\times10^{-5}\ \mathrm{m}$ |
| Total plasma beta                 |                 $8.05\times10^{-5}$ |

The low reference plasma beta indicates that, under these conditions, the magnetic pressure is much larger than the thermal pressure.

---

## Software and Libraries

This project was developed using Python and the following libraries:

* **PlasmaPy 2026.2.0** — plasma physics calculations
* **Astropy** — physical units and constants
* **NumPy** — numerical calculations
* **Matplotlib** — data visualization
* **Pandas** — organizing calculated results
* **Jupyter** — notebook environment
* **JupyterLab** — interactive development environment

All required packages are listed in `requirements.txt`.

To install the dependencies:

```bash
pip install -r requirements.txt
```

---

## Project Structure

```text
deuterium-plasma-characterization/
│
├── README.md
├── requirements.txt
└── plasma_characterization.ipynb
```

---

## Reproducibility

The calculations are implemented in a Jupyter Notebook using SI units through Astropy and plasma-physics functions provided by PlasmaPy.

The notebook contains the complete workflow, from defining plasma conditions to calculating and visualizing the selected plasma parameters.

To reproduce the analysis:

1. Install the required Python packages using `requirements.txt`.
2. Open `plasma_characterization.ipynb` in JupyterLab.
3. Run the notebook cells from top to bottom.

---

## Purpose

This project was developed as a computational plasma-physics study to strengthen practical experience with:

* Python for scientific computing
* PlasmaPy
* Astropy units
* Numerical parameter scans
* Plasma-physics calculations
* Scientific visualization
* Physical interpretation of plasma parameters
* Reproducible computational research
