# Amazon Product Analytics | Exploratory Data Analysis

![Category distribution](figures/01_categories.png)

## Overview
Reproducible exploratory analysis of a public Amazon India product/review dataset (1,465 rows, 16 original columns). Prices are in Indian rupees (INR). **This is product listing data, not transaction or revenue data.**

## Questions
- Which main categories have the most listed products?
- How are discounted prices distributed?
- How do median discounts differ by category?
- Is there an association between discounted price and product rating?

## Reproduce
```bash
pip install -r requirements.txt
python src/analysis.py
```
Or open `notebooks/amazon_eda.ipynb` in Google Colab and upload `amazon.csv` when prompted.

## Key results (observed on supplied dataset)
- Rows: 1465 Unique product IDs: 1351
- Missing numerical fields: {'actual_price': 0, 'discounted_price': 0, 'discount_percentage': 0, 'rating': 1, 'rating_count': 2}
- Median discounted price INR: 799.0
- Median discount %: 50.0
- Mean rating: 4.096584699453552
- Pearson price/rating: 0.12033741712288648
- Air conditioner rows: 1 mean discounted INR: 42990.0

## Figures
![Prices](figures/02_prices.png)
![Price and rating](figures/03_price_rating.png)
![Discounts](figures/04_discounts.png)

## Limitations
- Convenience sample of product listings; not representative of all Amazon sales.
- The same product may appear in multiple rows; counts reflect rows, not necessarily distinct products.
- Correlation does not imply causation.
- Missing or invalid numeric values are coerced to NaN.
- Source review fields can contain personal identifiers; do not use them for profiling.

## Dataset credit
Kaggle: [Amazon Sales Dataset by Karkavelrajaj](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset). Check the source's terms before redistributing the original data.

## Stack
Python · Pandas · NumPy · Matplotlib · Jupyter
