# Aadhaar Data Cleaning & Preprocessing

A comprehensive data cleaning and preprocessing pipeline for Aadhaar biometric, demographic, and enrollment datasets. This project provides automated data cleansing workflows designed for UIDAI 2026 hackathon analysis.

## 📋 Table of Contents
- [Overview](#overview)
- [Project Structure](#project-structure)
- [Datasets](#datasets)
- [Data Cleansing Notebooks](#data-cleansing-notebooks)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Data Quality](#data-quality)
- [Contributing](#contributing)

## Overview

This project contains Jupyter notebooks and cleaned datasets for processing and analyzing Aadhaar data. The datasets have been segmented into manageable chunks and undergo rigorous data cleansing processes to ensure data quality and consistency.

**Key Features:**
- Automated data cleaning pipelines for three data types
- Segmented dataset files for scalability
- Comprehensive data quality checks
- Jupyter notebook-based workflows
- CSV format output for easy integration

## Project Structure

```
aadhaar-data-cleaning/
├── README.md                          # Project documentation
├── Analysis.pbix                      # Power BI analytics dashboard
├── Data-Cleansing/                    # Jupyter notebooks for data processing
│   ├── biometric_data_cleaning.ipynb  # Biometric data cleaning pipeline
│   ├── demographic_data_cleaning.ipynb # Demographic data cleaning pipeline
│   └── enrolment_data_cleaning.ipynb  # Enrollment data cleaning pipeline
└── Dataset/                           # Cleaned datasets
    ├── Biometric/                     # Cleaned biometric data
    │   ├── cleaned_api_data_aadhar_biometric_0_500000.csv
    │   ├── cleaned_api_data_aadhar_biometric_500000_1000000.csv
    │   ├── cleaned_api_data_aadhar_biometric_1000000_1500000.csv
    │   └── cleaned_api_data_aadhar_biometric_1500000_1861108.csv
    ├── Demographic/                   # Cleaned demographic data
    │   ├── cleaned_api_data_aadhar_demographic_0_500000.csv
    │   ├── cleaned_api_data_aadhar_demographic_500000_1000000.csv
    │   ├── cleaned_api_data_aadhar_demographic_1000000_1500000.csv
    │   ├── cleaned_api_data_aadhar_demographic_1500000_2000000.csv
    │   └── cleaned_api_data_aadhar_demographic_2000000_2071700.csv
    └── Enrollment/                    # Cleaned enrollment data
        ├── cleaned_api_data_aadhar_enrolment_0_500000.csv
        ├── cleaned_api_data_aadhar_enrolment_500000_1000000.csv
        └── cleaned_api_data_aadhar_enrolment_1000000_1006029.csv
```

## Datasets

### Biometric Data
- **Total Records:** ~1.86 million
- **Segments:** 4 CSV files
- **File Size:** Split into manageable chunks (500K-1M records per file)
- **Contents:** Fingerprint, iris, and facial recognition data

### Demographic Data
- **Total Records:** ~2.07 million
- **Segments:** 5 CSV files
- **File Size:** Split across multiple files for efficient processing
- **Contents:** Personal information, address, contact details

### Enrollment Data
- **Total Records:** ~1.01 million
- **Segments:** 3 CSV files
- **File Size:** Distributed for performance optimization
- **Contents:** Enrollment timestamps, status, and metadata

## Data Cleansing Notebooks

### 1. Biometric Data Cleaning
**File:** `Data-Cleansing/biometric_data_cleaning.ipynb`

Handles cleaning and validation of biometric data:
- Removes duplicate biometric entries
- Validates quality metrics for fingerprint/iris/facial data
- Handles missing values in biometric attributes
- Standardizes data formats
- Quality assurance checks

### 2. Demographic Data Cleaning
**File:** `Data-Cleansing/demographic_data_cleaning.ipynb`

Processes demographic and personal information:
- Standardizes name and address formats
- Validates contact information (phone, email)
- Handles missing demographic fields
- Removes duplicate records
- Data consistency validation

### 3. Enrollment Data Cleaning
**File:** `Data-Cleansing/enrolment_data_cleaning.ipynb`

Cleans enrollment-related information:
- Validates enrollment dates and timestamps
- Checks enrollment status consistency
- Removes invalid enrollment records
- Fills missing enrollment metadata
- Cross-references with demographic data

## Analytics Dashboard

### Power BI Analytics File
**File:** `Analysis.pbix`

A comprehensive Power BI dashboard for visualizing and analyzing the cleaned Aadhaar datasets.

**Features:**
- Interactive data visualizations
- Key metrics and KPIs from biometric, demographic, and enrollment data
- Trend analysis and statistical summaries
- Data quality insights
- Cross-dataset correlations
- Filterable views for detailed analysis

**Requirements:**
- Microsoft Power BI Desktop (latest version recommended)
- Or Power BI Service (cloud-based)

**How to Use:**
1. Download and install Power BI Desktop from [Microsoft](https://powerbi.microsoft.com/desktop/)
2. Open `Analysis.pbix` in Power BI Desktop
3. Connect to the cleaned CSV files in the `Dataset/` folder when prompted
4. Explore visualizations and generate insights
5. Export reports or dashboards as needed

## Installation & Setup

### Requirements
- Python 3.7+
- Jupyter Notebook or JupyterLab
- pandas
- numpy
- scikit-learn (optional, for advanced analysis)

### Install Dependencies
```bash
pip install jupyter pandas numpy scikit-learn
```

### Launch Jupyter
```bash
# From the project root directory
jupyter notebook

# Or use JupyterLab
jupyter lab
```

## Usage

### Running a Cleaning Pipeline

1. **Open Jupyter Notebook:**
   - Navigate to `Data-Cleansing/` folder
   - Open the desired notebook (e.g., `biometric_data_cleaning.ipynb`)

2. **Execute Cells:**
   - Run cells sequentially using `Shift + Enter`
   - Or run all cells using `Cell > Run All`

3. **Output:**
   - Cleaned data is saved to the `Dataset/` folder
   - CSV files are organized by data type and record range

### Processing Large Datasets

Each dataset file contains a specific record range (as indicated in the filename):
- `0_500000`: Records 0 to 499,999
- `500000_1000000`: Records 500,000 to 999,999
- And so on...

Process files independently or in sequence depending on your system resources.

## Data Quality

### Quality Checks Performed
✓ **Completeness:** Identification of missing values
✓ **Consistency:** Validation of data format and ranges
✓ **Accuracy:** Removal of duplicates and invalid entries
✓ **Validity:** Cross-field validation and integrity checks
✓ **Standardization:** Uniform formatting across all fields

### Quality Metrics
Each notebook generates quality reports showing:
- Records removed during cleaning
- Percentage of valid records retained
- Data quality scores
- Issues identified and resolved

## Contributing

To improve this project:
1. Review the existing cleaning pipelines
2. Identify areas for enhancement
3. Test changes on a sample dataset first
4. Document any modifications
5. Update this README accordingly

## Notes

- All datasets are cleaned versions of raw API data
- Record ranges in filenames indicate the data segments
- CSV files can be combined for full-dataset analysis
- Backup original raw data before processing