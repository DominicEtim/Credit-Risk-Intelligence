# Credit Risk Intelligence for Nigerian SME Lending

## 📌 Project Overview
This project provides a comprehensive credit risk intelligence framework for Nigerian SME lending portfolios. Using data extracted from a Power BI dashboard, we analyze key performance indicators (KPIs), identify risk concentrations, and propose actionable strategies to mitigate expected losses of over ₦1.04 Trillion.

Objective: 
To transform raw lending data into actionable business intelligence that helps financial institutions optimize pricing, reduce default rates, and improve portfolio health.


## 🧠 Approach & Methodology

### 1. Data Extraction & Transformation (SQL)
- Source: Simulated lending data (2021–2025) from a Nigerian SME lending platform.
- Tables Created:
  - `loan_disbursements` – monthly disbursement amounts.
  - `loan_defaults` – monthly default rates.
  - `portfolio_risk` – risk category distribution (Critical, High, Medium, Low).
  - `sector_performance` – expected loss and revenue by sector.
  - `lender_performance` – expected loss by lending institution.
  - `processing_times` – average processing days per month.
- SQL Logic: Aggregations, window functions for trends, and CTEs for loss rate calculations.

### 2. Data Analysis (Python)
- Libraries Used: `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`
- Key Steps:
  - Clean and merge datasets.
  - Calculate Net Expected Loss Rate = Total Expected Loss / Total Portfolio.
  - Compute Risk-Adjusted Revenue by sector.
  - Identify correlation between processing days and default rates.
  - Segment lenders by performance (above/below average loss rate).

### 3. Visualization & Reporting (Power BI)
- Built an executive dashboard (as shown in the PDF) with:
  - Monthly disbursement & default trends.
  - Portfolio health gauge.
  - Sectoral risk & revenue heatmaps.
  - Lender-wise loss contribution.

### 4. Insight Generation
- Key Finding 1: Total Expected Loss (₦1.04T) exceeds Total Interest Income (₦10.5B) by 100x → severe mispricing.
- Key Finding 2: Manufacturing and Agriculture sectors have the highest loss-to-revenue ratios.
- Key Finding 3: Processing days have remained stagnant (~18.5 days) with no improvement over 5 years.
- Key Finding 4: Portfolio Health Gauge at 70/100 indicates declining credit quality.


## 🔧 How to Run the Code

### Prerequisites
- Python 3.8+
- PostgreSQL / MySQL / SQLite (or any SQL-compatible database)
- Power BI Desktop (optional, for dashboard rendering)

### 1. Clone the Repository
``bash
git clone https://github.com/yourusername/credit-risk-intelligence.git
cd credit-risk-intelligence

## 2. Set Up the Database (SQL)
Run the SQL script to create tables and insert sample data:

psql -U postgres -d Nigerian_Banks_Loan_Data -f sql/create_tables.sql
psql -U postgres -d Nigerian_Banks_Loan_Data -f sql/insert_data.sql
Or use the provided SQLite file: sme_lending.db

## 3. Install Python Dependencies
pip install -r requirements.txt
4. Run Python Analysis Scripts
a. Data Processing & Feature Engineering
python src/data_processing.py

## This script:

Loads data from SQL/database.
Calculates loss rates, risk scores, and sectoral KPIs.
Outputs processed CSV files to data/processed/.

b. Generate Visualizations
python src/visualize.py

## Produces:
Trend charts (disbursement, default, processing days).
Sectoral risk heatmap.
Lender performance bar chart.
Portfolio health gauge (matplotlib version).

## c. Generate Executive Report
python src/generate_report.py
Outputs a Markdown/PDF summary report with key insights and recommendations.

## 5. Power BI Dashboard 
- Open dashboard/Nigerian_Banks_Loan_Data.pbix in Power BI Desktop.

- Update data source connection to point to your database.

- Refresh to see updated visuals.

📊 Key Findings Summary
Metric	                   Value	                               Implication
Total Active Loans	       2 Million	                           Strong market penetration
Total Portfolio	           ₦4.03 Trillion	                       Significant capital deployed
Total Expected Loss	       ₦1.04 Trillion	                       Critical – 26% loss rate
Total Interest Income 	   ₦10.5 Billion	                       Grossly insufficient to cover losses
Portfolio Health Gauge     70/100	                               Declining quality; needs intervention
Top Risk Sector	           Retail Trade (₦300bn loss)	           Volume-driven, requires stricter caps
Worst Risk-Adjusted Sector Manufacturing & Agriculture	         High loss relative to revenue
Processing Days	           ~18.5 days (flat)	                   No efficiency gains in 5 years


## 🧪 Testing & Validation
Run unit tests to ensure calculations are correct:

pytest tests/
Tests cover:
- Loss rate formulas.
- Sectoral risk ratios.
- SQL aggregation correctness.


## 🚀 Next Steps & Customization
### To adapt to your own data:
- Replace sql/insert_data.sql with your actual data.
- Update column mappings in src/data_processing.py.
- Modify the Power BI data source to point to your database.
### To extend the model:
- Add machine learning (e.g., XGBoost) for default prediction.
- Integrate external macroeconomic indicators (inflation, GDP).

## 🤝 Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

📬 Contact
For questions, consulting, or contract opportunities:

DOMINIC ETIM

📧 dommy.john.etim@gmail.com



🔗 LinkedIn Profile: https://www.linkedin.com/in/dominic-etim-hrmp-aichrm-hsep-aicsp-b9a300128/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BYs5ZwQWIRBqmggaau%2Bzx3Q%3D%3D
