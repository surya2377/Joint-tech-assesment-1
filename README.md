# Predicting Product Demand in a Retail Store

A machine learning project that forecasts product demand for a retail store chain using historical sales data, pricing, promotions, and other contextual factors. Accurate demand forecasting helps optimize inventory management, reduce overstock, and improve promotion planning.

> Built as part of the **Joint Tech Internship Community Program — Assessment 1**.

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `predicting_product_demand.ipynb` | Main Jupyter notebook with the full analysis and modeling workflow |
| `product_demand_prediction_dataset.csv` | Dataset of 5,000 records of daily product sales across multiple stores |
| `Joint Tech Internship Community Program assesment 1.docx` | Assessment brief / problem statement |

## 📊 Dataset

Each row represents a product–store–date observation with the following features:

- **ProductID, StoreID, Date** — identifiers and time reference
- **Sales, Price, CompetitorPrice** — sales volume and pricing data
- **Promotion, Season, Holiday, DayOfWeek, Weather** — categorical/contextual factors
- **EconomicIndicator, StockLevel** — macro and inventory signals
- **Demand** — target variable to predict

## 🔍 Project Workflow

### Task 1 — Data Exploration & Preprocessing
- Load and inspect the dataset (summary statistics, data types)
- Detect and visualize missing values with a heatmap
- Impute missing values (median for numerical, most frequent for categorical)
- Encode categorical variables (One-Hot Encoding for Promotion, Season, Holiday, DayOfWeek, Weather; Label Encoding for ProductID and StoreID)

### Task 2 — Feature Engineering
- Standardize numerical features with `StandardScaler`
- Create new features:
  - **PriceChange** — difference between product price and competitor price
  - **Sales_MA7** — 7-day moving average of sales per product

### Task 3 — Model Building
- Train/test split (80/20)
- Train and compare multiple regression models:
  - Linear Regression
  - Decision Tree Regressor
  - Random Forest Regressor
  - Gradient Boosting Regressor

### Task 4 — Model Evaluation
Models are evaluated using:
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

### Task 5 — Insights & Recommendations
- Pricing, promotions, and seasonality significantly influence demand
- Competitor pricing and economic conditions also play a key role
- Recommendations include dynamic pricing, strategically timed promotions, and competitor price monitoring

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook / JupyterLab

### Installation

```bash
# Clone the repository
git clone https://github.com/surya2377/Joint-tech-assesment-1.git
cd Joint-tech-assesment-1

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Usage

1. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
2. Open `predicting_product_demand.ipynb`
3. Update the dataset path in the first code cell to point to the local CSV:
   ```python
   df = pd.read_csv('product_demand_prediction_dataset.csv')
   ```
4. Run all cells in order.

## 🛠️ Tech Stack

- **Python** — core language
- **pandas / NumPy** — data manipulation
- **Matplotlib / Seaborn** — visualization
- **scikit-learn** — preprocessing, modeling, and evaluation

## 📄 License

This project was created for educational purposes as part of an internship assessment.
