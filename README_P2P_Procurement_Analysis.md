# P2P Procurement Analytics — Advanced Excel

An end-to-end Procure-to-Pay (P2P) analytics project built in Microsoft Excel to analyze procurement spend, supplier performance, invoice and payment exposure, procurement compliance, sourcing effectiveness, process efficiency, savings, and supplier risk.

## Project Overview

The objective of this project is to turn procurement transaction data into actionable business insights using Advanced Excel.

The analysis follows the P2P lifecycle and focuses on questions such as:

- Where is procurement spend concentrated?
- Which suppliers show delivery-performance concerns?
- How much spend is exposed to overdue or on-hold payments?
- Where is Maverick purchasing occurring?
- How effectively are preferred suppliers and contract structures being used?
- Where are procurement cycle-time bottlenecks?
- Which suppliers show multiple risk signals?
- Where are the largest savings opportunities?

## Tools & Techniques

- Microsoft Excel
- PivotTables & PivotCharts
- XLOOKUP / INDEX-MATCH
- IF / COUNTIFS / SUMIFS
- Conditional logic and KPI calculations
- Data validation
- Multi-currency normalization
- Dashboard design
- Business-focused data storytelling

## Dataset

The dataset contains **5,200 procurement transactions** covering **2022–2024**.

The source data contains multiple currencies, including:

- AUD
- EUR
- GBP
- JPY
- USD

For comparable financial analysis, monetary values were normalized to **INR using month-wise FX rates based on the PO date**.

> **Important:** FX conversion uses the transaction period's applicable rate rather than today's exchange rate.

## Analytical Framework

The workbook is organized into the following modules:

### M1 — Spend Analysis
Analyzes spend by PO status, category, supplier, department, region, country, and supplier-category combinations.

### M2 — Supplier Performance
Evaluates on-time delivery, supplier late rates, and average days late to identify suppliers requiring delivery-performance review.

### M3 — Invoice & Payment
Analyzes invoice status, invoice matching, problem invoice rates, payment status, and supplier-level payment exposure.

### M4 — Procurement Compliance & Control
Examines Maverick spend, preferred-supplier usage, departmental compliance patterns, and Maverick spend across contract types.

### M5 — Savings & Budget
Analyzes identified savings by year, category, and supplier, including savings percentages and savings contribution.

### M6 — Process Efficiency
Analyzes procurement volume, PO status trends, lead time by year/category/department/PO type, and long-cycle purchase orders.

### M7 — Supplier Risk
Combines delivery, Maverick purchasing, single-source exposure, ESG scores, and financial exposure to assess supplier risk from multiple dimensions.

### M8 — Contract & Sourcing
Analyzes contract-type mix, preferred vs non-preferred sourcing, Maverick spend by contract type, and Spot spend by department.

### M9 — Integrated Analysis
Consolidates the strongest findings into five management priorities and associated actions.

## Executive Dashboard

The final Excel dashboard summarizes the analysis using KPI cards and six management-focused visuals.

### Key KPIs

| KPI | Result |
|---|---:|
| Closed Procurement Spend | **₹51.65B** |
| Payment At-Risk | **₹12.10B** |
| Maverick Spend | **₹4.98B** |
| Identified Savings | **₹5.26B** |
| On-Time Delivery | **65.0%** |

**Payment At-Risk = Overdue + On Hold**

**Maverick Spend = Spend flagged as Maverick**

## Key Findings

### 1. Payment exposure
**₹12.10B** of closed spend is classified as **Overdue or On Hold**, representing approximately **23.4% of closed spend**.

### 2. Procurement compliance
The analysis identifies **₹4.98B of Maverick spend**, approximately **9.6% of closed spend**. All flagged Maverick spend is associated with non-preferred suppliers.

### 3. Supplier delivery
Overall on-time delivery is **65%**, meaning **35% of closed POs were delivered late**.

Suppliers highlighted for recurring delivery review include:

- SunRise Manufacturing
- Pacific Rim Supplies
- GlobalParts Ltd

### 4. Sourcing structure
**Spot procurement accounts for 53.7% of closed spend**, while non-preferred supplier usage is above 50% across every department.

### 5. Procurement cycle time
**284 of 3,094 closed POs (9.2%)** take more than **61 days** to complete.

### 6. Supplier risk is multidimensional
Delivery performance, Maverick purchasing, single-source exposure, payment exposure, and ESG scores do not consistently point to the same suppliers. The project therefore uses multiple indicators rather than relying on a single supplier-risk measure.

## Business Value

This project demonstrates how procurement transaction data can be converted into:

**Data → Analysis → KPI → Business Insight → Management Action**

Rather than producing only descriptive PivotTables, the project connects multiple dimensions of the P2P process to identify financial, operational, compliance, sourcing, and supplier-risk opportunities.

## Limitations

- The dataset is a consolidated procurement dataset rather than a fully normalized enterprise P2P database containing separate PR, PO, GRN, invoice, and payment tables.
- Some indicators, such as payment exposure and Maverick spend, are treated as analytical flags from the dataset and should be validated against underlying company policies and accounting records in a real business environment.
- Savings analysis uses INR-normalized monetary values; savings percentage is retained as the transaction-level percentage metric.

## Future Enhancement

A reusable **Vendor 360° Report** can be added to the workbook, allowing a user to select a supplier and retrieve:

- PO count
- Closed spend
- Payment status exposure
- Overdue / On Hold amounts
- Late PO count and late rate
- Maverick PO count
- Single-source exposure
- ESG score

A separate Power BI dashboard can also be developed later using the cleaned procurement dataset to demonstrate interactive BI reporting.

## Author

**Sudhir Kumar**

B.Com (Honours) Graduate | Aspiring Data Analyst / P2P Analyst

Skills demonstrated through this project: **Excel, data analysis, financial analysis, procurement analytics, KPI development, business reporting, and data storytelling.**
