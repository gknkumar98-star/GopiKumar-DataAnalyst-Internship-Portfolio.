# Gopi Kumar — Data Analyst Internship Portfolio

**ApexPlanet Data Analytics Internship · End-to-End Sales Analytics Project**

From a raw 1,000-order sales spreadsheet to a cleaned dataset, SQL-driven EDA, customer segmentation, an interactive Power BI dashboard, and a statistically validated business recommendation — all on one dataset, across four connected projects.



---

## The One-Paragraph Story

ApexPlanet's sales data (1,000 orders, 947 customers, ₹139.4M revenue) had a hidden data-integrity bug, a clear category concentration in Electronics, and a striking customer split: **28% of customers generate 54% of revenue while ordering only once.** I cleaned the data, explored it with SQL and visualizations, segmented customers with K-Means, built a Power BI dashboard, and then proved with a Welch's t-test that the high-value segment's advantage is real (p ≈ 2.6 × 10⁻¹²⁹, Cohen's d = 3.43) — which justifies a targeted repeat-purchase strategy.

---

## Project Map

| # | Project | What I did | Repository |
|---|---------|-----------|------------|
| 1 | **Data Immersion & Wrangling** | Data dictionary, quality audit, cleaning script, analysis-ready dataset | [Task-1 repo](https://github.com/gknkumar98-star/ApexPanet_Data_Immerssion_and_Wrangling.git) |
| 2 | **Exploratory Data Analysis & BI** | Univariate/multivariate EDA, 7 SQL business queries, KPI dashboard mock-up | [Task-2 repo](https://github.com/gknkumar98-star/EDA_-_Business_Intelligence.git) |
| 3 | **Deep-Dive Analysis & Interactive Dashboard** | KPI definitions, K-Means customer segmentation, star-schema data model, Power BI dashboard | [Task-3 repo](https://github.com/gknkumar98-star/ApexPlanet_Sales_Dashboard.git) |
| 4 | **Data Storytelling & Statistical Validation** | Hypothesis test, data-story report, stakeholder presentation | [Task-4 repo](https://github.com/gknkumar98-star/Apexplanet_DataST-Stat_Valid.git) |

---

## Key Findings

| Stage | Finding |
|-------|---------|
| **Data quality** | 20 missing `Age` values, 13 missing `City` values, and one `Order_ID` (`ORD100050`) reused across **9 different orders** — all fixed before analysis |
| **EDA** | Electronics drives **₹50.8M (36.4%)** of revenue from ~35% of orders; revenue is right-skewed (a few big-ticket orders lift the average order value of ₹1,39,399) |
| **Segmentation** | K-Means (k = 3, silhouette = 0.44) → *High-Value / Big-Basket* (27.9% of customers, **53.9% of revenue**), *Repeat Customers* (5.5%), *Low-Value / One-Time* (66.6%) |
| **Validation** | Welch's t-test: High-Value orders are worth **₹2,08,715 more** on average (95% CI ₹1,98,171 – ₹2,19,260), t = 38.93, p ≈ 2.6 × 10⁻¹²⁹, Cohen's d = 3.43 |
| **Recommendation** | Convert one-time High-Value buyers into repeat customers, using the existing Repeat Customers as the model, and pair the push with Electronics |

---

## Dashboard

Built in **Power BI** on the star-schema data model (`Fact_Sales` + `Dim_Customer`, `Dim_Product`, `Dim_Date`).

- 4 KPI cards: Total Sales Amount, Average of Total Sales, Max of Total Sales, Total Quantity
- Gender slicer with cross-filtering across all visuals
- Sales by Age Group (donut), Total Sales by City (map), Total Sales by Month/Year (area)
- Total Sales by Category and Total Quantity by Product (bar charts)

📁 File: [`dashboard/Apex_Dashboard.pbix`](https://github.com/gknkumar98-star/ApexPlanet_Sales_Dashboard/blame/00be55707c3c8fa36de0965c5e5bc3e95cf2b43f/Apex_Dashboard.pbix)


---

## Final Presentation

A 7-slide stakeholder deck: dashboard walkthrough → customer segmentation → hypothesis test → recommendation.

📁 File: [`presentation/Final_Presentation.pptx`](https://github.com/gknkumar98-star/Apexplanet_DataST-Stat_Valid/blob/main/ApexPlanet_Final_Presentation_v2.pptx)

---

## Repository Structure

```
Gopi Kumar-DataAnalyst-Internship-Portfolio/
├── README.md
├── data/
│   ├── cleaned_dataset.csv
│   ├── data_dictionary.csv
│   └── PowerBI_Tableau_DataModel.xlsx
├── notebooks/
│   ├── 01_Data_Wrangling.ipynb
│   ├── 02_EDA_and_SQL.ipynb
│   ├── 03_Segmentation_Deep_Dive.ipynb
│   └── 04_Hypothesis_Testing.ipynb
├── scripts/
│   └── cleaning_script.py
├── dashboard/
│   ├── Apex_Dashboard.pbix
│   └── dashboard-screenshot.png
├── presentation/
│   └── Final_Presentation.pptx
└── reports/
    ├── Deep_Dive_Report.docx
    └── Data_Story_Report.docx
```

---

## Technical Skills Demonstrated

| Area | Tools & Techniques |
|------|--------------------|
| **Data wrangling** | Python, pandas, NumPy — missing-value handling, duplicate-key repair, date standardization, feature engineering |
| **SQL** | Aggregation, filtering, grouping, multi-dimension queries (SQLite) |
| **Visualization** | Matplotlib, Seaborn — histograms, boxplots, heatmaps, pair plots, scatter plots |
| **Machine learning** | scikit-learn — StandardScaler, K-Means, elbow method, silhouette scoring |
| **Statistics** | SciPy — Levene's test, Welch's t-test, confidence intervals, effect size (Cohen's d) |
| **BI & dashboards** | Power BI — KPI cards, slicers, cross-filtering, star-schema modelling |
| **Communication** | Data storytelling, stakeholder decks, written reports |
| **Workflow** | Jupyter, Git/GitHub |

---

## Key Learnings

1. **Data quality comes before everything.** The reused `Order_ID` looked harmless but would have silently corrupted every customer- and order-level result downstream.
2. **Let the data choose the method.** Only 5.5% of customers ordered more than once and there was no session-level data, so cohort and funnel analysis weren't valid — segmentation was the right deep-dive.
3. **A striking chart isn't proof.** The 28%/54% split looked convincing, but the hypothesis test (and effect size, not just the p-value) is what made it defensible.
4. **Insight needs a call to action.** Every analysis stage ended in a decision a business could act on, not just a chart.

---

## Reproducing the Analysis

```bash
git clone https://github.com/<your-username>/[YourName]-DataAnalyst-Internship-Portfolio.git
cd [YourName]-DataAnalyst-Internship-Portfolio
pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter openpyxl
jupyter notebook notebooks/
```

Run the notebooks in order (01 → 04). Open `dashboard/Apex_Dashboard.pbix` in Power BI Desktop.

---


*Completed as part of the ApexPlanet Data Analytics Internship.*
