> **Data Confidentiality Notice**
>
> This project uses synthetic sample data generated based on the structure and format of company-provided sample data. The original company dataset has not been published due to company confidentiality policies. All analysis, calculations, and reports in this repository are demonstrated using the generated dataset and should not be interpreted as actual company production results.
>
> # May 2026 Production Data Analysis & Efficiency Monitoring

## Project Overview

This project demonstrates an end-to-end production data analysis workflow using Python, Pandas, and Excel. It focuses on data cleaning, data quality validation, production metrics, wastage calculations, and line-wise performance reporting using a synthetic dataset based on a company-provided sample structure.

### Objectives

- Clean and validate production records before analysis.
- Check missing values, duplicate records, date consistency, and data quality.
- Calculate machine wastage, total wastage, and operational wastage.
- Compare production metrics across production lines.
- Generate structured Excel reports to support operational analysis.

- ## Tools & Technologies

- **Python:** Data processing and analysis
- **Pandas:** Data cleaning, validation, and transformation
- **Jupyter Notebook:** Analysis workflow and documentation
- **Microsoft Excel:** Summary reports, metrics, and formatted outputs

## Dataset Description

The synthetic dataset represents 30 days of production records for 9 production lines in May 2026, containing 270 expected date-line records.

| Column | Description |
|---|---|
| Report Date | Production report date |
| LINE | Production line identifier |
| HMR | Hourly Machine Running measure, as defined for this project |
| LCR | Laminate Count Report |
| PCR | Packed Count Report |
| WASTAGE | Machine wastage quantity |
| % M/C | Machine wastage percentage |
| PROD | Production quantity |
| PKG | Packaging quantity |
| TOTAL_WAST | Total wastage quantity |
| OPERATIONAL_WASTAGE | Operational wastage quantity |
| OPERATIONAL_WASTAGE_% | Operational wastage percentage relative to PCR |

**Data note:** Some `PROD` and `PKG` values are blank for Line 9 in the generated dataset. These blanks are preserved rather than replaced with invented values or zeros.

## Calculation Methodology

The project uses the following formulas:

- **Machine Wastage:** `LCR - PCR`
- **Total Wastage:** `LCR - PKG`
- **Operational Wastage:** `Total Wastage - Machine Wastage`, equivalent to `PCR - PKG`
- **Machine Wastage %:** `(WASTAGE / LCR) × 100`
- **Operational Wastage %:** `(OPERATIONAL_WASTAGE / PCR) × 100`

Percentage calculations are undefined when their denominators are zero or missing; such cases should remain blank or be handled explicitly during validation.

## Data Cleaning & Validation

The notebook performs data quality checks before calculating production metrics.

Validation checks include:

- Total record count and expected date coverage.
- Duplicate records and duplicate date-line combinations.
- Missing values and missing production fields.
- Date validity and production quantity checks.
- Consistency of machine wastage against `LCR - PCR`.
- Validation of total wastage and operational wastage formulas where required inputs are available.
- Checks for packaging quantities exceeding production quantities on complete records.

### Validation Summary

- **Expected records:** 270
- **Reporting period:** 1–30 May 2026
- **Production lines:** 9
- **Duplicate full rows:** 0 in the validated dataset
- **Missing values:** 30 `PROD` and 30 `PKG` values for Line 9

These figures describe the generated dataset used in this project.

## Reports Generated

The project includes Excel workbooks for reviewing the results:

- **Production Master Dataset:** Structured records with calculated wastage metrics.
- **Production Metrics:** Line-wise comparisons, efficiency measures, and wastage summaries.
- **Summary Reports:** Validation results, daily summaries, monthly line summaries, and data completeness reports.

Screenshots of selected analysis outputs are included in the repository.

## Project Structure

```text
May-2026-Production-Analysis/
├── May_2026_Production_Report.ipynb
├── May_2026_Production_Master_Updated.xlsx
├── May_2026_Production_Metrics.xlsx
├── May_2026_Production_Summary_Reports.xlsx
├── Data_Validation.png
├── Daily_Summary.png
├── Monthly_Line_Summary.png
├── Machine_Efficiency.png
├── Highest_Operational_Wastages.png
└── Total_Highest_Machine_Wastage.png
```

## How to Run the Project

### Prerequisites

- Python 3.9 or later
- Jupyter Notebook
- Pandas
- NumPy
- OpenPyXL

### Setup

1. Clone or download this repository.
2. Install the required Python libraries:

   ```bash
   pip install pandas numpy openpyxl jupyter
   ```

3. Open Jupyter Notebook in the project directory:

   ```bash
   jupyter notebook
   ```

4. Open `May_2026_Production_Report.ipynb`.
5. Ensure the input file path in the notebook points to the location of `May_2026_Production_Master_Updated.xlsx`.
6. Run the notebook cells in order to reproduce the cleaning, validation, calculations, and reporting workflow.

## Limitations & Notes

- The dataset is synthetic and based on the structure of company-provided sample data.
- Results demonstrate the analysis methodology and are not verified actual company performance.
- Missing `PROD` and `PKG` values for Line 9 are preserved where source information is unavailable.
- Production metrics depend on the definitions and assumptions documented in the notebook.
- No business improvement or wastage reduction percentage is claimed without independent verification.

## Future Improvements

- Develop an interactive Excel or Power BI dashboard.
- Add monthly comparisons when additional datasets are available.
- Improve automated validation and reporting workflows.

## Author

**Aditya Tripathi**  
Commercial Support Intern | Production Team

Working on production data cleaning, validation, wastage analysis, and reporting using Python, Pandas, and Excel.

**Technical Skills:** Python · Pandas · Jupyter Notebook · Microsoft Excel

**Project Focus:** Production Data Analysis & Manufacturing Performance Monitoring
