# Data Quality & Reconciliation
 
![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-Reporting-217346?logo=microsoftexcel&logoColor=white)
![Data](https://img.shields.io/badge/Data-Synthetic-lightgrey)
 
A Python project that automates data quality checks and reconciliation between two transaction data sources, and produces a structured Excel report of every finding.
 
**Author:** Mohit Bhati
 
---
 
## Table of Contents
 
- [Overview](#overview)
- [Key Features](#key-features)
- [Input Data](#input-data)
- [Reconciliation Logic](#reconciliation-logic)
- [Output](#output)
- [Data Quality Issues Covered](#data-quality-issues-covered)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Skills Demonstrated](#skills-demonstrated)
- [Data Privacy](#data-privacy)
- [Future Improvements](#future-improvements)
- [Author](#author)
---
 
## Overview
 
Reconciling data from two systems is a common task in finance, operations and analytics. This project demonstrates a practical, repeatable workflow for comparing two synthetic transaction datasets and clearly separating clean records from problem records.
 
The script compares **Source A** and **Source B** and identifies:
 
- Duplicate records
- Records missing from one source
- Amount discrepancies
- Status discrepancies
- User mismatches
- Date mismatches
- Exact matches
## Key Features
 
- **Duplicate detection** on `transaction_id` in each source
- **Outer join reconciliation** so no record is silently dropped
- **Field-by-field comparison** of records present in both sources
- **Clear separation** of discrepancies from exact matches
- **Summary metrics** for a quick high-level view
- **Excel report** with one sheet per finding type
## Input Data
 
The project uses two synthetic datasets:
 
| File | Description |
|------|-------------|
| `source_a.csv` | Synthetic Source A transactions |
| `source_b.csv` | Synthetic Source B transactions |
 
**Fields**
 
| Field | Description |
|-------|-------------|
| `transaction_id` | Unique identifier used as the reconciliation key |
| `user_id` | User associated with the transaction |
| `transaction_date` | Date of the transaction |
| `amount` | Transaction amount |
| `status` | Transaction status |
 
The datasets intentionally contain several data quality issues for demonstration purposes.
 
## Reconciliation Logic
 
The script follows these steps:
 
1. Load both datasets
2. Check for duplicate transaction IDs
3. Remove duplicates for reconciliation
4. Perform an outer join on `transaction_id`
5. Identify records available only in Source A
6. Identify records available only in Source B
7. Compare common records field by field
8. Separate discrepancies from exact matches
9. Build a reconciliation summary
10. Save the results into an Excel workbook
## Output
 
Running the script generates `reconciliation_result.xlsx` with the following sheets:
 
| Sheet | Contents |
|-------|----------|
| **Summary** | High-level reconciliation metrics (see below) |
| **Duplicates A** | Duplicate transaction IDs found in Source A |
| **Duplicates B** | Duplicate transaction IDs found in Source B |
| **Only in A** | Transactions in Source A but missing from Source B |
| **Only in B** | Transactions in Source B but missing from Source A |
| **Discrepancies** | Transactions in both sources with differences in one or more fields |
| **Exact Matches** | Transactions that match across both sources |
 
**Summary metrics**
 
- Rows in Source A
- Rows in Source B
- Duplicate records
- Records available only in Source A
- Records available only in Source B
- Discrepancies
- Exact matches
## Data Quality Issues Covered
 
The synthetic datasets include examples such as:
 
- Duplicate transaction IDs
- Missing transactions
- Different transaction amounts
- Records existing in only one source
These cases are intentionally included to demonstrate the automated reconciliation logic.
 
## Tech Stack
 
- Python
- pandas
- openpyxl
- Microsoft Excel
## Project Structure
 
```text
data-quality-reconciliation/
├── source_a.csv                 # Synthetic Source A dataset
├── source_b.csv                 # Synthetic Source B dataset
├── reconciliation.py            # Reconciliation script
├── reconciliation_result.xlsx   # Generated reconciliation report
├── requirements.txt             # Python dependencies
└── README.md                    # Project documentation
```
 
## Getting Started
 
### Prerequisites
 
- Python 3
- pip
### 1. Clone the repository
 
```bash
git clone https://github.com/mohitbhati05042001-byte/data-quality-reconciliation.git
cd data-quality-reconciliation
```
 
### 2. Install dependencies
 
```bash
pip install -r requirements.txt
```
 
### 3. Check the input files
 
Make sure both datasets are in the project folder:
 
- `source_a.csv`
- `source_b.csv`
### 4. Run the reconciliation
 
```bash
python reconciliation.py
```
 
### 5. Review the report
 
Open the generated file:
 
```text
reconciliation_result.xlsx
```
 
## Skills Demonstrated
 
- Data quality analysis
- Data reconciliation
- Python automation
- Data validation
- Duplicate detection
- Discrepancy analysis
- Data comparison
- Excel reporting
- pandas
## Data Privacy
 
All data used in this repository is synthetic and created specifically for demonstration purposes.
 
The repository does not contain confidential, customer, production, or employer data.
 
## Future Improvements
 
- [ ] Configurable reconciliation keys
- [ ] Tolerance thresholds for numeric differences
- [ ] Automated Excel formatting
- [ ] Reconciliation status by row
- [ ] Logging
- [ ] Automated summary charts
- [ ] Support for multiple input files
- [ ] SQL-based reconciliation examples
## Author
 
**Mohit Bhati**
 
GitHub: [@mohitbhati05042001-byte](https://github.com/mohitbhati05042001-byte)
