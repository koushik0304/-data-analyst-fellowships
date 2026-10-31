# Training Data Analysis

Summary of `TrainingData1.xlsx`, a retail sales dataset (Contoso / Adventure Works style).

## Dataset overview

- **Rows:** 15,000 orders
- **Columns:** 17
- **Date range:** 2011-12-06 to 2014-12-05
- **Data file:** [`TrainingData1.csv`](TrainingData1.csv)

### Columns

`Order ID`, `Order Date`, `Unit Cost`, `Price`, `Order Qty`, `Cost of Sales`, `Sales`, `Profit`, `Channel`, `Promotion Name`, `Product Name`, `Manufacturer`, `Product Sub Category`, `Product Category`, `Region`, `City`, `Country`

## Data quality

- No missing values
- No duplicate rows and no repeated Order IDs
- `Profit = Sales - Cost of Sales` holds for every row
- About 7,900 rows have `Sales != Price x Order Qty`, most likely due to promotional discounts

## Headline numbers

- **Total sales:** $55,391,760
- **Total cost of sales:** $23,804,323
- **Total profit:** $31,587,437 (57.0% margin)

### By channel

| Channel | Sales ($) | Profit ($) | Margin |
|---|---:|---:|---:|
| Store | 31,720,647 | 18,049,279 | 56.9% |
| Online | 11,500,207 | 6,529,717 | 56.8% |
| Reseller | 7,170,614 | 4,112,546 | 57.4% |
| Catalog | 5,000,291 | 2,895,895 | 57.9% |

### By region

| Region | Sales ($) | Profit ($) | Margin |
|---|---:|---:|---:|
| North America | 32,783,557 | 18,668,831 | 56.9% |
| Asia | 12,412,345 | 7,144,694 | 57.6% |
| Europe | 10,195,858 | 5,773,913 | 56.6% |

### By product category

| Product Category | Sales ($) | Profit ($) | Margin |
|---|---:|---:|---:|
| Computers | 21,306,971 | 12,162,419 | 57.1% |
| Cameras and camcorders  | 17,048,932 | 10,102,802 | 59.3% |
| TV and Video | 9,107,839 | 4,823,735 | 53.0% |
| Cell phones | 5,841,156 | 3,285,926 | 56.3% |
| Music, Movies and Audio Books | 1,057,480 | 635,285 | 60.1% |
| Audio | 1,029,381 | 577,270 | 56.1% |

## Usage

```python
import pandas as pd
df = pd.read_csv("TrainingData1.csv", parse_dates=["Order Date"])
```
