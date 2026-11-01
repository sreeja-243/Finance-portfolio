# Nestlé India: FP&A Budget vs Actual and FY27 Forecast

[Back to portfolio](README.md) | **Workbook:** [nestle_fpa_model.xlsx](nestle_fpa_model.xlsx) | **Raw data:** [Raw_Data_Nestle_India.xlsx](Raw_Data_Nestle_India.xlsx)
**Company:** Nestlé India Ltd (standalone) | **Data:** Screener.in Excel export, Nov 2026 | **Units:** Rs. crore

## Objective
Show the core FP&A cycle in one workbook: set drivers, build a budget, compare it with actuals, explain the variance down to cost lines, then roll the forecast forward and test it against reported results.

## Data
The `Raw_Data` sheet is the unedited Screener export (identical to the separate raw file in this repo). Every figure on `Historicals` is a formula pointing to it. EBITDA = profit before tax - other income + depreciation + interest (Screener's operating profit); total expenses = sales - EBITDA, and a check row confirms this equals the sum of Screener's individual cost lines.

## What the model does
| Sheet | Purpose |
|---|---|
| `Cover` | Scope, colour legend, data notes |
| `Historicals` | FY24 (15-month), FY25, FY26 P&L and balance sheet, linked to Raw_Data, with derived checks |
| `Drivers_Budget` | Back-tested FY26 budget: FY25 actual sales x (1 + 11% growth), 24% EBITDA margin |
| `VarianceAnalysis` | Budget vs actual with favourable/adverse flags, EBITDA bridge, flexed-budget expense split, cost-head drift vs FY25 |
| `FY27_Forecast` | Downside / Base / Upside scenarios (yellow cells editable) and a cross-check against reported H1 FY27 |
| `Dashboard` | KPI cards, four charts, takeaways that update from the model |
| `Raw_Data` | Unedited Screener export |

## Key results
- FY26 sales **+3.3%** (+Rs. 731 cr) vs budget; EBITDA **-1.4%** (-Rs. 75 cr); operating margin **22.9% vs 24.0%** budgeted.
- Bridge: **+Rs. 175 cr** growth effect and **-Rs. 250 cr** margin effect; reconciles to reported EBITDA.
- Expenses **+4.7%** over budget: Rs. 555 cr volume-driven (flexed budget), **Rs. 250 cr cost-ratio overrun**.
- Cost heads vs FY25 (share of sales): **materials** rose from 37.2% to 38.6% (-Rs. 341 cr of EBITDA at FY26 sales); employee cost, power and the balancing "other expenses" line offset part of it. Total expense ratio rose 0.7 pp.
- FY27 EBITDA: Rs. 5,400 cr (downside) / **Rs. 6,040 cr (base)** / Rs. 6,715 cr (upside).
- Forecast cross-check: H1 FY27 (Jun + Sep 2026 quarters) sales were +22.6% and EBITDA +35.2% on H1 FY26, margin 24.0%. H1 EBITDA is already **52% of the base case** (in FY26, H1 was about 44% of the full year), so the base case looks conservative against actuals.

## FY27 assumptions
| | Downside | Base | Upside |
|---|---|---|---|
| Revenue growth | 6.0% | 11.0% | 16.0% |
| Operating margin | 22.0% | 23.5% | 25.0% |

The scenarios were set from FY26 results, before the H1 FY27 actuals were considered, which is why the cross-check is useful. A rolling forecast (H1 actual + H2 estimate) would be the natural next step.

## Method notes
- Bridge: growth variance = (actual sales - budget sales) x budget margin; margin variance = (actual margin - budget margin) x actual sales.
- Flexed budget: budget cost ratio x actual sales separates volume-driven cost from genuine overrun.
- Cost-head drift: each Screener cost line as a % of sales, FY26 vs FY25, converted to Rs. crore at FY26 sales. Materials = raw material cost less change in inventory.
- FY24 is a 15-month transition period (fiscal year-end moved from December to March), so it is excluded from growth calculations.

## Limitations
- The FY26 budget is **back-tested from FY25 actuals**; it is not Nestlé India's internal budget (not public).
- Screener's "Other expenses" is a balancing line and can be negative, so it is not a true cost head.
- Share price in `Historicals` is a memo item and does not drive any calculation.

*Educational portfolio exercise, not investment advice.*
