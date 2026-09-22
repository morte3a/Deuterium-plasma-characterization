# ِِDeuterium-plasma-characterization

A computational plasma physics project investigating the dependence of fundamental plasma parameters on **plasma density, magnetic field, and temperature** using [PlasmaPy](https://www.plasmapy.org/), Astropy, NumPy, Matplotlib, and Pandas.

The project focuses on a deuterium plasma and calculates characteristic spatial, temporal, thermal, and magnetic quantities relevant to magnetized plasma physics.

---

## Project Overview

The objective of this project is to numerically investigate how key plasma parameters change when the plasma density, magnetic field, and temperature are varied.

The analysis is performed using the **PlasmaPy** Python library and includes:

* Alfvén speed
* Ion inertial length
* Debye length
* Electron plasma frequency
* Ion and electron thermal speeds
* Ion and electron gyrofrequencies
* Ion and electron Larmor radii
* Plasma beta

The calculations are performed using physically meaningful parameter ranges and the resulting trends are analyzed using log-log plots.

---

## Physical Model

The primary plasma species considered in this project is deuterium:

* Ion: D⁺
* Electron: e⁻
* Electron temperature: 10 eV
* Ion temperature: 10 eV
* Reference density: \(10^{19}\,\mathrm{m^{-3}}\)
* Reference magnetic field: 1 T

The main parameter scans are:

| Parameter      |                                Range | Number of points |
| -------------- | -----------------------------------: | ---------------: |
| Plasma density | \(10^{17}-10^{21}\,\mathrm{m^{-3}}\) |               20 |
| Magnetic field |               \(0.1-10\,\mathrm{T}\) |               20 |
| Temperature    |              \(1-1000\,\mathrm{eV}\) |               20 |

Logarithmically spaced values are used for the parameter scans.

---

## Calculated Plasma Parameters

### Alfvén Speed

The Alfvén speed characterizes the propagation of magnetohydrodynamic disturbances in a magnetized plasma.

At fixed magnetic field and ion species:

$$
v_A \propto n^{-1/2}
$$

Therefore, increasing plasma density results in a decrease in Alfvén speed.

---

### Ion Inertial Length

The ion inertial length is a characteristic spatial scale associated with ion inertia and two-fluid plasma effects.

For a fixed ion species:

$$
d_i \propto n^{-1/2}
$$

The ion inertial length therefore decreases as plasma density increases.

---

### Debye Length

The Debye length characterizes the spatial scale over which electric fields are screened by the plasma.

For fixed electron temperature:

$$
\lambda_D \propto n^{-1/2}
$$

Thus, increasing density produces a shorter Debye length.

---

### Electron Plasma Frequency

The electron plasma angular frequency is given by

$$
\omega_{pe}
=
\sqrt{\frac{n_e e^2}{m_e\epsilon_0}}
$$

and therefore:

$$
\omega_{pe}\propto n_e^{1/2}
$$

The electron plasma frequency increases as the electron density increases.

> Note: PlasmaPy returns the plasma frequency here as an angular frequency in rad/s. The ordinary frequency in Hz is obtained using \(f=\omega/(2\pi)\).

---

### Gyrofrequency

The gyrofrequency is given by

$$
\omega_c=\frac{|q|B}{m}
$$

For a fixed particle species:

$$
\omega_c\propto B
$$

Therefore, both the D⁺ and electron gyrofrequencies increase linearly with magnetic field.

Because electrons have a much smaller mass than deuterium ions, their gyrofrequency is much higher.

---

### Larmor Radius

The Larmor radius is calculated from

$$
r_L=\frac{v_\perp}{\omega_c}
$$

At fixed temperature:

$$
r_L\propto B^{-1}
$$

Therefore, increasing the magnetic field results in a smaller Larmor radius.

The D⁺ Larmor radius is larger than the electron Larmor radius because of the difference in particle mass.

---

### Plasma Beta

Plasma beta represents the ratio of thermal pressure to magnetic pressure:

$$
\beta=
\frac{p_{\mathrm{thermal}}}{p_{\mathrm{magnetic}}}
$$

For a single species:

$$
\beta=
\frac{2\mu_0 n k_B T}{B^2}
$$

Therefore:

$$
\beta\propto n
$$

$$
\beta\propto T
$$

and

$$
\beta\propto B^{-2}
$$

The project confirms these dependencies numerically through density, temperature, and magnetic-field scans.

---

## Reference Results

For the reference conditions

$$
n=10^{19}\,\mathrm{m^{-3}},
\qquad
T=10\,\mathrm{eV},
\qquad
B=1\,\mathrm{T}
$$

the calculated quantities are:

| Quantity                          |                        Value |
| --------------------------------- | ---------------------------: |
| Alfvén speed                      |      \(4.878\times10^6\) m/s |
| Ion inertial length               |     \(1.018\times10^{-1}\) m |
| Debye length                      |     \(7.434\times10^{-6}\) m |
| Electron plasma angular frequency | \(1.784\times10^{11}\) rad/s |
| D⁺ thermal speed                  |      \(3.096\times10^4\) m/s |
| Electron thermal speed            |      \(1.876\times10^6\) m/s |
| D⁺ Larmor radius                  |     \(6.460\times10^{-4}\) m |
| Electron Larmor radius            |     \(1.066\times10^{-5}\) m |
| Electron beta                     |       \(4.027\times10^{-5}\) |
| Total beta                        |       \(8.053\times10^{-5}\) |

The small beta value indicates that, under these reference conditions, magnetic pressure is much larger than the thermal pressure.

---

## Main Scaling Results

The numerical analysis reproduces the expected physical scaling laws:

### Density dependence

$$
v_A\propto n^{-1/2}
$$

$$
d_i\propto n^{-1/2}
$$

$$
\lambda_D\propto n^{-1/2}
$$

$$
\omega_{pe}\propto n^{1/2}
$$

$$
\beta\propto n
$$

### Magnetic-field dependence

$$
\omega_c\propto B
$$

$$
r_L\propto B^{-1}
$$

$$
\beta\propto B^{-2}
$$

### Temperature dependence

$$
\beta\propto T
$$

These relationships provide a useful numerical demonstration of how characteristic plasma scales respond to changes in fundamental plasma parameters.

---

## Software and Libraries

The project was developed in Python using:

* [PlasmaPy](https://www.plasmapy.org/)
* [Astropy](https://www.astropy.org/)
* [NumPy](https://numpy.org/)
* [Matplotlib](https://matplotlib.org/)
* [Pandas](https://pandas.pydata.org/)
* Jupyter / JupyterLab

PlasmaPy is used for the primary plasma-physics calculations, while NumPy, Matplotlib, and Pandas are used for numerical processing, visualization, and organization of results.

---

## Project Structure

```text
deuterium-plasma-characterization/
│
├── README.md
├── requirements.txt
│
└── plasma_characterization.ipynb
```

---

## Reproducibility

To reproduce the analysis:

```bash
pip install -r requirements.txt
```

Then open the Jupyter notebook:

```bash
jupyter lab
```

and run:

```text
plasma_characterization.ipynb
```

---

## Purpose

This project was developed as a computational study of fundamental plasma parameters and as a practical application of Python-based plasma physics analysis.

The main emphasis is on connecting numerical calculations with the underlying physical scaling laws and interpreting how characteristic plasma length, time, velocity, and pressure scales respond to changes in density, magnetic field, and temperature.
