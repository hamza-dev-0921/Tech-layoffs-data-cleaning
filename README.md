# Tech-layoffs-data-cleaning
# Tech Layoffs: Data Cleaning

Cleaning a dataset of 489 tech layoff events (2022 to 2023) using Python and pandas.
The same cleaning is done twice: once with functions and once with plain commands.

## Dataset
- 489 rows and 9 columns: company, total layoffs, impacted workforce percentage, reported date, industry, headquarter location, sources, status, additional notes
- Source: Kaggle (Technology Company Layoffs (2022-2023))

## What I did
1. Loaded the data and audited it (types, missing values, duplicates)
2. Cleaned column names and normalized text
3. Converted the word `Unclear` into real missing values
4. Removed duplicate rows
5. Converted text columns to numbers
6. Split `headquarter_location` into city and region
7. Fixed city, region and industry spelling mistakes, and created `main_industry`
8. Checked date formats and set rules for impossible values
9. Handled missing data (kept unreported layoffs as missing on purpose)
10. Flagged outliers (46 large layoffs, kept because they are real)
11. Set data types and created new columns: `month`, `layoff_size`, `impact_level`
12. Prepared the data for modelling (encoding and train/test split)
13. Compared before and after, and ran final checks

## Results
| | Before | After |
|---|---|---|
| Rows | 489 | 489 |
| Columns | 9 | 13 |
| Missing `total_layoffs` | 0 (hidden as `Unclear`) | 182 |
| Missing percentage | 0 (hidden as `Unclear`) | 133 |

Missing layoff numbers were not filled, because companies did not report them and filling would invent data.

## Files
- `Tech_layoffs_Hamza.ipynb`: cleaning notebook written with functions
- `Tech_layoffs_Hamza_1.ipynb`: same cleaning, written as plain commands
- `tech_layoffs.csv`: original data
- `layoffs_clean.csv`: cleaned data from the first notebook
- `layoffs_clean_1.csv`: cleaned data from the second notebook

## Tools
Python, pandas, NumPy, Jupyter
