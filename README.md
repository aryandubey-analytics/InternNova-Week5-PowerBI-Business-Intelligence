# InternNova-Week5-PowerBI-Business-Intelligence
InternNova Week 5 Power BI project covering data cleaning, data modeling, DAX measures, interactive dashboards, business intelligence, and data-driven insights.

## Project Overview

This repository contains my **Week 5 Data Analyst Internship project for InternNova**, focused on **Power BI and Business Intelligence**.

The project covers the complete BI workflow: importing and cleaning data with Power Query, creating a relational data model, writing DAX measures, building interactive visualizations, designing a dashboard, and extracting business insights and recommendations.

## Tools Used

- Microsoft Power BI Desktop
- Power Query
- DAX
- Microsoft Excel

## Dataset

The project uses a retail business dataset with four related tables:

- **SalesTable** – transaction-level sales records
- **ProductsTable** – product and category information
- **CustomersTable** – customer demographic and regional information
- **DateTable** – date, month, year, and quarter fields

## Tasks Completed

### 1. Power BI Introduction & Data Import
- Imported the Excel dataset into Power BI.
- Reviewed all four tables, columns, and data types.
- Explored the Power BI and Power Query interfaces.

### 2. Data Cleaning & Preparation
- Corrected data types.
- Handled an invalid Quantity value.
- Removed duplicate records.
- Removed the unnecessary Notes column.
- Standardized inconsistent text values.
- Reviewed and cleaned customer, product, and date fields.

### 3. Data Modeling & Relationships

A star-schema style model was created with **SalesTable** as the fact table and ProductsTable, CustomersTable, and DateTable as dimension tables.

Relationships:

- ProductsTable[Product_ID] **1 → \*** SalesTable[Product_ID]
- CustomersTable[Customer_ID] **1 → \*** SalesTable[Customer_ID]
- DateTable[Date] **1 → \*** SalesTable[Order_Date]

### 4. DAX Measures

```DAX
Total Sales = SUM(SalesTable[Sales_Amount])

Average Sales = AVERAGE(SalesTable[Sales_Amount])

Total Orders = DISTINCTCOUNT(SalesTable[Order_ID])

Total Profit = SUM(SalesTable[Profit])

Maximum Sales = MAX(SalesTable[Sales_Amount])

Minimum Sales = MIN(SalesTable[Sales_Amount])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
