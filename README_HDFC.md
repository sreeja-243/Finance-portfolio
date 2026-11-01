# HDFC Bank: Excess Return Valuation with DDM Cross-Check

[Back to portfolio](README.md) | **Workbook:** [hdfc_valuation_model.xlsx](hdfc_valuation_model.xlsx) | **Raw data:** [Raw_Data_HDFC_Bank.xlsx](Raw_Data_HDFC_Bank.xlsx)
**Company:** HDFC Bank Ltd (consolidated) | **Data:** Screener.in Excel export, Nov 2026 | **Units:** Rs. crore; per-share in Rs.

## Objective
Value a bank with a method that suits banks. Free cash flow is not economically meaningful when interest is core to operations, so this uses the **Excess Return (residual income) Model**, with a **Dividend Discount Model** cross-check that reconciles to it.

## Data
The `Raw_Data` sheet is the unedited Screener export (identical to the separate raw file in this repo). Every figure on `Historicals` links to it: revenue, interest, expenses, other income, profit before tax, net profit, equity, dividend payout (dividend / net profit), shares and price. A check row confirms the P&L reconciles to profit before tax.

## What the model does
| Sheet | Purpose |
|---|---|
| `Cover` | Scope, legend, sources |
| `Historicals` | FY22 to FY26 P&L and equity, linked to Raw_Data, with ROE, tax rate and book value per share computed |
| `Assumptions` | CAPM cost of equity, ROE path, payout, terminal growth (yellow = editable) |
| `ExcessReturnModel` | 5-year projection, terminal value, intrinsic value per share |
| `DDM_CrossCheck` | 2-stage DDM on the same path, with a reconciliation check |
| `Summary` | Value vs price, P/B, and a 5 x 5 sensitivity grid that re-runs the full model |
| `Raw_Data` | Unedited Screener export |

## Key assumptions
| Input | Value |
|---|---|
| Risk-free rate (10-yr G-Sec) | 6.8% |
| Beta (assumed; an observed 5-yr beta of 0.42 was found unusually low) | 0.90 |
| Equity risk premium | 6.5% |
| **Cost of equity** | **12.65%** |
| FY26 ROE, computed on average equity | 13.7% |
| ROE path, Yr 1 to 5 | 14.0% rising to 15.0% |
| Payout, explicit period (FY26 actual 31.4%) | 30% |
| Terminal growth | 5.5% |
| Terminal payout = 1 - g / ROE | 63.3% |
| Starting book value per share (equity / shares) | Rs. 380.72 |

## Key results
- Intrinsic value: **Rs. 523 per share** vs market price **Rs. 692.80** (Screener export, Nov 2026): **-24.5%**.
- Market P/B **1.82x** vs 1.37x supported by the model.
- **DDM = excess return value, exactly.** This holds only when terminal payout is consistent with growth (1 - g/ROE), which is the main modelling insight.
- Sensitivity grid (cost of equity 11.65% to 13.65%, growth 4.5% to 6.5%): Rs. 443 to Rs. 660; **no cell reaches the market price**. The result is driven mainly by cost of equity and the ROE recovery path.

## Method notes
- Excess return in year t = (ROE - Ke) x opening book value. Terminal excess return uses Year 6 book value, so it is not understated while book value still grows about 10% a year.
- Each sensitivity cell recomputes the full 5-year model for that Ke and g; the centre cell equals the headline value (a check cell confirms this).
- Net profit is Screener's reported figure (after minority interest), consistent with equity excluding minority interest.

## Limitations
- Beta of 0.90 is my assumption; changing it moves the result materially.
- FY24 onward reflects the HDFC Ltd merger (effective 1 Jul 2023), so FY24 is not comparable with FY22/FY23.
- Screener groups bank costs into generic lines, so "expenses" include provisions and are not net interest income.
- The risk-free rate and beta come from public sources noted on the Assumptions sheet and are not part of the raw export.

*Educational portfolio exercise, not investment advice or a price target.*
