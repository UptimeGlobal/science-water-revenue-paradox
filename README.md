# Africa’s Rural Water Revenue Paradox – Data and Code Repository

This repository contains the data and code supporting the manuscript:

“Africa’s Rural Water Revenue Paradox”  
submitted to *Science*.

The study makes a primarily empirical contribution by quantifying the scale and structure of rural water revenues across multiple African countries. Predictive modeling is used as an analytical tool to demonstrate that observed revenue patterns are systematic rather than idiosyncratic.

---

## Repository Structure

```
SCIENCE_WATER_REVENUE_PARADOX/
├── README.md
├── requirements.txt
├── code/
│   ├── 01_eda_and_figures.ipynb
│   └── 02_modeling_and_evaluation.ipynb
    └── figures/
        └── README.md
├── data/
│   ├── analysis_dataset.csv
│   └── README_data.md
├── docs/
│   └── data_code_availability.md
└── outputs/
    └── figures/
        ├── revenue_per_handpump.svg
        ├── revenue_per_m3_scheme.svg
        └── revenue_per_person.svg
```


---

## Data

All analyses in the manuscript are based on the anonymized analytical dataset provided in:

- `data/analysis_dataset.csv`

This dataset is sufficient to reproduce all figures, tables, and modeling workflows reported in the paper. Details on dataset structure and variables are provided in `data/README_data.md`.

---

## Code

The analysis is organized into two Jupyter notebooks:

1. `01_eda_and_figures.ipynb`  
   Generates all descriptive statistics and figures used in the manuscript.

2. `02_modeling_and_evaluation.ipynb`  
   Implements the two-stage predictive modeling framework, including model training, evaluation, LOCO calibration, drift analysis, and learning curves.

---

## Reproducibility

To reproduce the analyses:

1. Install dependencies:

pip install -r requirements.txt


2. Run the notebooks in the following order:
- `01_eda_and_figures.ipynb`
- `02_modeling_and_evaluation.ipynb`

Figures will be saved to the `outputs/figures/` directory.

---

## Notes on Anonymization

For privacy and contractual reasons, precise geographic coordinates were anonymized in the publicly released dataset, and country identifiers were label-encoded. As a result, while the code reproduces the full analytical workflow, numerical results may differ slightly from those reported in the manuscript due to the absence of fine-grained location information.

---

## License

This repository is provided for academic and research use in support of the associated publication.
