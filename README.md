# 🦠 COVID-19 Global Analysis

## 📓 View Notebook

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Saif-Ahmed0/covid19-global-analysis/blob/main/covid_19_clean_complete.ipynb)
[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.org/github/Saif-Ahmed0/covid19-global-analysis/blob/main/covid_19_clean_complete.ipynb)

> ⚠️ Interactive charts (Plotly) are not supported on GitHub.
> Open the notebook via Google Colab to view all charts and animated maps.

---

## 🔍 Project Overview

Exploratory Data Analysis (EDA) and Machine Learning on the global COVID-19 dataset, tracking the spread of the pandemic across countries and time, with predictive modeling on confirmed cases.

---

## 📁 Dataset

> ⚠️ The dataset is not included in this repo.
> Download it from Kaggle and place it in a `DATA/` folder:

📥 [COVID-19 Clean Complete Dataset — Kaggle](https://www.kaggle.com/datasets/imdevskp/corona-virus-report)

### Dataset Features:

| Column | Description |
|--------|-------------|
| `Date` | Date of record |
| `Country/Region` | Country name |
| `Province/State` | Province or state (if applicable) |
| `Confirmed` | Total confirmed cases |
| `Deaths` | Total deaths |
| `Recovered` | Total recovered cases |
| `Active` | Active cases (engineered feature) |
| `WHO Region` | WHO regional classification |

---

## 🔬 Project Steps

### 1. Data Loading & Cleaning
- Loaded dataset with date parsing
- Created `Active` column: `Confirmed - Deaths - Recovered`
- Standardized country names (e.g. `Mainland China` → `China`)
- Filled missing `Province/State` values with empty string

### 2. Exploratory Data Analysis (EDA)
- Aggregated confirmed, deaths, recovered, and active cases per country
- Analyzed the latest global snapshot of the pandemic
- Built a country-level summary table with background gradient highlighting
- Plotted pairwise relationships between all numeric features

### 3. Visualizations
- **Time series plot** — Confirmed vs Recovered cases over time (Plotly)
- **Choropleth map** — Total confirmed cases per country (Plotly)
- **Animated scatter map** — Spread of confirmed cases and deaths over time (Plotly Express)
- **Pairplot** — Correlation between Confirmed, Deaths, Recovered, and Active (Seaborn)

### 4. Machine Learning Models

#### 📈 Polynomial Regression
- Used `Date` as the independent variable
- Predicted confirmed cases over time
- Applied degree-10 polynomial features for curve fitting

#### 📈 Linear Regression
- Features: `Confirmed`, `Recovered`, `Active`, `WR_LE` (encoded WHO Region)
- Target: `Deaths`
- Applied **Label Encoding** on `WHO Region`
- Evaluated using **R² Score**

---

## 🛠️ Tools & Libraries

| Library | Usage |
|---------|-------|
| `Pandas` | Data loading and manipulation |
| `NumPy` | Numerical operations |
| `Seaborn` | Statistical visualizations |
| `Matplotlib` | Plotting charts |
| `Plotly` | Interactive charts and animated maps |
| `Scipy` | Statistical analysis |
| `Scikit-learn` | Machine Learning models and preprocessing |

---

## 🚀 How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/Saif-Ahmed0/covid19-global-analysis.git
   ```

2. Download the dataset from Kaggle and place it in a `DATA/` folder:
   ```
   covid19-global-analysis/
   └── DATA/
       └── covid_19_clean_complete.csv
   ```

3. Install requirements:
   ```bash
   pip install pandas numpy seaborn matplotlib plotly scipy scikit-learn kaleido==0.1.0post1
   ```

4. Open the notebook:
   ```bash
   jupyter notebook covid_19_clean_complete.ipynb
   ```
