# US Marriage & Divorce Trends Analysis (CDC Data, 1990–2023)


<img width="948" height="520" alt="Screenshot 2026-01-02 at 11 32 55" src="https://github.com/user-attachments/assets/1b357691-ed2f-4306-908a-d5b5cd814af2" />



## Project Overview
I built this project to explore how marriage and divorce rates have evolved across the US over the past three decades, using official data from the Centers for Disease Control and Prevention (CDC). It's fascinating to see how these trends reflect bigger social changes—like shifting attitudes toward marriage or economic factors—and I wanted to dig in with some solid analysis. The result is an interactive dashboard that highlights national declines, state variations, and statistical relationships between the rates.

## Key Findings
- **National Trends**: Marriage rates have dropped about 44% since 1990 (from ~9.8 to 6.57 per 1,000 population), while divorce rates fell 49% (from ~5 to 2.52). Both show steady declines, with sharper drops post-2010.
- **State Variations**: Nevada stands out with the highest marriage rate (41 per 1,000 in 2023), likely due to quick weddings in Las Vegas. Other top states for marriage include Hawaii (20) and Arkansas (14). Divorce rates are more even, but Arkansas and Idaho top the list at ~10.
- **Correlations & PCA**: In most states, marriage and divorce rates move together (positive correlation). PCA reduced the data to key components, with the first one explaining 97.8% of variance—showing these trends are closely linked.
- **Main Takeaway**: Fewer people are getting married or divorced overall, but where marriages are high, divorces often follow. This could tie into cultural or economic shifts, but the data doesn't show a clear "opposite" pattern anywhere.

## How I Built It
I started with a clear goal: pull reliable CDC data, clean it up, run some stats to find patterns, and build a dashboard for easy exploration. The project took a few hours spread over a couple of days, focusing on accuracy and usability. Here's the step-by-step:

### Data Source
- Sourced from CDC National Vital Statistics System (publicly available Excels).  
- Marriage data: https://www.cdc.gov/nchs/data/dvs/marriage-divorce/state-marriage-rates-90-95-00-23.xlsx  
- Divorce data: https://www.cdc.gov/nchs/data/dvs/marriage-divorce/state-divorce-rates-90-95-00-23.xlsx  
- Rates are per 1,000 population, covering all 50 states + DC from 1990–2023 (some gaps filled with averages).

### Data Cleaning
- Loaded Excels into pandas DataFrames.  
- Handled missing values: Some states/years had gaps (e.g., pre-1995 data), so I used forward/backward fill or state averages where logical. Dropped incomplete rows if needed.  
- Converted rates to numeric, standardised state names, and added derived columns like year and rate changes.  
- Final dataset: ~1,200 rows (states x years), clean and ready for analysis.

### Statistical Analysis
- **Descriptive Stats**: Calculated averages, declines (e.g., % change since 1990), and correlations between marriage/divorce. Used scipy.stats for Pearson correlations with p-values to check significance.  
- **PCA (Dimensionality Reduction)**: Applied sklearn.decomposition.PCA to see underlying patterns. The first principal component captured 97.8% of variance, showing marriage and divorce rates are highly aligned.  
- **Outlier Detection**: Flagged states like Nevada with extreme values for deeper looks.  
- All code is in the Jupyter notebook – I kept it simple but rigorous, focusing on interpretable results.

### Tools & Methods
- **Python**: Core language for everything – pandas for data wrangling, numpy for calculations, scipy.stats for correlations/testing, sklearn for PCA.  
- **Visualisation**: Matplotlib for basic plots, Plotly for interactive dashboard (year slider, hover tooltips).  
- **Environment**: Jupyter Notebook for development – easy to iterate and document.  
- **Methods**: Started with EDA (exploratory data analysis) to spot trends, then stats for relationships, finally visuals for presentation. No advanced ML needed – kept it focused on insights.

## Screenshots & Visuals
Here's a walkthrough of the dashboard in images:

1. **Full Dashboard Overview**: Main view with metrics, line chart, and state comparisons.  
   ![Full Dashboard](images/dashboard_overview.png)

2. **National Trends Line Chart**: Shows declines over time – marriage (blue) always higher than divorce (black).  
  <img width="994" height="261" alt="Screenshot 2026-01-02 at 11 36 27" src="https://github.com/user-attachments/assets/d8472655-8443-48dd-92a0-8bd5a8ad17db" />


3. **State Maps**: Side-by-side for marriage (left) and divorce (right) in 2023 – darker colours mean higher rates.  
   ![State Maps](images/state_maps.png)

4. **Top States Bar Chart**: Dual bars (green marriage, red divorce) for outliers like Nevada.  
   ![Top States Bar](images/top_states_bar.png)

5. **Correlation Heatmap**: Shows positive links (green) in most states – with significance stars.  
   ![Correlation Heatmap](images/correlation_heatmap.png)

6. **PCA Scree Plot**: Explains variance – first component dominates.  
   ![PCA Scree Plot](images/pca_scree_plot.png)

## Run It Yourself
1. Clone the repo: `git clone https://github.com/Combatant94/us-marriage-divorce-analysis.git`  
2. Install requirements: `pip install -r requirements.txt` (pandas, matplotlib, scipy, sklearn, plotly)  
3. Open the notebook: `jupyter notebook us_marriage_divorce_analysis.ipynb`  
4. Explore – run cells to recreate visuals or tweak the analysis.

## What I Learned
This project sharpened my skills in handling time-series data and blending stats with visuals. If I did it again, I'd add more forecasting (e.g., ARIMA for 2024+ predictions). Feedback welcome – always looking to improve!

Mohd Nafees | January 2026 | nafees.mohd.datascientist25@gmail.com
