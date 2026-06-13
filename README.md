# Sales & Customer Analytics Dashboard | Tableau 📊

A dynamic, interactive dual-dashboard Tableau report built to help 
sales and marketing stakeholders track, compare, and act on 
year-over-year business performance — across KPIs, product 
subcategories, weekly trends, and customer-level insights.

The Sales & Customer Analytics Dashboard is a visually engaging 
analytical tool designed to give users a complete picture of business 
performance for any selected year vs. the prior year. Powered by a 
single **dynamic year parameter**, both dashboards update simultaneously 
— eliminating the need to rebuild views for each reporting period. The 
tool covers 6 core KPIs, subcategory-level profitability analysis, 
weekly trend anomaly detection, and customer loyalty segmentation. It 
is intended for use by sales managers, marketing strategists, and 
data analysts who need to monitor performance and identify 
opportunities through an interactive, self-serve interface.

---

## Tools & Technologies

- 📊 **Tableau Desktop** — Primary data visualization and dashboard 
  platform
- 🧮 **Tableau Calculated Fields** — CY/PY logic, % difference 
  measures, Min/Max window functions, KPI avg comparisons, and LOD 
  expressions for fixed customer-order counts
- 🎛️ **Tableau Parameters** — A single `Select Year` parameter 
  dynamically drives all CY and PY calculations across both dashboards
- 📂 **Data Source** — `Sales DataSource` (single flat table embedded 
  in the `.twbx`)
- 📁 **File Format** — `.twbx` for development and distribution; 
  `.png` for dashboard previews

---

## Data Source

- **Source:** Sales DataSource (CSV/extract embedded in workbook)
- **Coverage:** Multi-year transactional sales data (selectable year 
  range via parameter)
- **Fields include:** Order ID, Order Date, Ship Date, Ship Mode, 
  Customer ID, Customer Name, Segment, City, State, Region, Product 
  ID, Product Name, Category, Sub-Category, Sales, Quantity, Discount, 
  Profit

---

## Dashboard Views

### 1. Sales Dashboard
Year-over-year sales performance overview:

- **6 KPI Summary Tiles** — Sales, Profit, Quantity, Customers, 
  Orders, and Sales Per Customer; each showing CY value, PY value, 
  and % difference with directional indicators
- **Monthly Trend Sparklines** — Each KPI plotted month-by-month for 
  CY and PY, with highest and lowest months dynamically highlighted 
  using Min/Max window calculations
- **Subcategory Comparison Chart** — Dual bar chart comparing CY vs. 
  PY Sales and Profit across all product subcategories, with a legend 
  distinguishing above/below threshold performance
- **Weekly Trends Chart** — Sales and profit plotted week-by-week for 
  the current year with a dynamic average reference line; weeks above 
  and below average are color-coded for instant anomaly detection

### 2. Customer Dashboard
Customer behavior and loyalty analysis:

- **6 KPI Summary Tiles** — Same KPI set as Sales Dashboard, 
  maintaining consistency across both views
- **Customer Distribution Histogram** — Customers segmented by number 
  of orders placed, revealing loyalty tiers and repeat purchase 
  behavior (powered by a FIXED LOD expression)
- **Top 10 Customers Table** — Ranked by profit, showing each 
  customer's order count, total sales, and last order date — enabling 
  targeted relationship management and retention strategy

---

## Features & Highlights

**Business Problems Addressed:**
1. Which product subcategories are generating the most profit vs. 
   sales this year compared to last year?
2. Which weeks had below-average sales and profit — and is there a 
   seasonal pattern to performance dips?
3. Who are the top 10 customers by profit, and how recently did they 
   place an order?
4. Which regions, states, or cities have the highest concentration of 
   high-order customers?

**Goal of the Dashboard:**
To deliver a single, parameter-driven Tableau interface that eliminates 
static year-specific reports — enabling stakeholders to dynamically 
select any year and instantly compare performance against the prior 
year across all KPIs, product lines, and customer segments.

**Key Calculated Fields:**

| Field | Logic |
|---|---|
| CY Sales / Profit / Quantity / Orders / Customers | Filter to selected parameter year |
| PY Sales / Profit / Quantity / Orders / Customers | Filter to parameter year − 1 |
| % Diff (all KPIs) | (CY − PY) / PY |
| Min/Max Sales, Profit, etc. | WINDOW_MAX to highlight peak months |
| KPI Sales Avg / Profit Avg | Above/Below WINDOW_AVG for weekly trend coloring |
| Nr of Orders per Customers | FIXED LOD — order count per customer for histogram |
| Current Year / Previous Year | Alias labels derived from the Select Year parameter |

**Dynamic Parameter:**
A single `Select Year` parameter (default: 2023) drives every CY and 
PY field across both dashboards — making the entire workbook reusable 
across any reporting period without modification.

---

## Business Impact

- **Sales Teams** can identify which subcategories are high-revenue 
  but low-margin, and redirect focus accordingly
- **Marketing Teams** can pinpoint seasonal dips in weekly trends to 
  time campaigns more effectively
- **Account Managers** can use the Top 10 Customer table to prioritize 
  outreach based on recency and profitability
- **Leadership** gets an instant CY vs. PY snapshot across all core 
  KPIs without waiting for manual reports

---

## File Structure

Sales___Customer_Dashboards__Dynamic_.twbx

├── Sales & Customer Dashboards (Dynamic).twb   # Tableau workbook

└── Data/

└── Sales DataSource                        # Embedded data extract

---

*Built with Tableau Desktop · Single-source flat table · 
Dynamic year parameter · 2 dashboards · 15 worksheets*

### 6.	Screenshots
 ![Dashboard Preview](https://github.com/Akshit7-Jain/Sales---Customer-Dynamic-Dashboard/blob/main/Sales%20Dashboard%20(2).png)
![Dashboard Preview](https://github.com/Akshit7-Jain/Sales---Customer-Dynamic-Dashboard/blob/main/Customer%20Dashboard.png)

