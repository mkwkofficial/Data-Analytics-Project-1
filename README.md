# Data Analytics Project 1 – Data Cleaning & Preparation

## 📌 Project Overview

This project is part of the **Data Analytics Project 1** training assignment by **DecodeLabs**.

The main focus of this project is **Data Cleaning & Preparation**. The goal is to transform a raw dataset into a clean, consistent, and reliable dataset that can be used for further data analysis.

The project focuses on identifying missing values, checking duplicate records and IDs, and validating data formats such as dates and numeric fields.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Identify missing or null values
- Handle missing values appropriately
- Check and remove duplicate records where required
- Verify that Order IDs are unique
- Validate date formatting
- Check numeric data types and values
- Prepare a clean dataset for further analysis

These tasks follow the requirements provided for Project 1: **Data Cleaning & Preparation**.

---

## 📊 Dataset Overview

The dataset contains **1,200 records** and **14 columns** related to customer orders.

### Dataset Columns

| Column | Description |
|---|---|
| `OrderID` | Unique identifier for each order |
| `Date` | Date on which the order was placed |
| `CustomerID` | Identifier of the customer |
| `Product` | Product associated with the order |
| `Quantity` | Number of units ordered |
| `UnitPrice` | Price per unit |
| `ShippingAddress` | Customer shipping address |
| `PaymentMethod` | Payment method used for the order |
| `OrderStatus` | Current status of the order |
| `TrackingNumber` | Shipment tracking number |
| `ItemsInCart` | Number of items in the customer's cart |
| `CouponCode` | Coupon or promotional code used |
| `ReferralSource` | Source through which the customer arrived |
| `TotalPrice` | Total price of the order |

---

## 🧹 Data Cleaning Process

### 1. Missing Values

Missing-value analysis was performed across all 14 columns.

The following result was identified:

- `CouponCode`: **309 missing values**
- All other columns: **0 missing values**

The missing `CouponCode` values represent orders where a coupon code was not provided. These values can be handled by replacing the blank/null values with:

`No Coupon`

This makes the dataset easier to analyze while preserving the meaning of the data.

---

### 2. Duplicate Records

The dataset was checked for duplicate rows.

**Result:**

- Duplicate complete rows: **0**

Therefore, no complete duplicate records needed to be removed.

---

### 3. Duplicate Order IDs

The `OrderID` column was checked using a `COUNTIF`-based validation.

**Result:**

- Total Order IDs: **1,200**
- Unique Order IDs: **1,200**
- Duplicate Order IDs: **0**

Therefore, every order currently has a unique `OrderID`.

> Note: `CustomerID` can legitimately appear more than once because one customer can place multiple orders. Customer ID duplication is therefore not treated as duplicate order records.

---

### 4. Date Validation

The `Date` column was checked for missing and invalid date values.

**Result:**

- Missing dates: **0**
- Invalid/unreadable dates: **0**
- Earliest date: **2023-01-01**
- Latest date: **2025-06-30**

The date column is stored as a valid date type and can be standardized for analysis using a consistent format such as:

`YYYY-MM-DD`

---

### 5. Numeric Data Validation

The following numeric fields were checked:

- `Quantity`
- `UnitPrice`
- `ItemsInCart`
- `TotalPrice`

Their data types were verified as numeric, allowing them to be used for calculations and analysis.

---

## 🔍 Excel Techniques Used

The following Excel techniques can be used to perform and verify the cleaning process:

### COUNTIF – Duplicate ID Check

```excel
=COUNTIF($A:$A,A2)
```

This formula counts how many times the `OrderID` in cell `A2` appears in the complete OrderID column.

Interpretation:

- `1` → Unique ID
- Greater than `1` → Duplicate ID

### Duplicate / Unique Status

```excel
=IF(COUNTIF($A:$A,A2)>1,"Duplicate","Unique")
```

### Other Excel Features

- Conditional Formatting
- Remove Duplicates
- Filter
- Sort
- Data Type Validation
- Missing Value Checks

---

## 📈 Data Quality Summary

| Data Quality Check | Result |
|---|---:|
| Total Records | 1,200 |
| Total Columns | 14 |
| Missing `CouponCode` | 309 |
| Missing values in other columns | 0 |
| Duplicate complete rows | 0 |
| Duplicate `OrderID` | 0 |
| Unique `OrderID` | 1,200 |
| Missing dates | 0 |
| Invalid dates | 0 |

---

## 🛠️ Tools Used

- **Microsoft Excel**
- Excel `COUNTIF`
- Conditional Formatting
- Remove Duplicates
- Sorting and Filtering
- Data Validation
- Basic Data Cleaning Techniques

---

## 📁 Project Structure

```text
data-analytics-project-1/
│
├── README.md
│
├── data/
│   ├── raw_dataset.xlsx
│   └── cleaned_dataset.xlsx
│
├── report/
│   └── data_cleaning_report.pdf
│
└── screenshots/
    ├── missing_values.png
    ├── duplicate_ids.png
    └── date_validation.png
```

> If the raw dataset contains private or sensitive information, do not upload it to a public GitHub repository. In that case, keep only an anonymized/cleaned version or provide a sample dataset.

---

## ✅ Final Outcome

The dataset was analyzed for the key data-quality issues required in Project 1:

- Missing values were identified
- Duplicate rows were checked
- `OrderID` uniqueness was verified
- Date values were validated
- Numeric fields were checked
- The dataset was prepared for further data analysis

The final cleaned dataset can now be used as a reliable starting point for future analytics tasks.

---

## 📚 Project Requirements

This project follows the DecodeLabs Data Analytics Project 1 requirements, which emphasize **Data Cleaning & Preparation**, including handling missing values, removing duplicates, and correcting data formats.

---

## 👤 Author

**Khuram Waheed**

Data Analytics Project 1  
Data Cleaning & Preparation
