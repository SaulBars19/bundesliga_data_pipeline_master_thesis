# Bundesliga Tactical Formations: Data Pipeline & Risk–Return Analysis  
### Master’s Thesis — University of Lucerne  
**Author:** José Saúl Barrientos Rivera  
**Supervisor:** Prof. Dr. Thorsten Hens  
**Program:** Master of Arts in Economics & Management (Specialization in Data Science)  
**Period:** 2015/16 – 2024/25 Bundesliga Seasons

---

## Project Overview

This repository contains the full data pipeline developed for my Master’s Thesis:  
**“An Evolutionary Portfolio Theory Approach to Football Strategy:  
An Empirical Analysis of Bundesliga Tactical Formations (2015–2025).”**

The objective of the thesis is to treat football formations as **competing strategies** in an evolutionary environment, analysing their consistency, volatility, and payoff structure—analogous to risk–return trade-offs in financial portfolios.

The pipeline includes:

- Web scraping of tactical formations (Sportschau)
- Integration with market values (Transfermarkt)
- Cleaning, correction, and harmonization of team naming conventions
- Construction of match-level formation comparisons
- Identification of “surprise” matches using a market-value–based dominance structure
- Computation of Aggregate Score, Variance, and Standard Deviation
- Creation of payoff matrices (W–D–L, Aggregate Score, Variance–Std. Dev.)
- Visualization of formation-level risk–return profiles

All code and data transformations are fully reproducible.

---

## Repository Structure
```
bundesliga_data_pipeline_master_thesis/
│
├── README.md
│
├── notebooks/
│ └── bundesliga_data_scraping_pipeline.ipynb
│
├── data_raw/
│ ├── formations.html
│ └── transfermarkt_debug.html
│
├── data_processed/
│ ├── bundesliga_matches_all_seasons.csv
│ ├── bundesliga_formation_effectiveness_all_seasons.csv
│ ├── bundesliga_2024_2025_from_match_7.csv
│ ├── bundesliga_2024_2025_clean.csv
│ ├── bundesliga_matches_merged.csv
│ ├── bundesliga_formation_effectiveness_merged.csv
│ ├── bundesliga_formation_effectiveness_vertical.csv
│ ├── bundesliga_formation_effectiveness_scores.csv
│ ├── market_values_total_all_seasons.csv
│ ├── market_values_merged.csv
│ ├── bundesliga_matches_with_market_values.csv
│ ├── names_per_season.csv
│ ├── market_values_final.csv
│ ├── bundesliga_values_complete.csv
│ ├── bundesliga_surprises.csv
│ ├── bundesliga_effectiveness_surprises.csv
│ ├── bundesliga_effectiveness_surprises_vertical.csv
│ ├── bundesliga_var_sd_surprises.csv
│ ├── bundesliga_var_sd_all_matches.csv
│ ├── bundesliga_var_sd_all_matches_matrix.csv
│ ├── bundesliga_var_sd_surprises_matrix.csv
│ ├── 1.1_wins_draws_losses_all.csv
│ ├── 1.2_variance_std_dev_all.csv
│ ├── 1.3_aggregate_score_all.csv
│ ├── 1.4_average_score_all.csv
│ ├── 2.1_wins_draws_losses_surprises.csv
│ ├── 2.2_variance_std_dev_surprises.csv
│ ├── 2.3_aggregate_score_surprises.csv
│ └── 2.4_average_score_surprises.csv
│
├── excel_outputs/
│ ├── bundesliga_surprises.xlsx
│ ├── bundesliga_effectiveness_surprises.xlsx
│ ├── bundesliga_effectiveness_surprises_vertical.xlsx
│ ├── bundesliga_var_sd_surprises.xlsx
│ ├── bundesliga_var_df_all_matches.xlsx
│ ├── 1.1_wins_draws_losses_all.xlsx
│ ├── 1.2_variance_std_dev_all.xlsx
│ ├── 1.3_aggregate_score_all.xlsx
│ ├── 1.4_average_score_all.xlsx
│ ├── 2.1_wins_draws_losses_surprises.xlsx
│ ├── 2.2_variance_std_dev_surprises.xlsx
│ ├── 2.3_aggregate_score_surprises.xlsx
│ └── 2.4_average_score_surprises.xlsx
│
├── figures/
│ ├── formation_scores_table.png
│ ├── fig_risk_return_all_matches.png
│ ├── fig_risk_return_surprise_matches.png
│ ├── fig_frequency_all_matches.png
│ ├── fig_frequency_surprise_matches.png
│ ├── fig_dominance_all_matches.png
│ ├── fig_dominance_surprise_matches.png
│ ├── fig_variance_std_all.png
│ └── fig_variance_std_surprise.png
│
└── requirements.txt
```

---

## Main Notebook

### **`bundesliga_data_scraping_pipeline.ipynb`**
This is the core of the project.  
It contains:

1. **Web Scraping**  
   - Tactical formations for all Bundesliga matches (Sportschau)  
   - Raw HTML storage for reproducibility  

2. **Data Cleaning & Integration**  
   - Team name harmonization  
   - Season-by-season lineup extraction  
   - Transfermarkt market value integration  

3. **Surprise Match Identification**  
   Based on market-value dominance zones (group_1, group_2, group_3)

4. **Formation Performance Metrics**  
   - Aggregate Score  
   - Average Score  
   - Variance  
   - Standard Deviation  
   - Data Quality Classification (High / Medium / Low)

5. **Matrix Generation**  
   - Wins–Draws–Losses matrices  
   - Variance–Std Dev matrices  
   - Aggregate Score matrices  
   - Average Score matrices  
   For:
     - All matches  
     - Surprise matches only  

6. **Risk–Return Visualization**  
   Formation-level scatter plots analogous to portfolio analysis.

---

## Key Outputs

### **Payoff Matrices**
- `1.x_*.csv` → All matches  
- `2.x_*.csv` → Surprise matches  

### **Visual Figures**
- Formation Risk–Return Profile (All Matches)
- Formation Risk–Return Profile (Surprises)
- Dominance Heatmaps
- Variance–Std Dev Heatmaps
- Matchup Frequency Charts

### **Processed Datasets**
Used for all empirical analysis in the thesis.

---

## Reproducibility

1. Clone the repository:
```bash
git clone https://github.com/<your-username>/bundesliga_data_pipeline_master_thesis.git
```
2. Install dependencies:
```
pip install -r requirements.txt
```
3. Run the main notebook:
```
jupyter notebook notebooks/bundesliga_data_scraping_pipeline.ipynb
```
---

## How to Cite This Repository (Harvard Style)
If you use this code or dataset, please cite the following notebook:
Barrientos Rivera, J.S. (2025) *bundesliga_data_pipeline_master_thesis.ipynb*.  
Jupyter Notebook, GitHub Repository. Available at: https://github.com/SaulBars19/bundesliga_data_pipeline_master_thesis (Accessed: 11.12.2025).


## License
This repository is for academic and non-commercial research use.

## Contact
For questions regarding the methodology or the dataset:
José Saúl Barrientos Rivera
University of Lucerne
Email: jose.barrientos@stud.unilu.ch
