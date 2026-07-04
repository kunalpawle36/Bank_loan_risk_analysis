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

