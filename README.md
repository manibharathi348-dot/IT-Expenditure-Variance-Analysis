# IT Expenditure Variance Analysis

An Excel workbook that compares IT spending (**Actual**) against **Forecast** and **Plan** for a full year. It breaks the variance down by month, business area, country, IT area, and cost element.

All results use live Excel formulas (`SUMIFS`), so the analysis updates when the source data changes.

## Contents

| File | Description |
|------|-------------|
| `IT Expenditure Variance Analysis.xlsx` | The workbook: source data and variance analysis |
| `README.md` | This file |

## Workbook Structure

| Sheet | Rows | Description |
|-------|------|-------------|
| `Data` | 81,610 | Transaction lines for Jan–Dec with `Actual`, `Forecast`, and `Plan` amounts |
| `Future Data` | 12,119 | Additional `Actual` lines for Sep–Dec |
| `Variance Analysis` | — | Summary tables built with formulas from the two data sheets |

### Data Columns

| Column | Description |
|--------|-------------|
| `Date` | Month (`Jan` – `Dec`) |
| `Business Area` | 7 areas, e.g. R&D, Distribution, Manufacturing, Services |
| `Region` | 6 regions, e.g. Europe, USA, Latin America, Aus and NZ |
| `Country` | Country of the cost |
| `IT Area` / `IT Sub Area` | IT function, e.g. BU Support, Governance, Infrastructure |
| `Cost element name` | Detailed cost line, e.g. Contractors, Travel Expense |
| `Cost Element Group` / `Sub Group` | Cost category, e.g. Labor, Hardware & Software, Shared Services |
| `Actual` | Actual spend |
| `Forecast` | Forecast spend (`Data` sheet only) |
| `Plan` | Planned budget (`Data` sheet only) |

## Analysis

The `Variance Analysis` sheet contains:

1. **Full-year results:** total Actual, Plan, variance, and variance %
2. **Monthly comparison:** Jan–Dec with a full-year total
3. **By Business Area**
4. **By Country**
5. **By IT Area**
6. **By Cost element name**

Each breakdown table shows these columns:

| Column | Formula |
|--------|---------|
| Actual | `Data` Actual + `Future Data` Actual |
| Forecast | `Data` Forecast |
| Plan | `Data` Plan |
| Actual vs Plan | `Actual − Plan` |
| Actual variance % | `(Actual − Plan) / ABS(Plan)`, or `n.m.` when Plan is 0 |
| Forecast vs Plan | `Forecast − Plan` |

## How to Read the Results

- **Positive variance:** Actual is **above** Plan (overspend).
- **Negative variance:** Actual is **below** Plan (underspend).
- **`n.m.`** (not meaningful) appears when Plan is zero.
- Some lines are negative (credits or allocations). Review these separately.
- Amounts are in the source units, with no currency conversion.

## How to Use

1. Download `IT Expenditure Variance Analysis.xlsx`.
2. Open it in Microsoft Excel (or another spreadsheet app that supports `SUMIFS`).
3. Go to the `Variance Analysis` sheet to see the results.
4. To update the analysis, paste new rows into `Data` or `Future Data` with the same columns. If you add rows past the current range (row 81,611 in `Data`), extend the formula ranges.

## Tools Used

- Microsoft Excel: `SUMIFS`, `SUM`, `IF`, `ABS`

## Author

Manibharathi T
