# Excel Data Sync
**Version:** 1.0.0 | **Status:** Production | **License:** MIT

---

## 1. Purpose

The **Excel Data Sync** project provides a lightweight ETL pipeline for automated retrieval, parsing, and aggregation of structured Excel data stored in a remote Git repository.

The system eliminates manual file handling by providing a single access point for analytics processing.

---

## 2. Core Functionality

| Component | Description |
|-----------|-------------|
| **File Download** | Retrieves the source file via a permanent raw URL from GitHub |
| **Structure Parsing** | Handles merged cells and non‑standard worksheet layouts |
| **Multi‑sheet Aggregation** | Combines data from three sheets into a unified dataset |
| **Data Cleaning** | Removes currency symbols, whitespace, and normalises data types |
| **Record Indexing** | Applies automatic sequential numbering to all entries |
| **Result Export** | Outputs a well‑structured Excel workbook |

---

## 3. Data Flow

| Step | Process | Description |
|------|---------|-------------|
| 1 | **Fetch** | Script sends HTTP GET request to the permanent GitHub raw URL. |
| 2 | **Validate** | Response status is verified. File integrity is checked by size. |
| 3 | **Load** | The binary content is saved to local storage as `Book.xlsx`. |
| 4 | **Extract** | The script reads three worksheets: `Sheet 1`, `Sheet 2`, `Sheet 3`. |
| 5 | **Parse** | From each sheet, data is extracted from rows 8, 12, 16, 20, 24. |
| 6 | **Clean** | Currency symbols (`₽`) and spaces are removed; type conversion is applied. |
| 7 | **Aggregate** | All records are combined into a single dataset with sequential indexing. |
| 8 | **Export** | The final table is saved as `processed_data.xlsx`. |

---


