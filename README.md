### Smart Price Optimization

**Overview**

Retailers often struggle to decide the right price for their products:

If the price is too high → sales drop

If the price is too low → sales rise but profits drop

👉 This project builds a Machine Learning–based Smart Price Optimization system that finds the sweet spot:
the price that maximizes revenue (and profit) while staying competitive.

We used XGBoost on historical sales data to predict demand at different prices and recommend the optimal one.

**Dataset**

Dataset: Online Retail II (UCI ML Repository)
###  Download Full Dataset
You can download the full datasets from here:  
- [Google Drive Link to Raw Data]- [(http://bit.ly/4gNZCAE)]
- [Google Drive Link to Cleaned Data]- [(https://bit.ly/4gRcbLD)]

 **Usage**
After downloading, place the files inside the `data/` folder:

### Features include:

Product ID (StockCode)

Invoice date

Unit price

Quantity

Revenue

Customer ID

Country

### Competitor Price Data

This project includes a simulated competitor price dataset (data/competitor_price.csv) to demonstrate how external market signals can be integrated into the pricing model.

File Location: data/competitor_price.csv

Note: These competitor prices are synthetically generated (using random variations of our product prices) and do not represent real retailer data.

Purpose: To show how the model could incorporate competitor prices in real-world deployments.

In a real retail environment, competitor prices can be obtained via:

1.APIs from pricing intelligence providers
2.Web scraping (with ethical & legal considerations)
3.Retail partnerships with shared pricing feeds



### Installation & Setup

1. Clone this repo
git clone https://github.com/your-username/smart-price-optimization.git
cd smart-price-optimization

2. Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate    # Mac/Linux
venv\Scripts\activate       # Windows

3. Install dependencies
pip install -r requirements.txt

 **How to Run**
1. Jupyter Notebook

Run the pipeline step by step:

jupyter notebook Smart_Price_Notebook.ipynb


**Steps covered:**

Data loading & preprocessing

Feature engineering (lags, competitor prices, clustering, holiday flags, etc.)

Train/Test split

Model training (XGBoost vs Baseline)

Price recommendation function

KPI evaluation (profit & revenue uplift)

Backtest reports



**Pretrained Model**

We’ve included a ready-to-use model inside the models/ folder:

xgb_qty_model.joblib → trained XGBoost model

feature_columns.pkl → feature column order for predictions

✅ This means you can test recommendations without retraining.

**Load like this:**

import joblib

model = joblib.load("models/xgb_qty_model.joblib")
feature_columns = joblib.load("models/feature_columns.pkl")


**Backtest Reports**

Generated reports are available in the reports/ folder:

business_kpi_full_backtest.csv

business_kpi_profit_backtest.csv

These show actual vs recommended prices, revenue, and profit uplift.
 Ready to load into Power BI / Excel for dashboards.

**Future Improvements**

Replace simulated competitor price with real APIs (e.g., PriceAPI, DataWeave)

Add profit margin optimization (currently revenue-first)

Build interactive dashboard (Streamlit/Power BI) for managers

Scale to real-time pricing system

 **Acknowledgements**

Dataset: UCI ML Repository – Online Retail II

Libraries: Pandas, NumPy, Scikit-learn, XGBoost, Matplotlib

With this project, retailers can stop guessing prices and start making data-driven pricing decisions.
