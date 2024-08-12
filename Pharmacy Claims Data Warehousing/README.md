# Pharmacy Claims

**Author**: Ayeshabi W Tigdikar  
**Program**: Master of Science in Project Management, Northeastern University  
**Course**: Data Warehousing and SQL  
**Instructor**: Professor Kayal Chandrasekaran  
**Date**: March 30th, 2024

---

## Table of Contents

1. [Introduction](#introduction)
2. [Normalization](#normalization)
3. [Primary and Foreign Key](#primary-and-foreign-key)
4. [Entity Relationship Diagram](#entity-relationship-diagram)
5. [Analytics and Reporting](#analytics-and-reporting)
6. [Conclusion](#conclusion)

---

## Introduction

This project explores a dataset containing information related to prescriptions, including member details, drug information, fill dates, copay amounts, and insurance payments. The primary objective is to gain insights into prescription patterns, analyze costs covered by insurance, and segment the data based on member age groups.

## Normalization

The dataset initially contained repeating groups of data that prevented it from being in 1NF (First Normal Form). By organizing prescriptions into distinct rows based on fill dates, copays, and insurance paid amounts, the dataset was normalized to 1NF. Further steps were taken to ensure the dataset met the criteria for 2NF and 3NF, involving the elimination of transitive dependencies. The final normalized structure consists of one fact table and four dimension tables, enhancing data organization and usability.

## Primary and Foreign Key

The dataset's normalized tables are interconnected via primary and foreign keys:

- **Dim_Member_Details_Table**: Primary Key - `member_id`
- **Dim_Drugs_Table**: Primary Key - `drug_ndc`
- **Dim_DrugForm_Table**: Primary Key - `drug_form_code`
- **Dim_DrugGeneric_Table**: Primary Key - `drug_brand_generic_code`
- **Fact_Prescription_Table**: Primary Key - `prescription_id`, Foreign Keys - `member_id`, `drug_ndc`, `drug_form_code`, `drug_brand_generic_code`

The `Fact_Prescription_Table` is the central table in the schema, referencing the dimension tables through foreign keys.

## Entity Relationship Diagram

The dataset's structure follows a star schema, with one central fact table (`Fact_Prescription_Table`) surrounded by four dimension tables (`Dim_Member_Details_Table`, `Dim_Drugs_Table`, `Dim_DrugForm_Table`, `Dim_DrugGeneric_Table`). This design is commonly used in data warehousing for its efficiency in querying and reporting.

## Analytics and Reporting

1. **Number of Prescriptions Grouped by Drug Name**:  
   - The drug **AMBIEN** was prescribed a total of 5 times.

2. **Total Prescriptions, Distinct Members, Copay, and Insurance Paid by Age Group**:  
   - There is 1 unique member aged 65+ with a total of 6 prescriptions.

3. **Amount Paid by Insurance for the Most Recent Prescription Fill Date**:  
   - For member **Jane Doe** (`member_id: 10003`), the most recent fill date is **May 16th, 2018**, for the drug **AMBIEN**, with an insurance payment of **$322**.

## Conclusion

Normalization of the dataset to 3NF successfully removed transitive dependencies, leading to a more organized and efficient data structure. The analysis provided valuable insights into prescription trends, highlighting the significance of data normalization and analysis in deriving actionable insights in the pharmaceutical industry.

---

This README provides an overview of the Pharmacy Claims project, summarizing the data normalization process, key structural elements like primary and foreign keys, and the analytics derived from the dataset.
