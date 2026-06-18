# 🏪 Superstore Sales Analytics — Power BI Portfolio Project

## 📌 Project Overview
A full end-to-end retail analytics project built with **Power Query** and **Power BI**, analyzing 9,800+ rows of US Superstore sales data across 4 interactive dashboards. This project also includes Python EDA analysis as part of a multi-tool analytics approach.

---

## 📂 Dataset

| File | Rows | Description |
|------|------|-------------|
| train.csv | 9,800 | US Superstore Sales 2015-2018 |

**Source:** Kaggle Superstore Sales Dataset

---

## 🔧 Tools & Skills

- **Python (Pandas + Matplotlib + Seaborn)** — EDA & Visualization
- **Power Query** — Data cleaning, custom columns
- **Power BI** — Data modeling, DAX measures, interactive dashboards
- **DAX** — SUM, DISTINCTCOUNT, AVERAGE, DIVIDE, DATEADD
- **Navigation Page** — Bookmarks & Page Navigation buttons

---

## 🐍 Python EDA

Performed exploratory data analysis using Python before building the Power BI dashboard:
- Sales distribution by Category, Region, Segment, Sub-Category
- Monthly & Yearly sales trends
- Ship Mode distribution
- Days to Ship analysis
- Sales histogram and outlier detection

---

## 🧹 Data Cleaning (Power Query)

- Changed `Order Date` and `Ship Date` to Date type
- Changed `Sales` to Decimal Number
- Changed `Postal Code` to Whole Number
- Replaced null values in `Postal Code` with 0
- Applied Text.Trim to all text columns
- Removed errors
- Added calculated columns:
  - `Days to Ship` = Ship Date - Order Date
  - `Ship Speed` = Fast / Standard / Slow / Very Slow
  - `Sales Band` = Small / Medium / Large / Enterprise
  - `Order Year` = Year from Order Date
  - `Order Month` = Month from Order Date

---

## 🗂️ Data Model

- Date Table: 2015–2018
- Relationship: Date Table → train (Order Date)

---

## 📊 DAX Measures

```dax
Total Sales         = SUM('train'[Sales])
Total Orders        = DISTINCTCOUNT('train'[Order ID])
Total Customers     = DISTINCTCOUNT('train'[Customer ID])
Total Products      = DISTINCTCOUNT('train'[Product ID])
Avg Sales per Order = DIVIDE([Total Sales], [Total Orders])
Avg Days to Ship    = AVERAGE('train'[Days to Ship])
YoY Growth          = DIVIDE(CurrentYear - PrevYear, PrevYear) * 100
```

---

## 📈 Dashboards

### 🏠 Home (Navigation Page)
- 4 navigation buttons
- Dark theme (#0D1117)

### 📊 Sales Overview
- KPI Cards: Total Sales · Total Orders · Total Customers · Avg Sales per Order
- Sales by Category (Bar Chart)
- Sales by Region (Bar Chart)
- Sales by Segment (Pie Chart)
- Sales Trend by Month (Line Chart)
- Year Slicer (2015-2018)

### 👥 Customer Analytics
- KPI Cards: Total Customers · Total Sales · Avg Sales per Order
- Top 10 Customers by Sales (Bar Chart)
- Sales by Segment (Bar Chart)
- Sales by State (Map)
- Orders by Ship Mode (Bar Chart)
- Segment Slicer

### 🏷️ Product Analytics
- KPI Cards: Total Products · Total Sales
- Sales by Category (Bar Chart)
- Sales by Sub-Category (Bar Chart)
- Top 10 Products (Bar Chart)
- Sales Band Distribution (Pie Chart)
- Category Slicer

### 🚚 Shipping Analytics
- KPI Cards: Avg Days to Ship · Total Orders
- Orders by Ship Mode (Bar Chart)
- Avg Days to Ship by Mode (Bar Chart)
- Ship Speed Distribution (Pie Chart)
- Shipping Trend by Month (Line Chart)
- Ship Mode Slicer

---

## 💡 Key Business Insights

1. **West region leads in sales** — generating $0.71M, outperforming East ($0.67M), Central ($0.49M), and South ($0.39M).

2. **Consumer segment dominates** — accounting for $1.15M (51%) of total sales, followed by Corporate ($0.69M) and Home Office ($0.42M).

3. **Technology is the top category** — at $0.83M, slightly ahead of Furniture ($0.73M) and Office Supplies ($0.71M).

4. **Phones lead sub-categories** — at $0.33M, followed closely by Chairs ($0.32M).

5. **Standard Class is the most used shipping mode** — handling 2,945 orders (60%) but also the slowest at 5 days average.

6. **Same Day delivery is fastest** — averaging less than 1 day, while Standard Class averages 5 days.

7. **Average shipping time is 4 days** — indicating room for improvement in last-mile delivery efficiency.

8. **Zebra ZM400 Thermal Label Printer is the top product** — generating $7K in sales, significantly ahead of other products.

---

## 🧠 Lessons Learned

- CSV files require careful date format handling — using dayfirst=True in Python and Date type in Power Query.
- DISTINCTCOUNT is more accurate than COUNTROWS for Orders and Customers since one order can have multiple rows.
- YoY Growth DAX requires DATEADD function — only works correctly with a proper Date Table relationship.
- Python EDA before Power BI helps identify patterns and outliers before building dashboards.
- Navigation pages with Page Navigation buttons significantly improve dashboard professionalism.

---

## 👤 Author
**AbdelHassib Essayad**
Data Management Analyst & Accounting Specialist | 15+ Years Experience
Python · Power BI · Power Query · DAX · Retail Analytics

🔗 [GitHub Portfolio](https://github.com/hassib-essayad)
📧 essayad@gmail.com
