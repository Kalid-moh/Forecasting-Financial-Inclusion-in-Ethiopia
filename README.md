# Forecasting-Financial-Inclusion-in-Ethiopia

This project analyzes and forecasts financial inclusion in Ethiopia using a unified, event-driven dataset. It supports evidence-based policy monitoring for Ethiopia’s National Digital Payments Strategy (NDPS) and related digital finance reforms.

The analysis focuses on two core dimensions of financial inclusion:

Access (e.g., account ownership)

Usage (e.g., digital payments)

The project integrates survey data, infrastructure indicators, policy events, and operator metrics into a single analytical framework.

🎯 Project Objectives

Understand trends in financial inclusion in Ethiopia (2011–2024)

Enrich the dataset with recent (2025) observations and key policy events

Analyze drivers of inclusion across infrastructure, regulation, and market entry

Model relationships between events and indicators using an impact-link schema

Forecast financial inclusion outcomes for 2025–2027

🗂️ Repository Structure
.
├── data/
│ ├── ethiopia_fi_unified_data.csv
│ ├── impact_links.csv
│ └── reference_codes.csv
│
├── notebooks/
│ ├── task_1_data_exploration.ipynb
│ └── task_2_eda.ipynb
│
├── data_enrichment_log.md
├── README.md
└── requirements.txt

🧱 Unified Data Schema

The dataset is organized around three core record types:

1. Observations

Measured indicators collected from surveys, operators, and official reports
(e.g., account ownership rate, mobile money penetration, 4G coverage).

Key fields:

pillar (Access, Usage, Enablers)

indicator_code

value_numeric

observation_date

source_name, source_url

confidence

2. Events

Discrete milestones that may influence financial inclusion:

Policy launches (e.g., NDPS)

Product launches (e.g., Telebirr, M-Pesa)

Infrastructure expansions (e.g., 4G rollout)

Events do not contain numeric values but are linked to indicators via impact modeling.

3. Targets

Official policy goals used for benchmarking progress against strategy objectives.

4. Impact Links

The impact_links table connects events to indicators using:

parent_id

related_indicator

impact_direction

impact_magnitude

lag_months

evidence_basis

This structure enables modeling how regulatory, infrastructure, and market events affect inclusion outcomes over time.

🧪 Task 1: Data Exploration & Enrichment

Completed:

Explored schema and record distributions

Identified temporal coverage and indicator gaps

Reviewed existing impact_links

Enriched dataset with high-confidence 2025 records:

Telebirr registered users

M-Pesa active users

4G coverage expansion

NDPS 2026–2030 launch event

All additions are documented in:

data_enrichment_log.md

Each enriched record includes:

source_url

original_text

confidence

collected_by

collection_date

notes

📈 Task 2: Exploratory Data Analysis (EDA)

Analyses performed:

Dataset summary by pillar, record_type, and source_type

Temporal coverage visualization

Confidence distribution and data quality assessment

Account ownership trend (2011–2024)

Growth rate analysis between survey waves

Mobile money adoption trends

Infrastructure vs. inclusion correlations

Event overlays on indicator trajectories

Correlation analysis across indicators

Key questions addressed:

Why did account ownership slow after 2021?

What explains the gap between registered and active users?

Which factors appear most associated with Access and Usage?

What data gaps limit interpretation?

🔍 Key Insights

Account ownership growth slowed significantly after 2021 despite massive mobile money registration.

A large “registered vs. active” gap explains much of this stagnation.

Infrastructure (especially mobile and 4G coverage) is strongly correlated with digital finance adoption.

Major policy and product launches align with shifts in trend direction.

Sparse survey frequency and lack of disaggregated data (gender, rural/urban) limit causal inference.

🧭 Roadmap

Next phases:

Event impact modeling using lagged effects

Scenario-based forecasting (2025–2027)

Interactive dashboard for policymakers

⚙️ Installation & Usage

Clone the repository:

git clone https://github.com/Kalid-moh/Forecasting-Financial-Inclusion-in-Ethiopia.git
cd Forecasting-Financial-Inclusion-in-Ethiopia

Install dependencies:

pip install -r requirements.txt

Run notebooks:

jupyter notebook

Open:

task_1_data_exploration.ipynb

task_2_eda.ipynb

📚 Data Sources

World Bank Global Findex

National Bank of Ethiopia (NBE)

Ethio Telecom

M-Pesa Ethiopia

Prime Minister’s Office

Official policy publications (NDPS, Fayda ID)
