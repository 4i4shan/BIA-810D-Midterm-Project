# BIA-810: Healthcare Analytics Midterm Project
**Author: Ishaan Nakhare**

## 📜 Project Objective

This repository contains the solution for the BIA-810D Midterm Exam. The objective is to act as a member of a Commercial Analytics team for a pharmaceutical company, analyzing the Syntegra Medicare CCLF Claims dataset.

The analysis provides insights into the Cardio Vascular Metabolic (CVM) disease landscape [cite: 11] [cite_start]to inform the decision-making and strategy development of the CVM Sales & Marketing leadership team.

## 🗂️ Table of Contents

1.  [Data Sources](#-data-sources)
2.  [Methodology](#-methodology)
3.  [Key Business Questions & Findings](#-key-business-questions--findings)
4.  [Extra Credit Analysis](#-extra-credit-analysis)
5.  [Technical Requirements](#-technical-requirements)

## 💾 Data Sources

The analysis is based on the Syntegra Medicare CCLF Claims dataset. The following files were prepared and analyzed:

* `parta_claims_header.csv`
* `parta_claims_revenue_center_detail.csv`
* `parta_diagnosis_code.csv`
* `partb_dme.csv`
* `partb_physicians.csv`
* `beneficiary_demographics.csv`

## 🔬 Methodology

The project was executed in the following phases, as seen in the notebook:

1.  **Data Preparation:** All raw `.csv` files were loaded into Pandas DataFrames. Unnecessary columns were dropped, and data quality checks (e.g., uniqueness, null values) were performed.
2.  **Data Consolidation:** The disparate claims files (Part A, Part B, DME, etc.) were combined into a single master `medicare_df` to create a unified view for analysis.
3.  **Feature Engineering:** New analytical columns were created, including `claim_year` (from `claim_date`) and `patient_age` (calculated by subtracting `patient_birth_date` from the claim year).
4.  **Analysis & Visualization:** The consolidated data was grouped and aggregated to answer the three KBQs. [cite_start]Findings were visualized using stacked bar charts and tables, per the exam requirements.

## 📊 Key Business Questions & Findings

This analysis answers the three primary KBQs outlined in the exam instructions.

### KBQ 1: CVM Claim Trends

> **Finding:** The upward trend in Blood Test claims from 2016 to 2018 demonstrates a growing emphasis on preventive healthcare and early disease detection. This steady increase highlights a shift in both patient behavior and healthcare provider practices.

### KBQ 2: HCP Behavior & Segmentation

> **Finding:** Most HCPs (88%) submitted only one blood test claim, indicating broad but low-frequency engagement. A small group of high-volume providers (less than 5%) drive the majority of testing.
>
> **Recommendation:** This distribution suggests a tiered sales strategy:
> * **High-Volume HCPs (10+ claims):** Prioritize for in-person sales force visits to maintain and grow these key relationships.
> * **Low-Volume HCPs (1-4 claims):** Target efficiently via non-personal promotions (NPP) like emails and digital campaigns to maintain awareness cost-effectively.

### KBQ 3: Patient Age Demographics

> **Finding:** The 60-69 age group consistently represents the largest volume of claims. However, the 70-79 age group showed significant growth, increasing from 991 claims in 2016 to 1,546 in 2018. The 80+ segment also grew steadily.
>
> **Recommendation:** Marketing budgets should be positioned accordingly:
> * **Core (Ages 60-79):** Allocate the largest budget share (50-55%) to retention and chronic-care programs.
> * **Growth (Ages 80+):** Dedicate 20-25% to accessibility and convenience-focused marketing (e.g., telehealth, home-collection).
> * **Emerging (Ages 18-59):** Invest 20-25% in digital-first awareness and preventive-care campaigns.

## ✨ Extra Credit Analysis

Per the exam's extra credit option, an additional analysis on HCP Loyalty and Retention was performed.

> **Finding:** The analysis showed a balanced dynamic of new vs. churned providers each year. However, the retention base is low (~8–10%), which highlights that most providers engage intermittently. This suggests a significant opportunity to improve loyalty and convert new or sporadic HCPs into long-term, high-volume partners.

## ⚙️ Technical Requirements

The notebook was written in Python 3 and relies on the following core libraries:

* `pandas`
* `numpy`
* `matplotlib`
