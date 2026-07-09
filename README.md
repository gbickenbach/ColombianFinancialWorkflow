# Colombian Financial Credit Data Processing API

## Overview

This project provides a high-performance Python pipeline for downloading, cleaning, and analyzing the Colombian financial credit dataset published through **Datos.gov.co**. The notebook is designed to efficiently process a dataset containing over **44 million records**, reducing download times through parallelization and optimized data processing techniques.

The project automates the complete workflow from data extraction to generating cleaned datasets and summary statistics for downstream analysis.

---

## Features

- Download large public datasets from the Socrata API
- Parallelized data retrieval for improved performance
- Data cleaning and normalization
- Duplicate removal
- Missing value handling
- Frequency and percentage table generation
- Flexible sorting and organization of results
- Optimized for datasets exceeding 40 million rows

---

## Dataset

The notebook works with the public Colombian financial credit dataset available through Datos.gov.co:

- Source: https://www.datos.gov.co/
- Dataset ID: `w9zh-vetq`

The dataset contains millions of observations related to credit information reported by Colombian financial institutions.

---

## Project Workflow

```
API.ipynb
│
├── Data Extraction
│   ├── API requests
│   ├── Chunked downloads
│   └── Parallel downloading
│
├── Data Cleaning
│   ├── Missing value handling
│   ├── Duplicate removal
│   └── Data normalization
│
├── Data Processing
│   ├── Frequency calculations
│   ├── Percentage calculations
│   └── Category organization
│
└── Export / Analysis
```

---

## Requirements

Install the required Python packages:

```bash
pip install pandas requests numpy pyarrow
```

---

## Main Components

### 1. Data Extraction

The notebook downloads the complete dataset directly from the Socrata API.

Different strategies are implemented, including:

- Single-request downloads
- Chunked downloads
- Parallel downloads using concurrent futures

These methods allow efficient retrieval of very large datasets.

---

### 2. Data Cleaning

After downloading, the pipeline performs several preprocessing steps:

- Removal of duplicate records
- Handling missing values
- Standardization of categorical variables
- Data normalization

The cleaning functions are designed to operate efficiently on large datasets.

---

### 3. Parallel Processing

To improve execution time, the notebook uses multiprocessing techniques to clean and normalize data chunks simultaneously before combining them into a final dataset.

---

### 4. Summary Statistics

The notebook generates descriptive summaries, including:

- Frequency tables
- Percentage distributions
- Sorted categorical summaries
- Organized outputs for reporting

These summaries can be customized using helper functions.

---

## Performance

The notebook was developed specifically for extremely large datasets.

Typical execution times:

| Task | Approximate Time |
|-------|-----------------:|
| Initial full download | ~35 minutes |
| Subsequent processing from local file | ~4 minutes |

Using local cached data significantly reduces processing time after the initial download.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Requests
- PyArrow
- Concurrent Futures
- Multiprocessing

---

## Example Applications

This pipeline can be adapted for:

- Large-scale government datasets
- Financial data processing
- Credit market analysis
- Statistical reporting
- Data engineering pipelines
- Public API ingestion

---

## Notes

- The notebook is optimized for large-memory environments due to the size of the dataset.
- Local caching is recommended after the initial download to avoid repeated API requests.
- Parallel downloading substantially reduces extraction time compared to sequential requests.

---

## Future Improvements

- Automatic incremental updates
- Retry logic for failed API requests
- Progress bars during downloads
- Database integration
- Command-line interface
- Configurable API parameters
- Automated scheduling for periodic updates
