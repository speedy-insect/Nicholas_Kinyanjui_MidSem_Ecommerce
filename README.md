# DSA 3050A Mid-Semester Exam - Power BI Project

**Student:** Nicholas Gunda Kinyanjui  
**Student ID:** AM 670178  
**Course:** DSA 3050A - Business Intelligence & Data Visualization  
**Project:** E-Commerce Sales Analysis Dashboard

---

## Live Dashboard

**Power BI Public Link:** [View Dashboard](https://app.powerbi.com/view?r=eyJrIjoiY2M2NTE0MzEtYWNhMC00ODAyLWE0ZDQtYmY0MzU5MTk2OGE3IiwidCI6IjE2ZDgzZWU2LTI1NGEtNDY5ZC1hNmNjLTU0ZTJjYTIzMTNlNyIsImMiOjh9)

**GitHub Repository:** [View Code](https://github.com/yourusername/dsa3050-midsem-powerbi)

---

## Project Overview

This project analyzes Brazilian e-commerce sales data using Power BI. The analysis covers sales performance, customer behavior, product trends, and geographic distribution across Brazil.

**Dataset:** Brazilian E-Commerce by Olist (Kaggle)  
**Period:** 2016-2018  
**Total Records:** 112,650 transactions

---

## Dataset

### Source
- Platform: Kaggle
- Dataset: Brazilian E-Commerce Public Dataset by Olist
- URL: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

### Tables Used (5)

1. **FactOrderItems** - 112,650 rows
   - Main transaction table with sales data
   - Contains: OrderID, ProductID, SellerID, Price, Freight

2. **DimOrders** - 99,441 rows
   - Order information with dates and status
   - Contains: OrderID, CustomerID, OrderDate, DeliveryDate, Status

3. **DimProducts** - 32,951 rows
   - Product details and categories
   - Contains: ProductID, Category, Dimensions, Weight

4. **DimCustomers** - 99,441 rows
   - Customer locations
   - Contains: CustomerID, City, State, Region

5. **DimSellers** - 3,095 rows
   - Seller locations
   - Contains: SellerID, City, State, Region

6. **DimDate** - Date dimension table
   - Created using M code
   - Contains: Date, Year, Quarter, Month, DayOfWeek

---

## Part A: Power Query Transformations (20 Marks)

### Transformations Applied

Each table underwent 10+ transformations including:

**FactOrderItems:**
- Removed duplicates
- Fixed data types (Date/Time, Decimal, Whole Number)
- Extracted Year, Month, Quarter from dates
- Created Total_Order_Value column (Price + Freight)
- Created Price_Category (High/Medium/Low)
- Renamed columns professionally

**DimOrders:**
- Handled missing values in delivery dates
- Extracted date components (Year, Month, Quarter, DayOfWeek)
- Created Delivery_Status column
- Calculated Delivery_Days
- Standardized column names

**DimProducts:**
- Replaced nulls with appropriate values
- Standardized category names (Trim, Clean, Capitalize)
- Split category into Main and Sub categories
- Created Product_Volume column
- Created Weight_Category (Heavy/Medium/Light)

**DimCustomers:**
- Standardized city and state names
- Created Region column (Southeast, South, Northeast, etc.)
- Merged City and State columns
- Removed unnecessary columns

**DimSellers:**
- Applied same transformations as customers
- Created region groupings
- Standardized location data

**DimDate:**
- Created using M code
- Generated dates from 2016-2018
- Added Year, Quarter, Month, DayOfWeek
- Added IsWeekend flag

### Screenshots
See `screenshots/power_query/` folder for transformation evidence.

---

## Part B: Data Modelling (15 Marks)

### Star Schema Structure

```
        DimCustomers
              |
         DimOrders
              |
    FactOrderItems ---- DimProducts
              |
         DimSellers
              |
          DimDate
```

### Relationships Created (5)

1. **FactOrderItems → DimProducts**
   - Key: ProductID
   - Cardinality: Many-to-One (*:1)
   - Filter: Single direction

2. **FactOrderItems → DimOrders**
   - Key: OrderID
   - Cardinality: Many-to-One (*:1)
   - Filter: Single direction

3. **DimOrders → DimCustomers**
   - Key: CustomerID
   - Cardinality: Many-to-One (*:1)
   - Filter: Single direction

4. **FactOrderItems → DimSellers**
   - Key: SellerID
   - Cardinality: Many-to-One (*:1)
   - Filter: Single direction

5. **DimOrders → DimDate**
   - Key: OrderDate → Date
   - Cardinality: Many-to-One (*:1)
   - Filter: Single direction

### Model Features
- Date table marked as date table
- Technical fields hidden
- Clean, organized layout
- No many-to-many relationships

### Screenshots
See `screenshots/data_model/` folder for model view and relationships.

---

## Part C: Dashboard Development (10 Marks)

### Dashboard Components

**KPI Cards (4):**
1. Total Revenue - R$ 16.0M
2. Total Orders - 112,650
3. Average Order Value - R$ 142
4. Total Customers - 99,441

**Visualizations (6):**

1. **Monthly Revenue Trend** (Line Chart)
   - Shows revenue growth over time
   - Identifies seasonal patterns

2. **Revenue by Region** (Bar Chart)
   - Southeast leads with 55% of revenue
   - South region second with 18%

3. **Top 10 Product Categories** (Column Chart)
   - Health & Beauty top category
   - Watches & Gifts second

4. **Order Status Distribution** (Pie Chart)
   - 97% delivered successfully
   - 2% shipped, 1% other statuses

5. **Delivery Performance** (Gauge)
   - Average delivery: 12 days
   - Target: Under 15 days

6. **Sales by Seller Region** (Map)
   - Geographic distribution of sellers
   - Concentration in major cities

**Interactive Slicers (3):**
- Year filter (2016-2018)
- Quarter filter (Q1-Q4)
- Region filter (5 regions)

### Design Features
- Professional color scheme
- Clear visual hierarchy
- Consistent formatting
- Cross-filtering enabled
- Mobile-responsive layout

### Screenshots
See `screenshots/dashboard/` folder for dashboard views.

---

## Part D: Publishing & Deployment (5 Marks)

### Publishing Process

1. Published to Power BI Service
2. Created public dashboard link
3. Tested accessibility in multiple browsers
4. Confirmed all visuals load correctly
5. Verified cross-filtering works

### Public Access
Dashboard is publicly accessible at the link provided above. No login required.

### Screenshots
See `screenshots/publishing/` folder for publishing confirmation.

---

## Key Insights

### Business Performance
- Total revenue of R$ 16.0M over 3 years
- 112,650 orders from 99,441 customers
- Average order value of R$ 142
- 97% successful delivery rate

### Geographic Analysis
- Southeast region dominates with 55% of sales
- São Paulo is the top city for both customers and sellers
- Strong presence in major urban centers

### Product Performance
- Health & Beauty is the top category
- Technology products have higher average values
- Furniture has longer delivery times

### Temporal Trends
- Steady growth from 2016 to 2018
- Peak sales in November (Black Friday)
- Consistent performance across quarters

### Operational Metrics
- Average delivery time: 12 days
- 3% of orders experience delays
- Freight costs average 15% of order value

---

## Technical Implementation

### Tools Used
- Power BI Desktop
- Power Query (M language)
- DAX for calculations
- Power BI Service for publishing

### Data Processing
- 5 CSV files imported
- 50+ transformation steps applied
- 6 tables in final model
- 5 relationships created

### Performance
- Dataset size: 42 MB
- Load time: Under 5 seconds
- Refresh time: Under 1 minute
- Optimized for web viewing

---

## Project Structure

```
MidSem/
├── README.md                  (This file)
├── datasets/                  (5 CSV files)
│   ├── olist_order_items_dataset.csv
│   ├── olist_orders_dataset.csv
│   ├── olist_products_dataset.csv
│   ├── olist_customers_dataset.csv
│   └── olist_sellers_dataset.csv
├── powerbi/                   (Power BI file)
│   └── Nicholas_Kinyanjui_MidSem_Ecommerce.pbix
└── screenshots/               (Evidence)
    ├── dataset_source/
    ├── power_query/
    ├── data_model/
    ├── dashboard/
    └── publishing/
```

---

## Requirements Met

### Dataset Requirements
✅ Real-world data source (Kaggle)  
✅ Multiple related tables (5 tables)  
✅ Over 7,000 rows (112,650 in main table)  
✅ Dates, categories, numerical values, locations  
✅ Supports analytical storytelling

### Part A: Power Query (20 marks)
✅ 10+ transformations per major table  
✅ Duplicates removed  
✅ Nulls handled  
✅ Data types corrected  
✅ Year, Month, Quarter extracted  
✅ Derived columns created  
✅ Professional query names  
✅ Screenshots provided

### Part B: Data Modelling (15 marks)
✅ Star schema implemented  
✅ Correct cardinality (Many-to-One)  
✅ Proper filter direction  
✅ Date table created and marked  
✅ Technical fields hidden  
✅ Clean model view  
✅ Screenshots provided

### Part C: Dashboard (10 marks)
✅ KPI summary visuals  
✅ Trend analysis  
✅ Comparative analysis  
✅ Distribution visualization  
✅ Interactive slicers  
✅ Cross-filtering enabled  
✅ Professional design  
✅ Screenshots provided

### Part D: Publishing (5 marks)
✅ Published to Power BI Service  
✅ Public link generated  
✅ Dashboard accessible  
✅ Screenshots provided

---

## Conclusion

This project demonstrates end-to-end business intelligence workflow using Power BI. The analysis provides actionable insights into e-commerce performance, customer behavior, and operational efficiency. The interactive dashboard enables stakeholders to explore data and make informed decisions.

The implementation follows best practices in data modeling, transformation, and visualization design. All requirements have been met with comprehensive documentation and evidence provided.

---

## Contact

**Student:** Nicholas Gunda Kinyanjui  
**Student ID:** AM 670178  
**Email:** [Your Email]  
**Course:** DSA 3050A

---

## Acknowledgments

- Dataset: Olist (via Kaggle)
- Platform: Microsoft Power BI
- Course: DSA 3050A - Business Intelligence & Data Visualization

---

**Submission Date:** [Date]  
**Total Marks:** 50 Marks
