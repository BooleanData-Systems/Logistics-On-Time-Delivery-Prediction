# On-Time Delivery Prediction

This application predicts whether a shipment will be delivered on time based on order details such as quantity, amount, shipping mode, region, and payment type.

## How to Use

1. Connect a warehouse to the app.
2. The Streamlit interface opens automatically.
3. Enter order details and click "Predict Delivery Status".
4. View the prediction result and probability scores.

## Input Features

| Feature | Description |
|---------|-------------|
| Shipping Day | Day of the week the shipment is sent |
| Order Item Quantity | Number of items in the order |
| Order Item Total Amount | Total monetary value of the order |
| Discount Rate | Discount applied to the order (0 to 1) |
| Sales | Total sales amount |
| Product Price | Price of the product |
| Order Profit per Order | Profit generated from the order |
| Shipping Mode | Standard Class, First Class, Same Day, or Second Class |
| Order Region | East, West, Central, or South |
| Payment Type | Credit Card, Debit Card, COD, Net Banking, or UPI |
| Customer City | City of the customer |

## Features

- Random Forest model for delivery prediction
- Real-time probability scores with on-time and delay percentages
- Supports multiple shipping modes, regions, and payment types
- Interactive Streamlit interface — no setup or external tools required
- Fully operational after installation with a pre-trained model

## Requirements

- A Snowflake warehouse connected to the app
