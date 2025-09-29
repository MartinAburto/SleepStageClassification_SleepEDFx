
# EL Sleep Stage Classification Project / Proyecto de Clasificación de Etapas del Sueño

**Course / Curso:** EL — Automatic Sleep Stage Classification using EEG (Sleep-EDFx)

## English
### Overview
This repository contains a compact and reproducible pipeline for **automatic sleep stage classification** using EEG signals from **Sleep-EDFx**. It follows a two-step approach inspired by recent literature: (1) feature extraction via **Instantaneous Frequency (IF)** and **Instantaneous Energy (IE)** tracking with **TVAR(2)+Kalman**, and (2) machine-learning classifiers (e.g., **LightGBM/XGBoost**).

### Goals
- Download and organize the Sleep-EDFx dataset locally (not committed to Git).
- Preprocess signals, extract IF/IE features per EEG sub-band (δ, θ, α, β, γ).
- Train/evaluate baseline classifiers with subject-wise cross-validation.
- Report metrics (Accuracy, F1-macro, Cohen’s κ) and produce figures with fixed axes, titles and captions.

### Repository Structure
```
EL_SleepStageClassification/
├─ data/              # Raw data stays here (not tracked); only data/README.md is committed
├─ notebooks/         # Jupyter notebooks (EDA, training, evaluation)
├─ src/               # Reusable modules: preprocessing, feature extraction, modeling
├─ results/           # Saved figures, metrics, reports
├─ requirements.txt   # Dependencies
├─ .gitignore         # Ignore large files & Python cache
└─ README.md          # This file
```

### Setup (Python ≥3.10)
```bash
# 1) Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# 2) Install dependencies
pip install -U pip
pip install -r requirements.txt

# 3) (Optional) Enable Jupyter
python -m ipykernel install --user --name el-sleep --display-name "EL Sleep"
```

### Data: Sleep-EDFx
- Homepage: https://physionet.org/content/sleep-edfx/1.0.0/
- **Do not commit raw data.** Place downloaded EDF and hypnograms under `data/`.
- See `data/README.md` for step-by-step download options (browser / `wget` / Python).

### Quickstart
```bash
# Launch notebooks
jupyter lab  # or: jupyter notebook
# Open notebooks/01_EDA.ipynb and notebooks/02_Model.ipynb
```

### References
- Heliyon 2023 — Abbasi et al.: *Automatic neonatal sleep stage classification: A comparative study*.
- Sensors 2024 — Nateghi et al.: *Model-Based EEG Instantaneous Frequency Tracking for Automated Sleep–Wake Stage Classification*.
- PhysioNet Sleep-EDFx dataset (link above).

---

## Español
### Descripción
Repositorio para **clasificación automática de etapas del sueño** con EEG del dataset **Sleep-EDFx**. Implementa un enfoque en dos pasos: (1) extracción de características **IF/IE** con **TVAR(2)+Kalman** y (2) clasificadores de ML (**LightGBM/XGBoost**), con validación por sujeto.

### Objetivos
- Descargar y organizar Sleep-EDFx localmente (no subir datos al repo).
- Preprocesar señales y extraer IF/IE por bandas (δ, θ, α, β, γ).
- Entrenar/evaluar clasificadores con CV sujeto-a-sujeto.
- Reportar métricas (Accuracy, F1-macro, κ) y generar figuras con ejes fijos, título y nombre de figura.

### Estructura del repositorio
(ver bloque anterior)

### Configuración (Python ≥3.10)
(ver bloque anterior)

### Datos: Sleep-EDFx
- Sitio: https://physionet.org/content/sleep-edfx/1.0.0/
- **No comprometer datos crudos en Git.** Colócalos bajo `data/`.
- Paso a paso en `data/README.md` (navegador / `wget` / Python).

### Inicio rápido
(ver bloque anterior)

### Referencias
- Heliyon 2023 — Abbasi et al.
- Sensors 2024 — Nateghi et al.
- PhysioNet Sleep-EDFx.
