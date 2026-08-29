# 📊 Telecom Customer Churn Prediction

A production‑grade machine‑learning pipeline that predicts customer churn for the IBM Telco Customer Churn dataset. The project showcases end‑to‑end data ingestion, preprocessing, feature engineering, model training with **XGBoost**, and hyper‑parameter optimisation using **Optuna**.

---

## 🚀 Project Overview
- **Dataset**: 7,043 rows, 21 features (demographics, services, usage, etc.)
- **Target**: `Churn` (Yes/No)
- **Model**: XGBoost classifier tuned with Optuna (TPE sampler)
- **Pipeline**: Scikit‑Learn `Pipeline` + `ColumnTransformer` for clean, leak‑free preprocessing
- **Performance**: ROC‑AUC 86.3 %, Accuracy 80.3 % (tuned) vs. 77.4 % (baseline)

---

## 🛠️ Tech Stack
| Library | Role |
|---------|------|
| `pandas` | Data manipulation |
| `numpy` | Numerical operations |
| `scikit-learn` | Pre‑processing, model evaluation |
| `xgboost` | Gradient‑boosted trees |
| `optuna` | Bayesian hyper‑parameter optimisation |
| `openpyxl` | Reading the original Excel dataset |
| `matplotlib` / `seaborn` | Visualisation |

---

## 📦 Installation
```bash
# 1. Clone the repository
git clone https://github.com/your-username/telecom-churn.git
cd telecom-churn

# 2. (Recommended) Create a virtual environment
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```
> **Note**: If a `requirements.txt` is not present, install the core packages manually:
> ```bash
> pip install pandas numpy scikit-learn xgboost optuna openpyxl matplotlib seaborn
> ```

---

## 📓 Usage
The primary notebook `code/churnRate.ipynb` contains the full pipeline.

### Run the notebook
```bash
jupyter notebook code/churnRate.ipynb
```

### Command‑line quick‑start (optional)
A thin wrapper can be added to run the pipeline from the terminal:
```bash
python -m code.churnRate --data path/to/telecom.xlsx
```
The script will:
1. Load the Excel file.
2. Pre‑process the data.
3. Train an XGBoost model with Optuna tuning.
4. Save evaluation metrics and a `model.pkl` artifact.

---

## 📈 Model Evaluation
| Metric   | Baseline | Tuned | Δ |
|----------|----------|-------|---|
| Accuracy | 77.4 %   | 80.3 %| +2.9 % |
| ROC‑AUC | 83.8 %   | 86.3 %| +2.5 % |
| F1‑Score| 55.5 %   | 61.4 %| +5.9 % |

The tuned model uses a decision threshold of **0.35** (optimised for F1‑score). Adjust the `threshold` variable in the notebook if a different trade‑off is required.

---

## 🤝 Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature`.
3. Make your changes and ensure the notebook runs without errors.
4. Commit with clear messages and push to your fork.
5. Open a Pull Request describing the change.

### Code Style
- Format code with **black**.
- Add type hints where appropriate.
- Keep notebooks tidy: remove unused cells and provide explanatory markdown.

---

## 📄 License
This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact
For questions or support, open an issue or contact `your.email@example.com`.
