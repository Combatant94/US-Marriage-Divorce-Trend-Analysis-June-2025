# US Marriage & Divorce Trend Analysis

This repository contains an analysis of state-level marriage and divorce rates in the United States from 1990 to 2021, sourced from the CDC/NCHS National Vital Statistics System. The goal is to uncover nationwide trends, highlight state-specific outliers, and explore relationships between marriage and divorce rates over time.

---

## 📂 Data

* **Source**: CDC/NCHS National Vital Statistics System ([https://www.cdc.gov/nchs/](https://www.cdc.gov/nchs/))
* **Coverage**: State-level marriage and divorce rates, 1990–2021
* **Format**: CSV file with columns: `Year`, `State`, `Marriage_Rate`, `Divorce_Rate`

---

## 🛠️ Methodology

1. **Data Extraction & Cleaning**

   * Loaded CSV and dropped metadata rows.
   * Replaced missing entries (`"---"`) with `NaN` and imputed using column medians.

2. **Exploratory Data Analysis (EDA)**

   * Visualized raw time series for each state’s marriage and divorce rates.
   * Applied Z-normalization to compare trends across states on the same scale.
   * Identified overall national declines and flagged state-level outliers.

3. **Dimensionality Reduction (PCA)**

   * Performed Principal Component Analysis on the marriage and divorce datasets separately.
   * Found PC1 explains \~97.8% of variance for marriage rates and \~85.3% for divorce rates.

4. **Statistical Correlation Analysis**

   * Conducted Pearson correlation tests between marriage and divorce rates on a state-by-state basis.
   * Applied Bonferroni correction (adjusted `p < 0.05`) to control for multiple comparisons.
   * Highlighted significant positive relationships in a summary table.

---

## 📈 Results

* **National Trends**: Marriage rates have steadily declined from \~10.5 per 1,000 population in 1990 to \~6.5 in 2021; divorce rates peaked around 2003 and then gradually decreased.
* **Outliers**: States such as Nevada and Wyoming display atypical patterns needing further investigation.
* **PCA Insights**: A single principal component captures nearly all variance, suggesting a strong common trend across states.
* **Correlations**: Positive correlations in 35 states after Bonferroni correction, indicating that higher marriage rates often accompany higher divorce rates historically.

---

## 🚀 Getting Started

### Prerequisites

* Python 3.7+
* pandas
* numpy
* matplotlib
* scikit-learn
* scipy

```bash
pip install pandas numpy matplotlib scikit-learn scipy
```

### Running the Analysis

1. Clone the repository:

   ```bash
   ```

git clone [https://github.com/yourusername/US-Marriage-Divorce-Analysis.git](https://github.com/yourusername/US-Marriage-Divorce-Analysis.git)
cd US-Marriage-Divorce-Analysis

````
2. Launch Jupyter Notebook:
   ```bash
jupyter notebook
````

3. Open **`CDC_Marriage_Divorce_Analysis.ipynb`** and run all cells.

---

## 📝 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

* Data provided by the CDC/NCHS National Vital Statistics System.
* Inspired by coursework at Birkbeck, University of London and community STEM initiatives.

