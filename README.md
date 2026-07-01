# Secure Public Health Telemetry & Capacity Pipeline

An end-to-end, privacy-first data engineering and predictive analytics pipeline that ingests live environmental telemetry, applies a cryptographic pseudonymization firewall to protect patient privacy, and streams data into a secure cloud data warehouse to forecast hospital operational load.

## 📊 Live Production Dashboard
you can explore the interactive analytics built from this pipeline here:
[![View Tableau Dashboard](https://img.shields.io/badge/Tableau-Interactive%20Dashboard-blue?style=for-the-badge&logo=tableau&logoColor=white)](https://public.tableau.com/views/ClinicalOperationsEnvironmentalDemandForecast/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 🚀 Project Overview
This project demonstrates a production-grade data architecture focused on **Data Governance and Predictive Modeling**. In healthcare and public health sectors, handling patient data requires strict adherence to compliance frameworks (such as POPIA and HIPAA). This pipeline ensures that no direct Patient Identifiers (PII) ever reach the cloud analytics tier unencrypted, while maintaining the complete analytical integrity of the dataset for machine learning.

* **Project Phase 1:** API Telemetry Ingestion (Extracting real-world $PM_{2.5}$ and $O_3$ coordinates).
* **Project Phase 2:** Cryptographic Pseudonymization Layer (SHA-256 local firewall).
* **Project Phase 3:** Secure Cloud Warehousing (Supabase relational storage with enforced Row-Level Security).
* **Project Phase 4:** Predictive Capacity Modeling (Random Forest Regressor achieving an 86.25% $R^2$ score).
* **Project Phase 5:** Executive Reporting (Interactive Tableau Public Dashboard).

## 🛠️ Tech Stack & Architecture
* **Language:** Python 3 (Pandas, NumPy, Scikit-Learn)
* **Cloud Database:** Supabase (PostgreSQL Cloud Backend)
* **Security Layer:** SHA-256 Hashing + PostgreSQL Row-Level Security (RLS) Policies
* **BI Visualization:** Tableau Public

## 📊 Key Analytical Insights
* **Model Performance:** The integrated Random Forest Regressor achieved an **86.25% predictive accuracy ($R^2$ score)** during evaluation, successfully capturing the variance in daily ER admissions based purely on environmental pollution patterns.
* **Root Cause Verification:** Regression analysis confirms a distinct linear correlation between elevated particulate matter ($PM_{2.5}$) thresholds and sudden operational hospital capacity surges.

## 🔒 Security & Compliance Posture
1. **Zero-Trust Ingestion:** Patient names and ages are deterministically transformed using SHA-256 before leaving the local memory environment, ensuring full anonymization.
2. **Least Privilege Infrastructure:** The Supabase cloud data warehouse explicitly enforces Row-Level Security (RLS) policies, allowing authenticated `service_role` tokens strictly controlled access to prevent open public web exploitation.

## 📈 Dashboard Layout
The final dataset feeds a production-ready operational dashboard featuring:
* **The Operational Surge Forecast:** A dual-axis timeline tracking actual vs. predicted daily admission volumes.
* **Environmental Risk Thresholds:** A scatter plot with an active regression line mapping pollution severity to emergency admissions.
