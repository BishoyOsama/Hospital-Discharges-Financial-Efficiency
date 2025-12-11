# Data Analyst Project: Hospital Discharges & Financial Efficiency Analysis

Welcome to the **Hospital Discharges & Financial Efficiency** repository! This project explores data-driven solutions to key business challenges in [balancing patient care quality with operational efficiency]. Follow along as we uncover insights and deliver actionable recommendations.

---

## Table of Contents

- [Background & Business Problem](#background--business-problem)
- [Project Objectives](#project-objectives)
- [Data Collection & Understanding](#data-collection--understanding)
- [Data Cleaning & Preprocessing & Modeling](#data-cleaning--preprocessing--modeling)
- [Main Insights](#main-insights)
- [Solutions & Recommendations](#solutions--recommendations)
- [Summary](#summary)
- [How to Reproduce](#how-to-reproduce)

---

## Background & Business Problem

Healthcare organizations face persistent challenges in balancing patient care quality with operational efficiency and financial sustainability. Wide variations in hospital length of stay (LOS) and cost per discharge — influenced by patient severity, regional practice differences, and hospital-specific processes — lead to inconsistent resource utilization, unpredictable costs, and potential patient care disparities. A clear understanding of these drivers, as visualized in the report, is essential for data-driven decision making, identifying improvement opportunities, and ensuring optimal healthcare delivery.



## Project Objectives

- Reduce unwarranted variation in patient length of stay (LOS) and cost per discharge across hospitals.
- Identify and analyze the primary drivers influencing LOS and healthcare cost, including patient severity, mortality risk, and regional factors.
- Implement risk-adjusted benchmarking for hospital performance to ensure fair and accurate comparisons.
- Develop targeted process improvement interventions for outlier hospitals to improve efficiency and lower costs without compromising quality.
- Promote best practices and data-driven protocols system-wide to achieve consistent, high-quality, and cost-effective healthcare delivery.

  
## Data Collection & Understanding

| file | type |
| ------- | ----------- |
| hospital_inpatient_discharges_totalhipreplacement | .csv |


hospital_inpatient_discharges_totalhipreplacement Table Columns

| columnName | Description |
| -----------| ------------|
| health_service_area	| The geographic region (usually defined by state health department or payer guidelines) where the hospital is located or where services are provided.|
| hospital_county	 | The specific county in which the hospital operates. |
| operating_certificate_number	| The unique identification number assigned to the hospital by a regulatory body to certify its authorization to operate. |
| facility_id	| A unique code identifying the hospital or healthcare facility within the dataset.|
| facility_name	| The name of the hospital or healthcare facility. |
| age_group	 | Categorical grouping of patient ages (e.g., 0-17, 18-64, 65+), used for population segmentation. |
| zip_code_3_digits	| The first three digits/chars of the patient’s residential zip code, used to approximate location while maintaining privacy. |
| gender	| Patient’s identified gender (such as Male, Female). |
| race	| Patient’s identified race, following reporting standards (e.g., White, Black or African American, Asian, etc.). |
| ethnicity	| Patient’s identified ethnicity, such as Hispanic/Latino or Not Hispanic/Latino. |
| length_of_stay	| Number of days the patient was admitted to the hospital from admission to discharge. |
| type_of_admission	 | Classification of how the patient was admitted (e.g., Emergency, Elective, Urgent). |
| patient_disposition	| The status or destination of the patient at discharge (e.g., Discharged to home, Skilled nursing facility, Deceased). |
| discharge_year	| Year in which the patient was discharged from the hospital. |
| ccs_diagnosis_code	| The Clinical Classification Software (CCS) diagnosis code categorizing the primary diagnosis (used for grouping ICD codes). |
| ccs_diagnosis_description	| The description of the CCS diagnosis code (diagnostic group name). | 
| ccs_procedure_code	| The CCS code categorizing the major procedure performed during admission. |
| ccs_procedure_description	| The description of the CCS procedure code (procedure group name). |
| apr_drg_code	| All Patient Refined Diagnosis Related Group code: categorizes admission into homogeneous groups for payment and benchmarking. |
| apr_drg_description	 | Text description of the APR DRG code (clinical episode). |
| apr_mdc_code	| Major Diagnostic Category code as defined by APR DRG (high-level clinical classification). |
| apr_mdc_description	| Description of the major diagnostic category. |
| apr_severity_of_illness_code	| Numeric code identifying the severity of illness (e.g., Minor, Moderate, Major, Extreme). |
| apr_severity_of_illness_description	| Text description of the severity of illness for the admission. |
| apr_risk_of_mortality	 | Numeric or categorical value indicating the risk of mortality, as assessed by APR DRG grouper (Minor to Extreme). |
| apr_medical_surgical_description	| Identifies whether the admission was medical or surgical in nature. |
| attending_provider_license_number	 | License number of the physician primarily responsible for patient care during the hospital stay. |
| operating_provider_license_number	 | License number of the physician who performed the principal procedure (if applicable). |
| total_charges	 | The total amount billed by the hospital for the patient’s stay (gross charges before payment/adjustment). |
| total_costs  | The hospital’s estimated actual cost of providing care to the patient during the hospitalization |




## Data Cleaning & Preprocessing & Modeling 

Data Cleaning

- Removing duplicates and changing datatype of numeric columns to numbers and filter data to include data for ccs_procedure_description is "HIP REPLACEMENT,TOT/PRT"

Data Model:

- surgical_program table is a summarized table

<img width="493" height="673" alt="datamodel" src="https://github.com/user-attachments/assets/8fc76b73-8867-4d0e-ae77-f58998991aba" />


## Sample Report:


https://github.com/user-attachments/assets/39b0d2d6-1e12-4665-8fea-24bb5641c206




------------------------------------------------------------------------------------------------

## Main Insights

1. Significant Performance Variation

  - The report shows most hospitals maintain low average LOS and moderate costs, but a minority are extreme outliers in both. The top three hospitals have much higher average LOS and costs compared to peers, skewing system performance.

2. Patient Severity is a Core Driver

  - Cases labeled “Extreme” in severity or risk of mortality have high impact, raising LOS by 6–9 days on average, underscoring that case mix adjustment is critical before benchmarking hospitals against each other.

3. Geographical Disparities

  - Health service area strongly influences cost: several regions show lower average cost per discharge, suggesting that local healthcare delivery models, payer contracts, or efficiency efforts are making a difference.

4. Outlier Analysis Guides Improvement

  - The outliers identified in the dashboards (bottom and top 3 for LOS & cost) demonstrate where targeted action could have the greatest financial and operational impact.

5. Positive Cost/LOS Relationship — But Room for Exceptions

  - The scatterplot reveals most hospitals cluster at reasonable levels of LOS and cost, but some deliver similar LOS with notably higher costs, hinting at inefficiency or higher-input cases (e.g., advanced procedures, supply choices).

## Solutions & Recommendations

1. Expand Risk-Adjusted Benchmarking

  - Eliminate unfair comparisons. Adjust key figures (LOS, cost) for patient severity, diagnosis, and social determinants to reveal true performance gaps.

2. Targeted Outlier Engagement

  - Why: High-impact fixes yield quicker results.
  - Action: Focus process improvement and clinical resource teams on top outlier hospitals, working directly with administrators and clinicians to identify bottlenecks (e.g., discharge planning, case management, supply utilization).

3. Share and Scale Best Practices

  - Why: Some hospitals (e.g., Alice Hyde) demonstrate efficiency despite similar case mixes.
  - Action: Conduct peer learning sessions, operational audits, and protocol sharing to propagate successful care pathways and cost management strategies across the system.

4. Regional Approaches to Cost Control

  - Why: Health service areas showing consistently lower cost per discharge can reveal actionable local strategies.
  - Action: Analyze contracting, resource allocation, and staffing in these areas; consider piloting their practices elsewhere.

5. Deep Dive High-Cost Procedures

  - Why: Outlier costs may be tied to specific procedures, supplies, or implant choices.
  - Action: Launch supply chain and clinical reviews for the highest-cost discharge cases; negotiate vendor contracts and streamline protocol for expensive interventions.

6. Address Quality and Safety

  - Why: Lowering LOS without attention to quality could increase readmissions or reduce patient satisfaction.
  - Action: Integrate readmission rates, complications, and patient satisfaction into the dashboard. Make changes with continuous monitoring to balance efficiency and outcomes.

7. Invest in Predictive & Prescriptive Analytics

  - Why: Proactive identification of high-risk or potentially costly cases can prioritize clinical interventions.
  - Action: Build tools to flag admissions that may result in excessive LOS/cost at intake, activating early case management.

8. Foster a Culture of Continuous Improvement

  - Why: Sustained benefit comes from ongoing review and adaptation.
  - Action: Establish monthly performance governance, publishing risk-adjusted scorecards to foster accountability and maintain focus on key metrics.

--------------------------------------------------------------------------------------

## Summary

The project analyzes hospital length of stay and cost data to identify what drives performance variation across facilities. By benchmarking hospitals and adjusting for patient severity, we uncover key improvement opportunities and offer recommendations to optimize efficiency, reduce costs, and maintain high-quality patient care. The goal is to support better decision-making and sustainable hospital operations.

 -----------------------------------------------------------------------------------------------------------
## How to Reproduce

Step-by-step instructions for running the analysis:
1. [Download dataset](https://github.com/BishoyOsama/Hospital-Discharges-Financial-Efficiency/tree/master/dataset)
2. Open your bi tool
3. feel free to refer to data model to reproduce

