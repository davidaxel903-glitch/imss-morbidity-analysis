# Morbidity Pattern Analysis & Resource Optimization — IMSS & INEGI

Academic consulting project developed at **Tecnológico de Monterrey CDMX**, sponsored by **BBVA** as industry partner · 2024

---

## Overview

This project analyzes national morbidity trends in Mexico using two large public health datasets to help the IMSS (Mexican Social Security Institute) better understand disease patterns and anticipate future demand for medical services.

The analysis follows a full data science workflow — exploratory analysis, predictive modeling, and unsupervised clustering — and results were presented to a BBVA representative.

**Key finding:** Predictive models project a **~25% increase in total patient demand by 2030**, driven primarily by digestive, respiratory, and pregnancy-related conditions.

---

## Datasets

Data is not included in this repository as it is publicly available from official sources.

| File | Source | Description |
|---|---|---|
| `new.csv` | [IMSS Datos Abiertos](https://datos.imss.gob.mx/) | Patient counts by disease, state & year (1995–2020) |
| `total pacientes.csv` | [INEGI — Morbilidad Hospitalaria](https://www.inegi.org.mx/sistemas/olap/proyectos/bd/continuas/salud/MobHospital.asp) | National morbidity across 21 disease categories (2004–2023) |

To run the notebook, download both files and place them in `Proyectos_uni/IMSS/` in your Google Drive, or update the `DATA_PATH` variable to match your folder structure.

---

## Structure

```
imss-morbidity-analysis/
│
├── imss_final.ipynb       # Main analysis notebook
└── README.md
```

---

## Methodology

### Part 1 — IMSS Dataset
- **Vaccine-preventable disease trends**: Tracked polio, measles, rubella, tetanus, influenza, and diphtheria nationally over 25 years
- **Regional disease patterns**: Analyzed dengue, leprosy, and pinto fever across states with highest historical caseloads
- **Top conditions in 2020**: Ranked diseases by total patient volume (acute respiratory infections: 14.5M cases)
- **State-level clustering**: K-Means (k=6) grouped Mexico's 32 states by total patient burden

### Part 2 — INEGI Dataset
- **Trend visualization**: Line plots for all 21 disease categories from 2004 to 2023
- **Predictive modeling**: Three models trained per category with 80/20 train-test split
  - Linear Regression, Decision Tree Regressor, SVR (RBF kernel)
  - Best model selected per category by lowest MSE
- **Disease clustering**: K-Means (k=6) and hierarchical clustering (Ward linkage) grouped categories by patient volume trajectory

---

## Key Results

**IMSS — Vaccine-preventable diseases**
Poliomyelitis, measles, rubella, and diphtheria showed near-zero cases throughout the entire period, confirming the effectiveness of Mexico's national vaccination programs. Influenza showed an upward trend in recent years, warranting continued surveillance.

**IMSS — Regional burden**
Dengue hemorrhagic fever was concentrated in Tabasco and Guerrero. Estado de México, CDMX, and Jalisco account for the highest total IMSS patient volumes — driven by population density and high formal employment rates.

**INEGI — Predictive modeling**
SVR was the best model for 8 of 21 categories, Decision Tree for 7, and Linear Regression for 6. The projected 25% demand increase by 2030 is not uniform — it is driven mainly by digestive, respiratory, and maternal health conditions.

**INEGI — Clustering**
K-Means and hierarchical clustering consistently identified two broad super-clusters: high-burden systemic conditions (digestive, respiratory, maternal) and lower-burden or specialized conditions (neurological, rare diseases, chronic conditions). This segmentation can directly inform resource allocation planning.

---

## Tech Stack

```
Python 3  ·  pandas  ·  NumPy  ·  scikit-learn  ·  matplotlib  ·  scipy
```

---

## How to Run

1. Download the datasets from the links in the Datasets section
2. Place them in `Proyectos_uni/IMSS/` inside your Google Drive (or update `DATA_PATH` to match your folder structure)
3. Open `imss_final.ipynb` in Google Colab
4. Mount your Drive and run all cells in order

---

## Authors

**David Axel Rodríguez Botello** · Yamilet Lozada Rangel · César Daniel Yamada Xochipa · Ignacio Reza Vera

Tecnológico de Monterrey CDMX · 2024
