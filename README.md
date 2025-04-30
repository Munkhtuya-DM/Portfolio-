---
Healthcare Data Analysis Project Report
---

# Healthcare Data Analysis Project Report

## Executive Summary

This report details a personal data analysis project focused on real-world healthcare sample data. Using SQL Server as the backbone, I built a comprehensive database and developed a relational data model to transform raw data into actionable insights. Strategic views were created to enable a deeper understanding of the healthcare landscape, covering payers, diagnoses, physicians, patients, and transactions. The analysis spans December 2019 to July 2020 for Nova Clinic, with insights visualized through detailed dashboards.

---

## Project Overview

The project leverages healthcare sample data to uncover meaningful insights. I utilized SQL Server to construct a robust database, implementing a relational data model to ensure data integrity and accessibility. This foundation facilitated the transformation of raw data into strategic insights, with a focus on creating views that provide a comprehensive understanding of the healthcare ecosystem.

**Key Technologies Used:**
- SQL Server
- Relational Database Design
- Data Visualization Tools

---

## Database Schema

The database follows a star schema design, with a central fact table (`FactTable`) linked to multiple dimension tables. Below is the schema structure:

### Fact Table
- **FactTable**
  - Primary Key: `FactTablePK`
  - Foreign Keys: `dimPatientPK`, `dimPhysicianPK`, `dimDatePostPK`, `dimDateServicePK`, `dimCptCodePK`, `dimPayerPK`, `dimTransactionPK`, `dimLocationPK`
  - Attributes: `PATIENT_NUMBER`, `DIAGNOSIS_CODE`, `CptUnits`, `GrossCharge`, `Payment`, `Adjustment`, `AR`

### Dimension Tables
1. **dimTransaction**
   - Primary Key: `dimTransactionPK`
   - Attributes: `TRANSACTION_TYPE`, `TRANSACTION`, `ADJUSTMENT_REASON`

2. **dimLocation**
   - Primary Key: `dimLocationPK`
   - Attributes: `LOCATION_NAME`

3. **dimPhysician**
   - Primary Key: `dimPhysicianPK`
   - Attributes: `ProviderNPI`, `ProviderName`, `ProviderSpecialty`, `ProviderFTE`

4. **dimDiagnosisCode**
   - Primary Key: `dimDiagnosisCodePK`
   - Attributes: `DiagnosisCode`, `DiagnosisCodeDescription`

5. **dimPayer**
   - Primary Key: `dimPayerPK`
   - Attributes: `PAYER_NAME`

6. **dimDate**
   - Primary Key: `dimDatePostPK`
   - Attributes: `Date`, `Year`, `Month`, `MonthPeriod`, `MonthYear`, `Day`, `DayName`

---

## Data Insights and Dashboards

The project includes a series of dashboards providing insights into various aspects of healthcare operations at Nova Clinic, spanning December 2019 to July 2020.

### 1. Summary Dashboard
- **Key Metrics**:
  - Total Revenue: $1,472,267
  - Total Payments: $703,613
  - Total Adjustments: $716,683
  - Total Account Receivable: $51,971
  - Total Transactions: 955
  - Total Patients: 4,962
  - Total Visits: 84,219

- **Prevalent Diagnoses Across Age Groups**: Visualized using a stacked bar chart, comparing diagnoses (e.g., I10, Z00, Z123) across age groups (Adult, Child, Infant, Senior Citizen).
- **Physicians by Specialty**: Bar chart showing Internal Medicine (224), Family Medicine (120), and other specialties.
- **Financial Performance Over Time**: Line chart tracking Total Revenue, Adjustments, Payments, and AR from January to July 2020.
- **Popular Payers by City**: Stacked bar chart showing payer distribution across cities like Emerson and Longview.

### 2. Payers Dashboard
- **Key Metrics**:
  - Total Payers: 4
  - Total Revenue: $1,472,267
  - Total Payments: $703,613
  - Total Adjustments: $716,683
  - Total Account Receivable: $51,971

- **Patient’s Preferred Payer by City**: Stacked bar chart showing payer distribution (e.g., Emerson: 51% Commercial).
- **Payer-specific Patient Trends**: Line chart tracking patient trends by payer type.
- **Payer Selection Trends Across Age Groups**: Bar chart showing payer preferences across age groups.
- **Overview**:
  - Commercial: $749,130 Gross Charges, $408,758 Payment, $30,261 AR
  - Medicare: $649,889 Gross Charges, $276,703 Payment, $13,510 AR

### 3. Diagnosis Dashboard
- **Prevalent Diagnoses by Patient Gender**: Bar chart comparing diagnoses like Essential Hypertension (145 Female, 122 Male).
- **Diagnosis Trends Over Time**: Line chart showing trends for diagnoses from January to July 2020.
- **Diagnosis Correlation with Total Patients and Gross Revenue**: Scatter plot showing relationships between patients and revenue.
- **Severity of Illness by Cities**: Stacked bar chart showing diagnosis distribution across cities.

### 4. Physicians Dashboard
- **Key Metrics**:
  - Total Physicians: 931
  - Median Weekly Work Hours: 36.0
  - Total Locations: 11

- **Distribution of Physicians by Specialties**: Bar chart showing Internal Medicine (224), Family Medicine (120), etc.
- **Total Revenue by Physicians**: Bar chart showing top earners (e.g., Dr. Hendricks: $25,090).
- **Geographic Distribution**: U.S. map highlighting physician distribution.
- **Total Physicians by Weekly Working Hours**: Pie chart showing 31-40 hours (61.65%).

### 5. Patients Dashboard
- **Key Metrics**:
  - Total Patients: 4,962
  - Total Visits: 84,219
  - Average Age: 45
  - Average Visits per Patient: 17
  - Average Bill per Patient: $297

- **Demographic Distribution**: Stacked bar chart showing gender distribution across age groups.
- **Patient Visit Trends Over Time**: Line chart showing visit trends.
- **Geographic Distribution**: U.S. map showing patient distribution.
- **Monthly & Weekly Visit Patterns**: Table showing visits by day and month.

### 6. Transactions Dashboard
- **Key Metrics**:
  - Total Transactions: 955
  - Average Bill per Patient: $297
  - Total Revenue: $1,472,267
  - Total Payments: $703,613

- **Transaction Breakdown: Adjustments by Reason**: Bar chart showing Charge (902), Contractual (16), etc.
- **Total Transactions by Location**: Bar chart showing Angelstone Community Hospital (586).
- **Transactions by Month & Year**: Line chart showing gross charges and adjustments.

---

## Conclusion

This project demonstrates the power of data analysis in healthcare, transforming raw data into actionable insights. The relational database and dashboards provide a comprehensive view of Nova Clinic’s operations, enabling better decision-making in payer management, diagnosis tracking, physician allocation, patient care, and transaction oversight.

---