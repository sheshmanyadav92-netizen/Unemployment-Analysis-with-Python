# Unemployment Analysis in India: COVID-19 Impact Assessment

A senior data analyst portfolio study investigating the macroeconomic and labor market disruptions across Indian states and union territories during the COVID-19 pandemic in 2020.

---

## 📌 Project Overview
On **March 25, 2020**, the Government of India instituted a nationwide lockdown to curb the transmission of COVID-19. This project delivers an exploratory data analysis (EDA) evaluating:
- Pre-pandemic labor market stability (January – February 2020).
- The severity, magnitude, and regional dispersion of the lockdown shock (March – May 2020).
- The trajectory and velocity of the post-lockdown V-shaped recovery (June – October 2020).
- Macroeconomic dynamics between unemployment rate, labor force participation, and absolute employment headcount.

---

## 📂 Project Structure
```text
Task-2-Unemployment-Analysis/
├── unemployment_analysis.ipynb    # Clean, fully-executed, annotated Jupyter Notebook
├── data/
│   └── Unemployment in India.csv  # Kaggle panel dataset (267 records, 9 attributes)
└── README.md                      # Project documentation and summary of findings
```

---

## 📊 Dataset Information
- **Source**: Kaggle – [Unemployment in India by Gokul Raj Kuppan](https://www.kaggle.com/datasets/gokulrajkmv/unemployment-in-india)
- **File**: `data/Unemployment in India.csv`
- **Granularity**: Monthly observations across 27 Indian states and Union Territories across 5 macro-regions.
- **Attributes**:
  - `region`: State or Union Territory name.
  - `date`: Monthly observation timestamp (formatted with `dayfirst=True`).
  - `frequency`: Data recording frequency (`Monthly`).
  - `unemployment_rate`: Estimated unemployment rate (`%`).
  - `employed`: Total estimated count of employed persons (headcount).
  - `labour_participation_rate`: Percentage of the working-age population active in the labor force (`%`).
  - `macro_region`: Broader geographic zone (*South, Northeast, East, West, North*).
  - `longitude` & `latitude`: Geographic coordinates.

---

## ⚙️ Installation & How to Run
Ensure Python 3.9+ is installed, then install the required dependencies:

```bash
pip install pandas matplotlib seaborn jupyter
```

Launch the Jupyter Notebook environment:

```bash
jupyter notebook Task-2-Unemployment-Analysis/unemployment_analysis.ipynb
```
Or execute from within the `Task-2-Unemployment-Analysis/` folder:
```bash
cd Task-2-Unemployment-Analysis
jupyter notebook unemployment_analysis.ipynb
```

---

## 📑 Notebook Outline
1. **Setup & Environment Configuration**: Package imports (`pandas`, `matplotlib`, `seaborn`, `numpy`), seed pinning (`random_state=42`), unified styling theme, and reusable visualization helper functions.
2. **Load & Inspect Dataset**: Data ingestion from `data/Unemployment in India.csv`, shape confirmation, data type profiling, null check, and duplicate verification.
3. **Data Cleaning & Feature Engineering**: Leading/trailing whitespace stripping, snake_case standardization, datetime parsing (`dayfirst=True`), and calendar feature extraction (`year`, `month`, `month_name`).
4. **Exploratory Data Analysis (EDA)**: State-wise statistical summary table (mean, median, standard deviation, range) and monthly national average unemployment rate trend.
5. **Time Series Analysis**: Multi-line comparative trajectory for 4 major bellwether states (*Delhi, Maharashtra, Tamil Nadu, Kerala*) with the March 25, 2020 COVID lockdown benchmark marked via `axvline`.
6. **Comparative State Rankings**: Sorted bar chart of the top 10 states by average unemployment rate with explicit on-bar percentage labels.
7. **Correlation Analysis & Headcount Caveat**: Pearson correlation heatmap with an explicit methodological note explaining that `employed` is an absolute headcount rather than a per-capita rate.
8. **Pre- vs. Post-COVID-19 Impact Assessment**: Segmentation at March 25, 2020, national summary comparisons, top 5 most affected states table, and grouped comparative bar chart reporting relative percentage changes.
9. **Conclusion & Limitations**: Comprehensive summary of 4 key analytical findings and 3 methodological constraints.

---

## 📈 Key Findings (From Executed Results)
1. **Unprecedented Lockdown Shock**: The national monthly average unemployment rate jumped from **9.20% in January** and **9.27% in February** to an all-time peak of **23.24% in May 2020** (a **+140%+ surge** relative to baseline).
2. **V-Shaped Labor Recovery**: As phased "Unlock" reopenings commenced, national unemployment dropped sharply to **10.91% in June** and steadily normalized to **8.03% by October 2020**, closing below the pre-pandemic baseline.
3. **Extreme Disparities in State Vulnerability**: Coastal and industrialized regions faced severe immediate shocks despite near-zero pre-pandemic baselines:
   - **Puducherry**: surged from **1.17%** to **22.14%** (+20.97 pp, **+1,791.88% relative increase**).
   - **Tamil Nadu**: leaped from **1.83%** to **14.78%** (+12.95 pp, **+707.45% relative increase**), peaking at **49.83% in April**.
   - Conversely, **Haryana (27.48%)** and **Tripura (25.06%)** suffered from chronically elevated structural unemployment across the entire period.
4. **Dual Contraction in Employment and Participation**: Comparing the pre-lockdown phase to post-lockdown, the national average employed headcount fell from **15.56M to 13.57M** per state (**-12.77% relative contraction**, shedding ~1.99M jobs per state on average), while the average labor force participation rate dropped from **44.40% to 41.02% (-7.61%)**.
5. **Macroeconomic Correlation Dynamics**: Unemployment rate showed a modest negative correlation (**r = -0.245**) with employed headcount. Labor force participation remained relatively rigid (**r = -0.074** with unemployment rate), indicating that the surge was driven primarily by an inability of active job seekers to secure employment rather than mass exit from the labor force.

---

## ⚠️ Analytical Limitations
- **Short Pre-COVID Baseline**: Only 2 pre-lockdown months (Jan–Feb 2020) are available, limiting longitudinal modeling and seasonal adjustments.
- **State-Level Aggregation**: Broad geographical aggregation obscures rural agrarian vs. urban industrial discrepancies and informal sector nuances.
- **Correlation is Not Causation**: External factors including reverse labor migration, local containment zones, and agricultural crop cycles coincided with the lockdown phases.
