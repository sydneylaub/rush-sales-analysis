# RUSH Sportswear — US Sales Analysis

Analysis of RUSH retail sales data for 2020–2021, prepared for the VP of US
Sales. Covers data cleaning, four requested business questions, and
additional findings on growth composition and seasonality.

**Author:** Sydney Laub
**Course:** GB885, M.S. Data, Insights and Analytics — UW–Madison

## Business Context

RUSH is a global sportswear and footwear brand. The VP of US Sales
requested an analysis of retail sales data to identify trends and growth
opportunities, along with answers to four specific questions:

- Which product category had the highest dollar sales in 2021?
- Which state had the highest dollar sales of women's products in 2021?
- Which state had the highest dollar sales of men's products in 2021?
- Which retailer purchased the most units in 2021? In 2020?

## Data

Three raw tables, committed to this repository and read directly by the
notebook over HTTPS:

| File | Contents | Rows |
|---|---|---|
| `TABLE_SALES_885.csv` | One row per order — units, price, margin, sales method | 9,648 |
| `TABLE_RETAILER_885.csv` | Retailer locations — region, state, city | 110 |
| `TABLE_PRODUCTS_885.csv` | Product category names (pipe-delimited) | 6 |

The data is unvalidated and required cleaning before analysis. Nine quality
issues were identified and documented in the notebook, including a
non-unique primary key in the retailer table that inflates the record count
by 622 rows if joined without correction.

Revenue is not a field in the source data; it is derived as
`PRICE_PER_UNIT × UNITS_SOLD`.

## Key Findings

- **Men's Street Footwear** led 2021 with $22.6M in revenue
- **Maine** and **Delaware** led women's and men's sales by state respectively
- **Foot Locker** purchased the most units in 2021; **Amazon** in 2020, from
  a smaller field of four retailers
- Revenue grew from $24.2M to $95.9M, but **78% of that growth came from two
  new retail partners**. Like-for-like growth among retailers present in both
  years was 65%
- 2021 revenue was strongly seasonal, peaking in July and December and
  troughing in March

## How to Run It

Open `rush_sales_analysis.ipynb` in [Google Colab](https://colab.research.google.com/)
and select **Runtime → Restart and run all**. No setup or credentials are
required — the notebook reads its data directly from this repository.

To run locally:

```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook rush_sales_analysis.ipynb
```

Cells are written to run in order, top to bottom.

## Repository Structure
├── README.md
├── .gitignore
├── rush_sales_analysis.ipynb
├── TABLE_SALES_885.csv
├── TABLE_RETAILER_885.csv
└── TABLE_PRODUCTS_885.csv

## Built With

Python · pandas · NumPy · matplotlib · seaborn · Google Colab
