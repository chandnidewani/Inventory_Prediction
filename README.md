# Inventory Sales Forecasting using Machine Learning

## Project Overview
This project focuses on optimizing inventory levels for **ABC**, a South American grocery retail firm. The objective is to improve product availability and minimize wastage by predicting sales using machine learning techniques. The dataset consists of sales records for 33 products across 54 stores, covering **January 1, 2013 to August 15, 2017**.

## Dataset Overview
- **Stores**: 54  
- **Products**: 33  
- **Date Range**: 01-Jan-2013 to 15-Aug-2017  
- **Attributes**:
  - Date
  - Store Number
  - Product Type
  - Sales
  - Special Offer

---

## Key Highlights

### Data Preprocessing & Feature Engineering
- **Lag Features**: Year-over-Year lagged sales (`lag_yoy_sales`)
- **Cluster-Based Features**:
  - Monthly & daily sales clusters
  - Special offer sensitivity clusters
  - Store sales clusters
- **Additional Features**:
  - Day of Week (Dow)
  - Month & Year indicators
- **Outlier Removal**: Based on excessive monthly sales spikes
- **Product-Specific Filtering**: Data trimmed post-July 2015 for stability

---

### Exploratory Data Insights
- **Seasonality**: Higher sales on weekends and start of the month
- **Festive Season Impact**: Noticeable spikes in May & December
- **Product Contribution**: Top 5 products account for over 80% of total sales
- **Store Variability**: Variations in store opening dates
- **Special Offer Effectiveness**: Selective impact observed across products

---

## Modeling Approach

### Custom Preprocessing & Feature Engineering
All preprocessing steps, including clustering, outlier removal, and feature creation, are handled within a single Jupyter Notebook.

### Custom Time Series Cross-Validation & Hyperparameter Tuning
A custom grid search methodology was implemented to handle time-series nature of the data, preventing data leakage and preserving sequence integrity.

### Algorithms Tested
- Random Forest Regressor
- XGBoost Regressor
- LightGBM Regressor

**Evaluation Metric**: Negative Root Mean Squared Error (`neg_root_mean_squared_error`)

---

## Final Model Details
- **Model Chosen**: XGBoost Regressor
- **Approach**: One model trained per product (due to varying sales patterns)
- **Forecast Period**: 01-Aug-2017 to 16-Aug-2017 (16 days ahead)
- **Features Used**:
  - Year
  - Month
  - Day of Week
  - lag_yoy_sales
  - relative_monthly_sales_cluster
  - relative_daily_sales_cluster
  - relative_monthly_offer_cluster
  - relative_store_cluster

---

## Performance Evaluation
- Accurate predictions on high-selling products
- Improved inventory balance with reduced wastage and stockouts
- Visual comparison of predictions vs actual sales trends

---

## Challenges & Future Work
- Adapting model to new product/store introductions
- Incorporating external variables (holidays, economic conditions)
- Setting up continuous retraining pipelines for evolving patterns

---

## Repository Structure
```
├── Inventory Prediction Model.ipynb   # Main notebook (EDA, preprocessing, modeling)
├── README.md                 # Project documentation
```

---

## How to Run
Open the Jupyter Notebook and run all cells:
   ```
   jupyter notebook Inventory Prediction Model.ipynb
   ```

---

## License
*For academic use only.*
