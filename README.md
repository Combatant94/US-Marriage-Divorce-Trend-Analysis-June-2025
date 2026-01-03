# US Marriage & Divorce Trends Analysis (CDC Data, 1990–2023)

<img width="948" height="520" alt="Screenshot 2026-01-02 at 11 32 55" src="https://github.com/user-attachments/assets/1b357691-ed2f-4306-908a-d5b5cd814af2" />

## Project Overview
I built this project to explore long-term trends in US marriage and divorce rates using official CDC data from 1990 to 2023. The goal was to go beyond simple charts – I wanted to uncover patterns, test relationships statistically, and build an interactive dashboard that makes the data easy to explore.

The result shows clear national declines in both rates, interesting state variations (Nevada's outlier explained by destination weddings), and strong statistical links between marriage and divorce in most states.

## Key Findings
- **National Declines**: Marriage rates fell ~44% (from ~9.8 to 6.57 per 1,000 population); divorce rates dropped ~49% (from ~5 to 2.52 per 1,000).
- **State Outliers**: Nevada leads marriage rates at ~41 per 1,000 in 2023 – driven by out-of-state couples marrying in Las Vegas (Clark County issued 74,000+ licenses in 2022, ~4% of US total). Hawaii and Arkansas follow.
- **Correlations**: Positive relationship in most states – higher marriage rates tend to coincide with higher divorce rates (confirmed with significance testing).
- **PCA**: First principal component explains 97.8% of variance, showing the two rates move closely together nationally.
- **Z-Normalised Trends**: State-level variation around the national average highlights regional differences clearly.

## Why Nevada Stands Out (Important Context)
Nevada's sky-high marriage rate isn't a data error – it's largely due to **destination weddings**. Thousands of couples from California, Texas, and even abroad travel to Las Vegas for quick ceremonies. CDC counts marriages by "state of occurrence" (where the wedding happens), not resident state. With only ~3 million residents but massive visitor weddings, Nevada's rate per 1,000 population looks extreme compared to states where most marriages are local residents.

Sources: CDC reports, Clark County records.

## How I Built It
Step-by-step workflow focused on clean data and reliable insights.

### Data Source
- CDC National Vital Statistics System (public Excel files).
- Marriage: https://www.cdc.gov/nchs/data/dvs/marriage-divorce/state-marriage-rates-90-95-00-23.xlsx
- Divorce: https://www.cdc.gov/nchs/data/dvs/marriage-divorce/state-divorce-rates-90-95-00-23.xlsx
- Rates per 1,000 population, 50 states + DC.

### Data Cleaning
- Loaded with pandas, handled missing values (forward/backward fill or state averages).
- Standardised state names, converted to numeric, added year/% change columns.

### Statistical Analysis
- Descriptive stats and time-series trends.
- Pearson correlations with significance testing.
- PCA (sklearn) – first component 97.8% variance.
- Z-normalisation for state comparisons.

### Tools Used
- **Python**: pandas/numpy for cleaning, scipy for correlations, sklearn for PCA.
- **Visualisation**: Matplotlib for line charts, heatmaps, scree plots, bar charts, and maps.
- **Environment**: Jupyter Notebook for full reproducibility.

## Visuals & Dashboard
Here's the key output:

1. **Full Dashboard Overview**  
<img width="948" height="520" alt="Screenshot 2026-01-02 at 11 32 55" src="https://github.com/user-attachments/assets/1b357691-ed2f-4306-908a-d5b5cd814af2" />

2. **Marriage Rate Over Time (All States)**  
<img width="989" height="789" alt="image" src="https://github.com/user-attachments/assets/f611fdf9-0fbe-4011-ab18-fb9bf5ca170c" />


3. **State Average Marriage Rate Bar Chart**  
   <img width="988" height="489" alt="image" src="https://github.com/user-attachments/assets/c1320bbf-529e-4838-a573-7da5b103c8f9" />


4. **Divorce Rate Over Time**  
  <img width="990" height="789" alt="image" src="https://github.com/user-attachments/assets/b8ce065c-6fac-4728-a5ee-68721d1e8a40" />




5. **Divorce Rates by State Bar Chart**  
<img width="988" height="489" alt="image" src="https://github.com/user-attachments/assets/65c8e25d-072f-47e7-b695-d916cb2bdb87" />


6. **Correlation Heatmap**  
  <img width="518" height="418" alt="image" src="https://github.com/user-attachments/assets/d9edb86a-7460-4184-b5c9-af9ea5ebee23" />


7. **PCA Scree Plot**  
<img width="567" height="453" alt="image" src="https://github.com/user-attachments/assets/7139edd3-7a5c-49fe-9fa1-27106246e60a" />


## Run It Yourself
```bash
git clone https://github.com/Combatant94/us-marriage-divorce-analysis.git
cd us-marriage-divorce-analysis
pip install -r requirements.txt
jupyter notebook us_marriage_divorce_analysis.ipynb
