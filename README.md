# EHR Yield Prediction

Code companion for the manuscript **“Predicting Annotation Yield in AI‑Ranked Electronic Health Record Cohorts: A Regression‑Based Screening‑Saturation Framework.”**

This repository contains Jupyter notebooks and minimal demo data illustrating how to:

1. **Pre‑process free‑text neurology notes** (map note‑level annotation codes and combine yearly files).  
2. **Train yield‑prediction models** (linear, polynomial & SV regressions plus a small PyTorch MLP).  
3. **Generate screening‑saturation curves** that tell reviewers *when to stop* manual chart review.  
4. **Recreate Figure 2** from the manuscript.

> **Important:** The full, PHI‑containing clinical notes cannot be shared publicly. Only **aggregated, de‑identified Excel exports** (`preprocessed_2013.xlsx`, `preprocessed_2020.xlsx`) are included so you can run the notebooks end‑to‑end.

---

## Repository layout

```
.
├── ehr-yield-prediction.ipynb   # full pipeline: data prep → model training → evaluation
├── figure2_notebook.ipynb       # plots the main screening‑saturation figure
├── preprocessed_2013.xlsx       # de‑identified sample for 2013
├── preprocessed_2020.xlsx       # de‑identified sample for 2020
└── LICENSE                      # MIT
```

---

## Quick start

```bash
# clone
git clone https://github.com/assaflandschaft/ehr-yield-prediction.git
cd ehr-yield-prediction

# create & activate environment (conda example)
conda create -n ehr_yield python=3.10 -y
conda activate ehr_yield

# install core dependencies
pip install pandas numpy scikit-learn matplotlib seaborn torch==2.*

# launch Jupyter
jupyter notebook
```

Open **`ehr-yield-prediction.ipynb`**, run the cells, and inspect the printed workload‑reduction metrics and plots.

If you wish to test on your own score‑ranked dataset, replace the Excel files with your data and update the `DATA_FILES_YYYY` lists at the top of the notebook.

---

## Reproducing the paper’s Figure 2

Simply run **`figure2_notebook.ipynb`**. The notebook loads the pre‑trained polynomial model from the main pipeline and renders the screening‑saturation curve shown in the manuscript.

---

## Dependencies

* Python ≥ 3.9  
* pandas, numpy, scikit‑learn, matplotlib, seaborn  
* PyTorch 2.x (for the optional neural‑net regression)

Optional: `notebook` or `jupyterlab` for interactive use.

---

## License

Released under the **MIT License** – see `LICENSE`.

