# Raw Data Overview

This folder contains the raw dataset files used for bank loan risk analysis.

## Files

- `application_data.csv`
  - Primary dataset of loan applications and borrower profiles.
  - Includes target label `TARGET`, loan amounts, borrower demographics, and credit bureau related variables.

- `previous_application.csv`
  - Historical credit applications linked to borrowers in the primary dataset.
  - Includes prior loan amounts, contract status, timing information, interest rates, and credit acquisition details.

- `columns_description.csv`
  - Data dictionary describing columns in both `application_data.csv` and `previous_application.csv`.
  - Useful for understanding feature meaning and selecting variables for analysis.

## Usage

1. Keep these files in the `Raw_data/bank_loan_case_study` folder.
2. Use `columns_description.csv` to interpret the dataset fields.
3. Load the CSV files into your analysis notebook or script to begin exploration and preprocessing.

## Notes

- These are raw source files and should not be modified directly before data cleaning.
- The main analysis notebook is located at `EDA_and_cleaning/Python_file/Bank_loan_riskanalysis_KK.ipynb`.
