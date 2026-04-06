# On-Time Delivery Prediction

This application predicts whether a shipment will be delivered on time based on order details such as quantity, amount, shipping mode, region, and payment type.

## How to Use

1. Install the app and connect a warehouse.
2. The Streamlit interface opens with two tabs: **Single Prediction** and **Batch Prediction**.

### Single Prediction
Enter order details manually and click "Predict Delivery Status" to get a real-time prediction with probability scores.

### Batch Prediction (Data-Centric)
1. Go to the app **Settings** (gear icon) > **References** tab.
2. Grant SELECT access on your orders table (consumer_orders_table reference).
3. Optionally grant SELECT + INSERT access on a results table (consumer_results_table reference).
4. Return to the **Batch Prediction** tab, preview your data, and click **Run Batch Predictions**.
5. Download results as CSV or have them written to your results table.

## Required Table Schema

Your orders table must contain the following columns:

| Column | Type | Description |
|--------|------|-------------|
| ORDER_ITEM_QUANTITY | NUMBER | Number of items in the order |
| ORDER_ITEM_TOTAL_AMOUNT | FLOAT | Total monetary value of the order |
| ORDER_ITEM_DISCOUNT_RATE | FLOAT | Discount applied (0 to 1) |
| SALES | FLOAT | Total sales amount |
| PRODUCT_PRICE | FLOAT | Price of the product |
| ORDER_PROFIT_PER_ORDER | FLOAT | Profit generated from the order |
| SHIPPING_MODE | VARCHAR | Standard Class, First Class, Same Day, or Second Class |
| ORDER_REGION | VARCHAR | East, West, Central, or South |
| PAYMENT_TYPE | VARCHAR | Credit Card, Debit Card, COD, Net Banking, or UPI |
| CUSTOMER_CITY | VARCHAR | City of the customer |
| SHIPPING_WEEKDAY | NUMBER | Day of week (0=Monday, 6=Sunday) |

## Features

- Pre-trained Random Forest model for delivery prediction
- Single-order prediction with real-time probability scores
- Batch prediction against consumer's own Snowflake tables
- Results written back to consumer's Snowflake table
- CSV export of prediction results
- Interactive Streamlit interface with no external dependencies

## Requirements

- A Snowflake warehouse connected to the app
- For batch mode: an orders table matching the schema above
