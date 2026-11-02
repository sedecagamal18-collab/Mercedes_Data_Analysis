# 🚗 Mercedes-Benz Cars Data Analysis & Interactive Dashboard

An end-to-end Data Analytics project analyzing Mercedes-Benz vehicle specifications, pricing trends, and performance metrics. This repository covers the complete workflow—from raw data preprocessing and outlier handling to interactive visual analytics using Python and Plotly.

---

## 📌 Project Overview

The objective of this project is to explore key factors influencing secondhand and new Mercedes-Benz car prices, analyze vehicle efficiency metrics (mileage vs. price), and observe market distributions across models, fuel types, and transmission systems.

### **Key Highlights:**
* **Data Cleaning & Wrangling:** Handled missing values, removed duplicate records, standardized column names, and handled statistical outliers using IQR capping.
* **Interactive Dashboard:** Built interactive data visualizations and KPIs using **Plotly Express** and **Plotly Graph Objects**, exported as a standalone HTML dashboard (`dashboard.html`).

---

## 📊 Dataset Description

The dataset contains detailed technical and financial attributes for Mercedes-Benz cars:

| Attribute | Description |
| :--- | :--- |
| **Model** | Car model name (e.g., S-Class, C-Class, A-Class, GLC, CLA) |
| **Year** | Manufacturing year |
| **Price_Euro** | Price of the car in Euros (€) |
| **Mileage_km** | Odometer reading in kilometers |
| **Fuel_type** | Fuel variant (Petrol, Diesel, Hybrid, etc.) |
| **Transmission** | Gearbox type (Automatic vs. Manual) |
| **Engine_size_l** | Engine displacement capacity in Liters |
| **Horsepower** | Vehicle engine power output (HP) |
| **Previous_owners** | Number of past registered owners |

---

## 🛠️ Data Preprocessing & Cleaning Workflow

1. **Duplicate Elimination:** Filtered and dropped duplicate vehicle records to prevent skewness.
2. **Missing Value Imputation:**
   * **Categorical Data (`Fuel_type`, `Transmission`):** Imputed missing values using the **Mode**.
   * **Numerical Data (`Year`, `Price_Euro`, `Mileage_km`, etc.):** Imputed missing values using the **Median** to avoid bias from extreme values.
3. **Column Normalization:** Standardized column naming conventions and renamed `Price_eur` to `Price_Euro`.
4. **Outlier Treatment:** Applied **Interquartile Range (IQR) Capping** across numerical features (`float64`) to bound extreme lower/upper outliers without deleting valuable data points:
   $$LB = Q1 - 1.5 \times IQR$$
   $$UB = Q3 + 1.5 \times IQR$$

---

## 📈 Dashboard & Key Insights

The interactive dashboard consists of key performance indicators (KPIs) and analytical charts:

### **1. Key Performance Indicators (KPIs)**
* **Total Portfolio Value:** Sum of vehicle prices calculated across the cleaned dataset.
* **Average Mileage:** Average vehicle distance driven ($km$).
* **Average Previous Owners:** Mean owner count across all models.

### **2. Charts & Analytics**
* 📉 **Average Price Over Years (Line Chart):** Tracks valuation depreciation and price trends across manufacturing years.
* 📊 **Price Distribution by Model (Bar Chart):** Ranks models by total market value contribution.
* 🥧 **Transmission Types Breakdown (Pie Chart):** Percentage distribution between Automatic and Manual transmissions.
* 🍩 **Fuel Type Distribution (Donut Chart):** Visualizes the proportion of Petrol vs. Diesel vehicles.
* 🌌 **Price vs. Mileage Analysis (Scatter Plot):** High-dimensional scatter plot highlighting the inverse relationship between vehicle mileage and market price, segmented by car model.

---

## 💻 Tech Stack & Libraries

* **Language:** Python 3.x
* **Data Manipulation:** `pandas`
* **Data Visualization:** `plotly.express`, `plotly.graph_objects`, `matplotlib`, `seaborn`
* **Output Format:** Standalone Interactive HTML (`dashboard.html`)

---

## 📁 Repository Structure

```text
├── mercedes_cars.csv             # Raw / Cleaned dataset
├── mercedes_analysis.ipynb.ipynb       # Jupyter Notebook with complete analysis code
├── dashboard.html                # Interactive Plotly Dashboard
└── README.md                     # Project documentation
```

---

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/mercedes-data-analysis.git
   cd mercedes-data-analysis
   ```

2. **Install required packages:**
   ```bash
   pip install pandas matplotlib seaborn plotly
   ```

3. **View Dashboard:**
   Open `dashboard.html` in any modern web browser to interactively explore the visualizations.
