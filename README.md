# Customer_personality_cleaning
 Marketing Campaign Data Cleaning Project

This project involves cleaning and preprocessing a marketing campaign dataset to prepare it for analysis and modeling.

## 📊 Dataset Overview

- **Source**: [Kaggle - Customer Personality Analysis](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis)
- **File used**: `marketing_campaign.csv` (tab-separated)
- The dataset includes customer demographics, campaign history, purchase behavior, and response to marketing offers.

---

Cleaning & Preprocessing Steps

1. Loaded the tab-separated dataset using `pandas.read_csv(sep='\t')`
2. Renamed columns to lowercase, snake_case (e.g., `Year_Birth` → `year_birth`)
3. Handled missing values by dropping rows with null `income`
4. Removed duplicate rows
5. Converted the `dt_customer` column to `datetime` format
6. Standardized text values in `education` and `marital_status`
7. Created a new feature: `customer_since_years` based on `dt_customer`
8. Fixed data types for numeric fields: `income`, `kidhome`, and `teenhome`
9. Saved the cleaned dataset to `cleaned_marketing_campaign.csv`





