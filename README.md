
# ERP Sales Data Analysis & Financial Analysis

## Overview

This project focuses on extracting, cleaning, and analyzing raw transactional data exported from an enterprise ERP system. The goal of the analysis is to restructure messy data, audit revenue streams, identify operational leaks (such as returns), and automate the generation of professional financial summaries.

## Tech Stack

* **Python:** Core data processing.
* **Pandas:** Data cleaning, type conversion, time-series resampling, and aggregations.
* **Seaborn & Matplotlib:** Dark-themed data visualization.
* **OpenPyXL:** Automated Excel workbook formatting and chart generation.

## Key Challenges Solved

* **ERP Structure Cleaning:** Successfully bypassed generic system headers and empty rows typical of raw ERP exports to programmatically assign the correct data taxonomy.
* **Pricing & VAT Auditing:** Reverse-calculated the 15% South African Value-Added Tax (VAT) from the consumer-facing price to verify the base revenue, distinguishing true system discounts from standard tax exclusions.
* **Anomaly Detection & Ledger Correction:** Identified a catastrophic human data-entry error (a single return logged at R 852,000,000.00). Programmatically cross-referenced historical sales to determine the true list price (R 9,800.00) and corrected the ledger without destroying the transaction history.
* **Automated Financial Reporting:** Engineered a script to aggregate top customers, highest-performing lines of business, and top revenue leaks, exporting the cleaned insights directly into a stylized, presentation-ready Excel dashboard.

## Project Structure

* `analysis.ipynb`: The primary Jupyter Notebook containing the data pipeline, cleaning logic, anomaly fixes, and visualization code.
* `Cleaned_Sales_Summary.xlsx`: An automated output file containing the final aggregated insights, formatted with custom headers, borders, and currency styling.

## Key Insights

1. **Seasonality:** Revenue peaks significantly in December (R 6.5M+) and March (R 5.2M+), with a noticeable mid-year slump in June.
2. **Product Ecosystem:** The business is heavily reliant on the `TM_Hardware` and `TM_iPhone` lines of business, which account for the vast majority of fulfilled stock.
3. **Fulfillment:** Warehouse `TRA` processes double the volume of the next largest fulfillment center.
