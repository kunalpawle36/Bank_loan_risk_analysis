# Bank Loan Risk Analysis Results

## What was analyzed

- Loan application data was loaded from `application_data.csv`.
- Historical credit application data was loaded from `previous_application.csv`.
- The goal was to understand loan payment difficulty and prepare the data for later modeling.

## Key data preparation steps

- Columns with very high missing values were dropped.
- Missing values were filled using reasonable defaults:
  - `AMT_ANNUITY` with the most common annuity value
  - `OCCUPATION_TYPE` with `Others`
  - `NAME_TYPE_SUITE` with the most common suite type
  - `CNT_FAM_MEMBERS` with the median family size
  - credit bureau enquiry counts and social-circle metrics with medians
- Negative day-offset fields were converted to absolute values for easier interpretation.

## Important findings

- The dataset includes a clear target variable:
  - `TARGET = 1` means the borrower had payment difficulty.
  - `TARGET = 0` means the borrower did not have difficulty.
- Strong risk-related features were identified:
  - loan amount relative to income (`CREDIT_RATIO`)
  - income and credit amount ranges
  - borrower age and employment duration
  - previous application history

## New features created

- `DAYS_BIRTH_IN_YEAR` and `DAYS_EMPLOYED_IN_YEAR`
- `DAYS_BIRTH_RANGE` and `DAYS_EMPLOYED_RANGE`
- `AMT_CREDIT_RANGE` and `AMT_INCOME_TOTAL_RANGE`
- `CREDIT_RATIO`
- `AMT_INCOME_TOTAL_RANGE1` (quartile-based income category)


