# P2P Procurement Analytics — Advanced Excel

An end-to-end Procure-to-Pay (P2P) analysis of **5,200 purchase orders (2022–2024)** built in Microsoft Excel. It covers procurement spend, supplier performance, invoice and payment exposure, compliance, sourcing, process efficiency, savings and supplier risk, and ends with an executive dashboard and an interactive supplier report.

**Files in this repo**

| File | What it is |
|---|---|
| `Dataset_Procurement.xlsx` | The full workbook: raw data, 8 analysis modules, integrated analysis, Supplier AP Report and Dashboard |
| `Dashboard.pdf` | A PDF copy of the executive dashboard |
| `README.md` | This file |

---

## Headline results (closed POs, INR)

| KPI | Result |
|---|---:|
| Closed procurement spend | **₹51.65B** (3,094 closed POs) |
| Payment at-risk (Overdue + On Hold) | **₹12.10B** (23.4% of closed spend) |
| Maverick spend | **₹4.98B** (9.6% of closed spend) |
| Identified savings | **₹5.26B** (8.66% average savings rate) |
| On-time delivery | **65.0%** |

## Key findings

1. **Payment exposure.** ₹12.10B of closed spend is Overdue or On Hold. Overdue invoices are 12.0% of closed invoices and Disputed are 8.4%.
2. **Maverick spend.** ₹4.98B (9.6%) was bought outside the preferred sourcing process, and **all of it is with non-preferred suppliers**. Every one of the 386 Maverick POs came from just three suppliers: Atlantic Raw Materials (133), Meridian Tech (129) and Iron Gate Steel (124).
3. **Supplier delivery.** 35% of closed POs were delivered late, by 15.5 days on average. SunRise Manufacturing, Pacific Rim Supplies and GlobalParts Ltd combine high spend with 37–39% late rates.
4. **Savings.** About 79% of the ₹5.26B came from IT Software, Professional Services, Marketing and IT Hardware. The average savings rate rose from 8.35% (2022) to 8.82% (2023) and held in 2024.
5. **Sourcing.** Spot purchasing is 53.7% of closed spend, and non-preferred suppliers account for more than 50% of spend in every department. Marketing is the most exposed (74.2% non-preferred spend).
6. **Process speed.** Average lead time is about 36 days, and 284 of 3,094 closed POs (9.2%) took more than 61 days.
7. **Supplier risk is multidimensional.** High-risk suppliers are not much later than low-risk ones, but 67.9% of their spend is Maverick. No single indicator ranks the suppliers correctly, so the analysis combines delivery, Maverick, single-source, payment exposure and ESG scores.
8. **Data consistency flag.** 372 closed POs show an invoice status of *Paid* but a payment status of *Overdue* (218) or *On Hold* (154). These are worth reconciling against payment records.

---

## Questions the analysis answers

- Where is procurement spend concentrated?
- Which suppliers deliver late, and by how much?
- How much spend is exposed to overdue or on-hold payments?
- Where does Maverick purchasing happen?
- How well are preferred suppliers and contract types used?
- Where are the cycle-time bottlenecks?
- Which suppliers show several risk signals at once?
- Where are the biggest savings?

## Workbook structure

| Sheet | Purpose |
|---|---|
| **Data** | 5,200 rows × 62 fields, kept as an Excel Table |
| **M1 Spend Analysis** | Spend by PO status, category, department, supplier, region and country |
| **M2 Supplier Performance** | On-time rate, late rate and average days late by supplier |
| **M3 Invoice & Payment** | Invoice status, match type, problem-invoice rate, payment exposure by supplier |
| **M4 Procurement Compliance** | Maverick spend by department, contract type and preferred-supplier status |
| **M5 Savings & Budget** | Savings by year, category and supplier |
| **M6 Process Efficiency** | PO volume, lead time by year, category, department and PO type, long-cycle POs |
| **M7 Supplier Risk** | Risk tier crossed with delivery, Maverick spend, single-source and payment exposure |
| **M8 Contract & Sourcing** | Contract mix, preferred vs non-preferred, Spot spend by department |
| **Integrated P2P Analysis** | The strongest findings ranked into five management priorities with actions |
| **Supplier AP Report** | Pick a supplier from a dropdown and see its POs, spend, payment status, late rate, Maverick and single-source POs and ESG score |
| **Dashboard** | KPI cards and six visuals for management |
| **Calendar / FX Rates / Lists** | Supporting tables for dates, month-wise FX rates and the supplier dropdown |

## Method

- **Multi-currency normalization.** The source data is in AUD, EUR, GBP, JPY and USD. Each PO was converted to INR using the **month-wise FX rate for its PO date** (not today's rate). A key built from the PO month and currency is looked up in an FX rate table with `XLOOKUP`.
- **Scope.** Most analysis uses **Closed** POs only, so cancelled, open and disputed POs do not distort spend, payment or savings figures. The PO-status view in M1 shows all statuses for context.
- **Definitions.** *Payment at-risk* = Overdue + On Hold. *Maverick spend* = spend flagged as Maverick in the data.

## Excel techniques used

- 48 PivotTables and 6 charts
- `XLOOKUP`, `SUMIFS`, `COUNTIFS`, `AVERAGEIFS`, `GETPIVOTDATA`, `IFERROR`, `TEXT`
- `SORT` and `UNIQUE` to build the supplier dropdown list
- Data validation (supplier selector)
- Excel Tables with structured references
- Calendar and FX lookup tables
- KPI cards and dashboard layout

> **Excel version:** `XLOOKUP`, `SORT` and `UNIQUE` need Excel 2021 or Microsoft 365.

## How to use the workbook

1. Open `Dataset_Procurement.xlsx` and start on the **Dashboard** sheet.
2. Open **Supplier AP Report** and choose a supplier from the dropdown in cell B4.
3. Open any **M1–M8** sheet to see the supporting pivots and the written conclusion.
4. The **Integrated P2P Analysis** sheet lists the five management priorities and recommended actions.

## Limitations

- The dataset is one consolidated table, not a full enterprise P2P system with separate requisition, PO, goods-receipt, invoice and payment tables. There are no invoice dates, so invoice ageing could not be analysed.
- Flags such as Maverick spend and payment status are taken as given in the data. In a real business they would be checked against company policy and accounting records.
- The 372 Paid-invoice versus Overdue/On-Hold-payment cases may be a data-recording issue, not a payment problem. They need checking at the source.

## Next step

Rebuild the analysis as an interactive **Power BI** model (star schema, DAX measures, row-level security and drill-through supplier scorecards).

---

## Author

**Sudhir Kumar Salugu** — B.Com (Accounting & Finance) | Data Analyst / P2P Analyst
[LinkedIn](https://www.linkedin.com/in/salugu-sudhir-kumar/)
