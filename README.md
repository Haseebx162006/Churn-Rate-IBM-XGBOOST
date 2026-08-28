# 📊 Telecom Customer Churn Prediction

A production‑grade machine‑learning pipeline that predicts customer churn for the IBM Telco Customer Churn dataset. The project demonstrates end‑to‑end data processing, feature engineering, model training with XGBoost, and hyper‑parameter optimisation using Optuna.

---

## 🚀 Project Overview

- **Data** – 7043 rows of customer information (demographics, services, usage, etc.)
- **Goal** – Predict the `Churn` column (Yes/No)
- **Model** – XGBoost Classifier tuned with Optuna (TPE sampler)
- **Pipeline** – Scikit‑Learn `Pipeline` + `ColumnTransformer` for clean, leak‑free preprocessing
- **Performance** – ROC‑AUC 86.3 %, Accuracy 80.3 % (tuned) vs. 77.4 % (baseline)

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data manipulation |
| `numpy` | Numerical operations |
| `scikit‑learn` | Pre‑processing, model evaluation |
| `xgboost` | Gradient‑boosted trees |
| `optuna` | Bayesian hyper‑parameter optimisation |
| `openpyxl` | Read the original Excel dataset |
| `matplotlib` / `seaborn` | Visualisation |

---

## 📦 Installation

```bash
# 1. Clone the repo
git clone https://github.com/your-username/telecom-churn.git
cd telecom-churn

# 2. Create a virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

> **Tip** – If you don’t have a `requirements.txt`, install the packages manually:
> ```bash
> pip install pandas numpy scikit-learn xgboost optuna openpyxl matplotlib seaborn
> ```

---

## 📓 Usage

The main notebook `code/churnRate.ipynb` contains the full pipeline. To run it locally:

```bash
jupyter notebook code/churnRate.ipynb
```

### Quick‑start from the command line
You can also run the pipeline as a script (after adding a `main.py` wrapper). For example:

```bash
python -m code.churnRate --data path/to/telecom.xlsx
```

The script will:
1. Load the Excel file.
2. Pre‑process the data.
3. Train an XGBoost model with Optuna tuning.
4. Output evaluation metrics and a `model.pkl` file.

---

## 📈 Model Evaluation

| Metric | Baseline | Tuned | Δ |
|--------|----------|-------|---|
| Accuracy | 77.4 % | 80.3 % | +2.9 % |
| ROC‑AUC | 83.8 % | 86.3 % | +2.5 % |
| F1‑Score | 55.5 % | 61.4 % | +5.9 % |

> The tuned model uses a decision threshold of 0.35 (optimised for F1‑score). Adjust `threshold` in `code/churnRate.ipynb` for different business trade‑offs.

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork** the repository.
2. Create a feature branch: `git checkout -b feature/your-feature`.
3. Commit your changes with clear messages.
4. Push to your fork and open a Pull Request.
5. Ensure all tests pass (if any) and the notebook renders correctly.

### Code Style
- Use `black` for formatting.
- Add type hints where appropriate.
- Keep notebooks tidy – remove unused cells and add markdown explanations.

---

## 📄 License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact

For questions or support, open an issue or reach out to `your.email@example.com`.
