# Bank Loan Risk Analysis

## Project Overview

This project explores bank loan risk using a real-world loan application dataset. It focuses on data exploration, cleaning, feature engineering, and preparing the dataset for future predictive modeling of loan payment difficulty.

The analysis is performed in `EDA_and_cleaning/Python_file/Bank_loan_riskanalysis_KK.ipynb`.

## Dataset

The raw data is stored in `Raw_data/bank_loan_case_study` and includes:

- `application_data.csv`: primary loan application and borrower profile dataset.
- `previous_application.csv`: prior credit applications for the same borrowers.
- `columns_description.csv`: variable dictionary and field descriptions.

### Key variables in `application_data.csv`

- `SK_ID_CURR`: unique ID for each loan application
- `TARGET`: payment difficulty label (1 = payment difficulty, 0 = no difficulty)
- `AMT_CREDIT`: amount of loan granted
- `AMT_ANNUITY`: loan annuity payment
- `AMT_INCOME_TOTAL`: borrower income
- `AMT_GOODS_PRICE`: price of goods financed by the loan
- `CODE_GENDER`: borrower gender
- `FLAG_OWN_CAR`, `FLAG_OWN_REALTY`: asset ownership indicators
- `NAME_INCOME_TYPE`, `NAME_EDUCATION_TYPE`, `NAME_FAMILY_STATUS`: demographic categories
- `DAYS_BIRTH`, `DAYS_EMPLOYED`, `DAYS_REGISTRATION`, `DAYS_ID_PUBLISH`, `DAYS_LAST_PHONE_CHANGE`: relative timing features
- `EXT_SOURCE_1`, `EXT_SOURCE_2`, `EXT_SOURCE_3`: external scoring source features
- `OCCUPATION_TYPE`: borrower occupation category
- Bureau enquiry features: `AMT_REQ_CREDIT_BUREAU_HOUR`, `AMT_REQ_CREDIT_BUREAU_DAY`, ...
- Social circle default features: `OBS_30_CNT_SOCIAL_CIRCLE`, `DEF_30_CNT_SOCIAL_CIRCLE`, `OBS_60_CNT_SOCIAL_CIRCLE`, `DEF_60_CNT_SOCIAL_CIRCLE`

### Key variables in `previous_application.csv`

- `SK_ID_PREV`: previous application ID
- `SK_ID_CURR`: current application ID, used to link previous applications
- `NAME_CONTRACT_TYPE`: contract type for previous application
- `AMT_APPLICATION`, `AMT_CREDIT`, `AMT_DOWN_PAYMENT`, `AMT_GOODS_PRICE`: financial amounts from prior applications
- `NAME_CONTRACT_STATUS`: outcome of previous application
- `DAYS_DECISION`, `DAYS_FIRST_DRAWING`, `DAYS_LAST_DUE`, `DAYS_TERMINATION`: timing of prior loan events
- `RATE_DOWN_PAYMENT`, `RATE_INTEREST_PRIMARY`, `RATE_INTEREST_PRIVILEGED`: rate and interest variables
- `NAME_PAYMENT_TYPE`, `CODE_REJECT_REASON`, `CHANNEL_TYPE`, `NAME_SELLER_INDUSTRY`: behavior and acquisition features

## Analysis and Cleaning Workflow

The notebook performs the following steps:

1. Load `application_data.csv` and `previous_application.csv`
2. Inspect dataset shape, data types, missing values, and summary statistics
3. Drop columns with extremely high missing rates
4. Impute missing values for key fields:
   - `AMT_ANNUITY` with the mode
   - `OCCUPATION_TYPE` with `Others`
   - `NAME_TYPE_SUITE` with the mode
   - `CNT_FAM_MEMBERS` with the median
   - Bureau enquiry counts and social circle variables with the median
5. Visualize distributions and counts for categorical and numerical features
6. Convert negative day offsets to absolute values
7. Create derived features including:
   - borrower age in years
   - employment duration in years
   - age and employment ranges
   - credit and income ranges
   - `CREDIT_RATIO` = `AMT_CREDIT` / `AMT_INCOME_TOTAL`
8. Merge application data with previous application records on `SK_ID_CURR`
9. Export a target-focused subset for deeper analysis

## Repository Structure

- `Readme.md`: project overview and usage guide
- `EDA_and_cleaning/Python_file/Bank_loan_riskanalysis_KK.ipynb`: exploratory data analysis and cleaning notebook
- `Raw_data/bank_loan_case_study/application_data.csv`: main loan dataset
- `Raw_data/bank_loan_case_study/previous_application.csv`: historical loan applications
- `Raw_data/bank_loan_case_study/columns_description.csv`: data dictionary

## Reproducing the Analysis

1. Place the dataset files under `Raw_data/bank_loan_case_study`.
2. Open `EDA_and_cleaning/Python_file/Bank_loan_riskanalysis_KK.ipynb` in Jupyter or VS Code.
3. Update file paths inside the notebook if needed so they point to local dataset files.
4. Run the notebook cells sequentially to reproduce EDA, cleaning, and feature engineering.



