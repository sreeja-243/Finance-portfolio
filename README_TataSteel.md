# Tata Steel: Ratio Analysis and Credit Risk Dashboard (FY22 to FY26)

[Back to portfolio](README.md) | **Workbook:** [tata_steel_credit_dashboard.xlsx](tata_steel_credit_dashboard.xlsx) | **Raw data:** [Raw_Data_Tata_Steel.xlsx](Raw_Data_Tata_Steel.xlsx)
**Company:** Tata Steel Ltd (consolidated) | **Data:** Screener.in Excel export, Nov 2026 | **Units:** Rs. crore

## Objective
Assess the credit quality of a capital-intensive, cyclical borrower whose net profit swung from Rs. 40,154 cr (FY22) to a Rs. 4,437 cr loss (FY24) and back to profit (FY26).

## Data
The `Raw_Data` sheet is the unedited Screener export (identical to the separate raw file in this repo). Every figure on `Historicals` is a formula pointing to it, including EBITDA (profit before tax - other income + depreciation + interest), cash and the working-capital days.

## What the model does
| Sheet | Purpose |
|---|---|
| `Cover` | Scope, legend, data notes |
| `Historicals` | Five years of P&L, balance sheet, cash flow and working-capital inputs, linked to Raw_Data |
| `Ratios` | Profitability, leverage (gross and net), coverage (EBITDA and EBIT based), cash-flow credit metrics, working-capital proxies |
| `CreditRisk` | Altman Z-Score approximation and a rule-based 0 to 6 scorecard |
| `Dashboard` | KPI cards with green/amber/red flags, four charts, auto-generated takeaways |
| `Raw_Data` | Unedited Screener export |

## Key results
| Metric | FY24 (trough) | FY26 |
|---|---|---|
| Net profit margin | -1.9% | 4.6% |
| Gross debt / EBITDA | 3.9x | 2.7x |
| Net debt / EBITDA (after cash & bank) | 3.5x | 2.4x |
| Interest coverage, EBITDA basis | 3.0x | 4.8x |
| Interest coverage, EBIT basis | 1.6x | 3.1x |
| Operating cash flow / gross debt | 23% | 38% |
| Altman Z-Score (book equity) | 1.74 | 1.74 |

- Scorecard: **2 of 6, "Elevated Risk"**. Z-Score is 1.74 on book equity and 2.07 using current market cap (distress below 1.81, grey zone 1.81 to 2.99).
- ROE (average equity) recovered to 11.2% in FY26 from -4.5% in FY24.
- Free cash flow proxy (operating + investing cash flow) was Rs. 20,667 cr in FY26.
- Reading: a recovering but still stretched cyclical credit, not a safe one. EBIT coverage is much thinner than EBITDA coverage because depreciation is heavy.

## Method notes
- ROE and ROA use **average** balances from FY23; FY22 uses closing balances (no FY21 balance sheet in the data).
- Working capital days are calculated from the raw balance sheet: debtor days = receivables / sales x 365; inventory days = inventory / cost of goods x 365 (cost of goods = raw material cost less change in inventory).
- Altman Z (1968 original): working capital proxy, retained earnings (reserves as proxy), EBIT, equity / liabilities, asset turnover.
- Scorecard: 0 to 2 points each for interest coverage, Gross Debt / EBITDA and Z-Score. The scorecard uses gross debt; net debt is shown for reference.

## Limitations
- Free cash flow is a **proxy** (operating + investing cash flow) because capex is not itemised in the export.
- Payables are not split out, so **days payable and the cash conversion cycle are not calculated**; the operating cycle excludes them.
- There is no current/quick ratio (current assets and liabilities are not split); working capital uses labelled proxies.
- Only the Altman cut-offs come from the literature. Interest-coverage and Debt/EBITDA thresholds are analyst rules of thumb. Altman's model was calibrated on US listed manufacturers, so treat it as directional.
- Market price is used only for the reference market-cap Z-Score.

*Educational portfolio exercise, not investment advice.*
