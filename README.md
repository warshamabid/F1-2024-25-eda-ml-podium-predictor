# 🏎️ Formula 1 (2024–2025) — EDA & ML Podium Predictor

> End-to-end data science project on real F1 race data — covering Exploratory Data Analysis, Statistical Testing, and a Machine Learning model that predicts podium finishes with **87% accuracy**.

---

## 📌 Project Overview

Formula 1 is one of the most data-rich sports in the world. This project digs into the 2024–2025 F1 seasons to uncover what truly determines race outcomes — qualifying pace, pit stop efficiency, reliability, or raw driver talent?

**Key Question:** Can we predict whether a driver will finish on the podium using only pre-race and in-race telemetry-style features?

---

## 📊 Analyses Performed

| # | Analysis | Technique |
|---|----------|-----------|
| 1 | Driver Championship — 2024 vs 2025 | Grouped bar charts |
| 2 | Constructor Points Progression | Cumulative line plots |
| 3 | Grid Position vs Race Finish | Spearman/Pearson correlation + regression |
| 4 | Pit Stop Strategy Analysis | Distribution plots, team-level medians |
| 5 | DNF & Reliability Breakdown | Bar chart + pie chart |
| 6 | Qualifying (Q3) Times by Team | Box plots |
| 7 | Driver Points Heatmap (Round by Round) | Seaborn heatmap |
| 8 | Sprint Race vs Main Race Performance | Scatter + correlation |
| 9 | ML Podium Predictor | Random Forest, Gradient Boosting, Logistic Regression |

---

## 🤖 Machine Learning Results

**Target:** Will a driver finish on the podium? (Top 3 = 1, else = 0)

**Features used:** Grid position · Driver number · Race round · Laps completed · Season

| Model | Accuracy | ROC-AUC | CV Mean (5-fold) |
|-------|----------|---------|-----------------|
| Random Forest | **87%** | **0.89** | **0.88** |
| Gradient Boosting | ~86% | ~0.88 | ~0.87 |
| Logistic Regression | ~81% | ~0.83 | ~0.82 |

**Top insight:** Grid position alone accounts for >50% of feature importance — qualifying is the race before the race.

---

## 🔑 Key Findings

1. **Grid position is the strongest predictor** — Pearson r = 0.76, p < 0.001
2. **Pole-to-win conversion ≈ 59%** — but 41% of poles don't win, proving strategy & reliability matter
3. **McLaren overtook Red Bull mid-season** — standings crossover happened at Round 14
4. **Reliability cost Red Bull the Constructors title** — Pérez alone: 5 DNFs, 150+ points lost
5. **Median pit stop ≈ 23.2 seconds** — right-skewed, outliers caused by safety car holds
6. **Sprint & main race points correlate strongly** — r > 0.80, consistent performers dominate both formats

---

## 📁 Repository Structure

```
f1-2024-25-eda-ml-podium-predictor/
├── f1-2024-25-eda-ml-podium-predictor.ipynb   # Main notebook
├── README.md                                   # This file
├── requirements.txt                            # Python dependencies
├── .gitignore                                  # Files to exclude
└── images/                                     # Output charts (optional)
    ├── driver_points_2024_2025.png
    ├── constructor_progression.png
    ├── grid_vs_finish.png
    ├── pit_stop_analysis.png
    ├── dnf_analysis.png
    ├── qualifying_boxplot.png
    ├── points_heatmap.png
    ├── ml_rf_results.png
    └── sprint_analysis.png
```

---

## 🚀 How to Run

**1. Clone the repo**
```bash
git clone https://github.com/YOUR_USERNAME/f1-2024-25-eda-ml-podium-predictor.git
cd f1-2024-25-eda-ml-podium-predictor
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Download the dataset from Kaggle**

Dataset: [Formula 1 Live Tracker 2024–2026](https://www.kaggle.com/datasets/devtayyabsajjad/formula-1-live-tracker-2024-2026-dataset)

Place the CSV files inside a `data/` folder:
```
data/
├── race_results.csv
├── driver_standings.csv
├── constructor_standings.csv
├── qualifying.csv
├── pit_stops.csv
├── sprint_results.csv
└── circuits.csv
```

Update `DATA_DIR` in the notebook to point to your local `data/` folder:
```python
DATA_DIR = 'data'
```

**4. Launch Jupyter**
```bash
jupyter notebook f1-2024-25-eda-ml-podium-predictor.ipynb
```

---

## 🗂️ Dataset

- **Source:** [Kaggle — Formula 1 Live Tracker 2024–2026](https://www.kaggle.com/datasets/devtayyabsajjad/formula-1-live-tracker-2024-2026-dataset)
- **Tables:** race_results · driver_standings · constructor_standings · qualifying · pit_stops · sprint_results · circuits
- **Seasons covered:** 2024, 2025
- **Note:** Dataset not included in this repo due to size. Download directly from Kaggle.

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-1.3-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-lightblue)

- **Data:** pandas, numpy
- **Visualization:** matplotlib, seaborn
- **Statistics:** scipy
- **Machine Learning:** scikit-learn (RandomForest, GradientBoosting, LogisticRegression)

---

## 👤 Author

**Warsham Abid**
- 📓 Kaggle Notebook: (https://www.kaggle.com/YOUR_KAGGLE_USERNAME](https://www.kaggle.com/code/warshamm/f1-2024-25-eda-ml-podium-predictor))
- 💼 LinkedIn: (https://www.linkedin.com/posts/warsham-abid-pk_kaggle-datascience-python-ugcPost-7461787894144491520-Pp2Q?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEq0dSEBFa3SVG0jhwbPPZcbQ2G7P7HTCjg))
- 🐙 GitHub: (https://github.com/warshamabid/F1-2024-25-eda-ml-podium-predictor)

---

## 📄 License

This project is open source under the [MIT License](LICENSE).
