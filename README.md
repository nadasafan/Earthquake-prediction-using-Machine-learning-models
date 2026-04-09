# Earthquake Magnitude Forecasting in Los Angeles

## How Validation Strategy Inflates Earthquake Forecasting Performance

A study quantifying temporal data leakage in ML-based earthquake forecasting, demonstrating that random train–test splits inflate reported accuracy by **74%** compared to prospective evaluation.

### Key Finding

| Validation Strategy | Mean Accuracy (11 Models) |
|---|---|
| Random Split | **0.593** |
| Temporal Validation | 0.266 |
| Prospective Test | **0.157** |

> Random splitting overestimates prospective performance by 74%, demonstrating that widely reported high accuracies in earthquake ML literature are substantially attributable to temporal data leakage.

### Overview

- **18,030 events** from the SCEDC catalog (1966–2007, M ≥ 2.0, 50 km radius around LA)
- **27 engineered features** (seismological, temporal, spatial, magnitude-based)
- **19 models**: 11 ML classifiers, 6 neural networks (CNN, RNN, LSTM, GRU, Transformer, MLP), 2 ensembles
- **Forward-chaining temporal validation**: Train (pre-2004) → Validation (2004–2005) → Prospective (2006+)
- **Binary classification** (M ≥ 4.0): SVM achieves **88.3% prospective accuracy**
- **63 references**, 20 figures, 9 tables, 20 equations with full symbol definitions

### Repository Structure

```
├── Dataset/
│   ├── Earthquake_Data.csv          # SCEDC earthquake catalog
│   ├── Earthquake.ipynb             # Original exploration notebook
│   └── Processed_data/
│       └── Earthquake_data_processed.xlsx
├── paper_figures/                   # All 20 publication-quality figures (300 DPI)
├── EDA_J_Component.ipynb            # Main analysis notebook
├── Research_Paper.docx              # Full manuscript (Q1-ready)
├── Earthquake_Visualization.twb     # Tableau visualization
├── requirements.txt                 # Python dependencies
└── README.md
```

### Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
xgboost
lightgbm
tensorflow
jenkspy
scipy
shap
statsmodels
openpyxl
python-docx
```

### Installation

```bash
pip install -r requirements.txt
```

### Models Evaluated

**Classical ML:** XGBoost, Random Forest, LightGBM, Gradient Boosting, MLP, Decision Tree, SVM, k-NN, AdaBoost, Logistic Regression, Naive Bayes

**Neural Networks (temporal sequences, L=10):** CNN, RNN, LSTM, GRU, Transformer, MLP-Keras

**Ensembles:** Soft Voting, Stacking (LR meta-learner)

**Baselines:** Majority Class, b-value Binning

### Citation

If you use this work, please cite:

```
@article{earthquake_leakage_2026,
  title={How Validation Strategy Inflates Earthquake Forecasting Performance: 
         A Temporal Leakage Analysis Using Machine Learning and Neural Networks 
         in Los Angeles},
  year={2026}
}
```

### Data Source

Southern California Earthquake Data Center (SCEDC): https://scedc.caltech.edu

### License

This project is for academic research purposes.
