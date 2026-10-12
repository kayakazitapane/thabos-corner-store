
# Thabo's Corner Store — Sales Insights System

**Occupational Certificate: Artificial Intelligence Software Developer — NQF Level 4**

Integrated project covering KM-04 (Data, Databases and Data Visualisation) and KM-05 (Programming and Python).

## Project Overview

This project cleans and analyses sales data for Thabo's Corner Store. The goal is to prepare reliable data, store it in a database, identify useful business insights, create charts, and demonstrate basic data security.

## Folder Structure

```text
thabos-corner-store/
├── data/
│   ├── products.csv
│   └── sales.csv
├── starter_code/
│   ├── README.md
│   ├── requirements.txt
│   ├── main.py
│   ├── data_cleaning.py
│   ├── database.py
│   ├── analysis.py
│   ├── visualize.py
│   └── security.py
├── PLAN.md
└── .gitignore
```

## Requirements and Setup

- Python 3.10 or later
- Git
- Visual Studio Code
- The Python packages listed in `requirements.txt`

Open a terminal in the project root folder and install the required packages:

```bash
python -m pip install -r starter_code/requirements.txt
```

Run the program from the project root when the pipeline is complete:

```bash
python starter_code/main.py
```

## Task 2: Data Cleaning

The raw CSV files contain deliberate data-quality problems. The cleaning functions are in `data_cleaning.py`.

### Product Data Cleaning

The raw products file contains 16 rows.

The cleaning process:
- Removes products with missing product IDs, names, or prices.
- Converts invalid product prices to missing values before removing unusable product records.
- Removes blank product IDs and product names.
- Removes unnecessary spaces from text fields.
- Standardises category capitalisation, for example, `beverages` becomes `Beverages`.
- Removes exact duplicate rows.

**Cleaning results:** 16 raw product rows were reduced to 12 cleaned product rows.

Three product records were removed because they contained missing information:
- P006 — Sunlight Dishwashing Liquid had no unit price.
- P009 — the product name was missing.
- P013 — Lays Chips 100g had no unit price.

One additional exact duplicate row was removed.

Products with missing prices were not assigned guessed prices because incorrect prices could produce inaccurate revenue calculations. The product with the missing name was removed because it could not be reliably identified.

### Sales Data Cleaning

The raw sales file contains 71 records.

The cleaning process:
- Converts supported date formats into the standard `YYYY-MM-DD` format.
- Removes sales with missing or invalid dates because they cannot be reliably used in date-based sales analysis.
- Converts quantities to numeric values.
- Removes rows with missing, invalid, zero, negative, or non-whole-number quantities.
- Removes sales with missing product IDs.
- Removes sales that reference product IDs that do not exist in the cleaned products data.
- Replaces missing or blank payment methods with `Unknown`.
- Replaces missing or blank customer types with `Unknown`.
- Removes exact duplicate rows.

**Cleaning results:** 71 raw sales records were reduced to 43 cleaned sales records.

Missing payment methods and customer types are labelled `Unknown` instead of being guessed. This preserves otherwise usable sales records while clearly showing that the original information was unavailable.

Sales with missing dates or unusable quantities were removed because those records could not be used reliably in the planned analysis. Sales referring to invalid product IDs were removed to ensure that sales can be linked to existing products.

### Task 2 Verification

The cleaning functions were tested using the original CSV files.

The latest test confirmed:
- 12 cleaned product rows.
- 43 cleaned sales rows.
- No missing values in the cleaned sales columns.
- No exact duplicate rows in the cleaned sales data.
- No invalid product references in the cleaned sales data.
- No invalid quantities in the cleaned sales data.
- Dates converted to the standard `YYYY-MM-DD` format.

The cleaning functions return cleaned copies of the data rather than intentionally modifying the original DataFrames.

## Task 3: Database and SQL

This section will be completed after the SQLite database is implemented and tested.

It will document:
- The database tables and their primary and foreign keys.
- How the cleaned products and sales are inserted.
- At least five SQL queries.
- The query results and what they show about the business.

## Task 4: Python Analysis

This section will be completed after the analysis functions are implemented and tested.

It will explain the calculations and business insights produced using Python functions, loops, conditionals, lists, and dictionaries.

## Task 5: Data Visualisation

This section will be completed after the charts are generated and checked.

The project requires:
- A bar chart showing revenue by product or category.
- A line chart showing the monthly sales trend.

The final README will describe the charts and the patterns they reveal.

## Task 6: Security

This section will be completed after the security functionality is implemented and tested.

It will document the password-hashing approach and include a 150–250 word reflection on the confidentiality, integrity, and availability (CIA) triad.

## Business Insights

This section will be completed after the database queries and Python analysis have been tested. It will summarise the most important findings and explain how they could help the store make business decisions.

The final business-insights section must contain 200–300 words, based on the actual results produced by the program.

## Final Submission Checklist

Before submitting, check the project brief and ensure the submission contains all required files, including:

- [ ] `PLAN.md`
- [ ] The complete `starter_code/` folder
- [ ] Updated README documentation
- [ ] The two generated PNG charts
- [ ] The SQLite database file (`store.db`)
- [ ] `SUBMISSION.txt`
- [ ] A ZIP file containing the required submission files
- [ ] A GitHub repository with at least eight meaningful commits

Only document database results, charts, and business insights after they have been generated and verified. Do not invent results.
