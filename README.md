# 🏃 Fitbit Health Data Analysis
**End-to-end analytics pipeline: Python → Power BI**
 
![Dashboard Preview](images/page1_activity_kpis.png)
 
## 📋 Project Overview
Phân tích dữ liệu sức khỏe từ 33 người dùng Fitbit trong 30 ngày
(Fitabase dataset, Apr–May 2016) nhằm xây dựng chiến lược retention
cho công ty công nghệ sức khỏe.
 
**Pipeline:** Data Merging → Clean Data → EDA → RFM Segmentation → Churn Prediction
 
---
 
## 🎯 Key Findings
 
| Metric | Value | Insight |
|--------|-------|---------|
| Avg Daily Steps | 7,638 | 76% of 10K WHO goal |
| Churn Rate | 15.15% | 5 users inactive 7+ days |
| Model AUC | 0.87 | Random Forest |
| Top Predictor | active_ratio (21%) | Consistency > Intensity |
| Safe Zone | RFM Score > 10 | Zero churn threshold |
 
---
 
## 📊 Dashboard Pages
 
### Page 1 — Activity KPIs
![Page 1](images/page1_activity_kpis.png)
- Activity intensity breakdown: 81.29% sedentary
- Sleep efficiency vs heart rate (r = −0.19)
- Hourly metabolic trend: dual peaks at 11h & 17h
- Health risk matrix: BMI vs METs
 
### Page 2 — RFM Segmentation
![Page 2](images/page2_segmentation.png)
- 5 segments: Champions (30.3%), Loyal (39.39%), Needs Attention (24.24%), At Risk (3.03%), Low Engagement (3.03%)
- RFM Score >10 = zero-churn threshold
- 69.7% high-value users (RFM ≥ 9)
 
### Page 3 — Churn Prediction
![Page 3](images/page3_churn.png)
- Random Forest model: AUC = 0.87
- active_ratio #1 predictor (21% importance)
- Users with active_ratio >80% = near-zero churn risk
- 4 high-risk users identified for immediate intervention
 
---
 
## 🛠 Tech Stack
 
| Tool | Usage |
|------|-------|
| Python 3.x | Data pipeline, ML model |
| pandas, numpy | Data processing |
| scikit-learn | Random Forest, AUC |
| matplotlib, seaborn | EDA visualization |
| Power BI Desktop | Interactive dashboard |
 
---
 
## 📁 Project Structure
 
```
fitbit-health-analysis/
├── README.md
├── data/output/          # Processed datasets
├── notebooks/            # Python analysis pipeline
├── dashboard/            # Power BI file (.pbix)
└── images/               # Dashboard screenshots
```
 
---
 
## 🚀 How to Run
 
### Python Pipeline
```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
python notebooks/fitbit_analysis_pipeline.py
```
 
### Power BI Dashboard
1. Download `dashboard/Fitbit_Analysis.pbix`
2. Open with Power BI Desktop
3. Update data source path in Transform Data
 
---
 
## 📈 Business Recommendations
 
1. **Champions (30%):** VIP streak badges, community leaderboard
2. **Loyal Users (39%):** Weekly progressive goals, gentle nudges
3. **At Risk (3%):** Re-engage within 48–72h of dropout
4. **Needs Attention (24%):** 3-day mini challenges to rebuild habit
5. **Retention KPI:** Maintain cohort active_ratio ≥ 80%
 
---
 
## 📝 Data Source
[Fitabase Fitbit Dataset](https://www.kaggle.com/datasets/arashnic/fitbit)
- 33 users, 30-day window (Apr 12 – May 12, 2016)
- 18 CSV files merged into master dataset
 
---
 
*Built by Anh Tran 
