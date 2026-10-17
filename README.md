# Shipment Volume Forecasting & Truck Planning Model

Analysis of daily shipment volume with a simple forecast and a truck planning model that flags days for adhoc truck booking or cancellation of an extra truck.

## Dataset
"DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS" on Kaggle (uploaded by Shashwat Tiwari), grouped to one row per order. The dataset is not included in this repo; download it from Kaggle.

## Key results
- 1,127 days of order data, averaging about 58 orders per day, with a peak of 69.
- Weekday volumes are nearly flat (about 58.2 to 58.6 orders on every weekday), so there is no strong weekday pattern.
- A 7-day moving-average forecast (on units, using only past days) has a Mean Absolute Percentage Error (MAPE) of 9.3%.

## Truck planning model
- **Assumption:** each truck carries 200 units. This is my assumption and is not from the dataset.
- Baseline plan: 2 trucks per day (based on average daily units).
- Trucks needed each day = forecast units divided by capacity, rounded up.
- Result: 45 days flagged for a potential adhoc truck, 117 days for potential cancellation of an extra truck, and 958 days within plan.

## Files
- `truck_planning_model.ipynb`: analysis and model in Python (pandas)
- `truck_planning.xlsx`: daily forecast, trucks needed vs planned, and action flag

## Limitations
- A simple moving average does not capture trend or seasonality; it is meant as an explainable baseline.
- Capacity and baseline are illustrative, so the flags show the method rather than real network decisions.

## Tools
Python (pandas, NumPy), Excel
