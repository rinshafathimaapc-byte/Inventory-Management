# 📦 Inventory Management Analytics

An end-to-end inventory analytics project. It starts from a 5,000-SKU dataset and builds the same analysis in **Excel**, **Power BI** and **Tableau**. The aim is to show where stock value sits, which products are running low, and how suppliers, warehouses and countries perform.

![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoft-excel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black)
![Tableau](https://img.shields.io/badge/Tableau-E97627?logo=tableau&logoColor=white)

---

## 📌 Business Problem

Inventory teams have to answer a few questions all the time:

- How much capital is tied up in stock, and where?
- Which products are at or below their reorder point?
- Which suppliers and warehouses hold the most inventory?
- How do lead times and stock levels differ across countries?

This project turns raw inventory records into dashboards that answer those questions.

---

## 🗂️ Dataset

| Item | Detail |
|---|---|
| Records | 5,000 products (unique `Product_ID`) |
| Columns | 17 (see below) |
| Categories | 7: Clothing, Toys, Home & Garden, Sports, Electronics, Books, Office Supplies |
| Countries | 10 |
| Suppliers | 50 |
| Date range | Entry dates from Mar 2023 to Mar 2025 |
| Data quality | No missing values, no duplicate Product IDs |

**Fields:** `Product_ID`, `Product_Name`, `Category`, `Unit_Price`, `Stock_Quantity`, `Stock_Level`, `Reorder_Point`, `Lead_Time_Days`, `Last_Restock_Date`, `Supplier_ID`, `Warehouse_Location`, `Min_Order_Quantity`, `Status`, `Entry_Date`, `Country`, `Latitude`, `Longitude`

A full data dictionary is included in the `Data Dictionary` sheet of the core data file.

### Calculated fields

| Metric | Logic |
|---|---|
| **Inventory Value** | `Unit_Price × Stock_Quantity` |
| **Low Stock Item** | `1` if `Stock_Quantity ≤ Reorder_Point`, otherwise `0` |

---

## 🔑 Headline KPIs

| KPI | Value |
|---|---|
| Total Products | 5,000 |
| Total Stock Quantity | ~2.50 million units |
| Total Inventory Value | ~$1.25 billion |
| Low Stock Items (at or below reorder point) | 263 |
| Out-of-Stock Products | 774 (15.5%) |
| Average Lead Time | ~15 days |

---

## 🛠️ Project Workflow

```
Core Data  ──►  Excel Dashboard  ──►  Power BI Dashboard  ──►  Tableau Dashboard
(clean data)    (pivots + slicers)    (DAX + interactive)       (visual storytelling)
```

### 1️⃣ Core Data
- A clean 5,000-row inventory table with a data dictionary.
- Checked for nulls and duplicates.
- Added geo-coordinates (`Latitude`, `Longitude`) for map visuals.

### 2️⃣ Excel Dashboard
- Excel Table with calculated columns (`Inventory Value`, `Low Stock Items`).
- 26 PivotTables feeding the charts, with `GETPIVOTDATA` KPI cards.
- Slicers for interactive filtering.
- **4 dashboard sheets:** Executive Summary, Inventory Analysis, Regional Analysis, Warehouse & Supplier Analysis.

### 3️⃣ Power BI Dashboard
- **4 report pages:** Executive Summary, Inventory Analysis, Regional Analysis, Supplier & Warehouse Analysis.
- KPI cards, filled map, line charts and clustered column charts.
- Trends over time: product entries and restocks.

### 4️⃣ Tableau Dashboard
- Custom background design with KPI tiles.
- Worksheets include Inventory by Country (map), Inventory Value by Category, Supplier and Warehouse, Stock Level by Country, Out of Stock by Category, Restock Trend, Product Entries Over Time and Unit Price vs Stock Quantity.

---

## 📊 Dashboard Pages

| Page | What it answers |
|---|---|
| **Executive Summary** | Overall health: products, stock, value, low-stock count, lead time, countries, suppliers, warehouses |
| **Inventory Analysis** | Stock quantity and value by category and product; stock level mix |
| **Regional Analysis** | Stock, value and lead time by country, with a map view |
| **Supplier & Warehouse Analysis** | Product count and inventory value by supplier and warehouse |

---

## 💡 Key Insights

- **Value is spread evenly across categories.** Home & Garden, Books and Office Supplies each hold about $187–190M of inventory.
- **Germany holds the most inventory value** (~$141M), followed by Poland and Belgium.
- **About 1 in 6 products is out of stock** (774 of 5,000), and 263 products are at or below their reorder point. These are the first candidates for replenishment.
- **Stock levels are mixed:** 2,021 Mid, 1,491 Low and 1,488 High.

---

## 🧰 Tools & Skills Demonstrated

- **Excel:** PivotTables, slicers, structured tables, calculated columns, `GETPIVOTDATA`, dashboard design
- **Power BI:** data modelling, DAX measures, multi-page reports, map visuals
- **Tableau:** calculated fields, dashboards, custom layouts
- **Data analysis:** data cleaning, KPI design, inventory and supply-chain analytics

---

## 📁 Repository Structure

```
├── data/
│   └── Inventory_Management_C25_English.xlsx   # Core dataset + data dictionary
├── excel/
│   └── Inventory_Management.xlsx               # Excel dashboard
├── powerbi/
│   └── Inventory_Management.pbix               # Power BI dashboard
├── tableau/
│   └── Inventory_Management.twbx               # Tableau packaged workbook
├── images/                                     # Dashboard screenshots
└── README.md
```
---

## 🚀 Future Improvements

- Add sales or demand data for turnover and days-of-stock analysis
- Reorder-quantity recommendations using lead time and `Min_Order_Quantity`
- Supplier performance scoring
- Automated data refresh

---

## 👤 Author

**<Rinsha Fathima PC>**
[LinkedIn](<www.linkedin.com/in/rinsha-fathima-pc-a85518388>) · [GitHub](https://github.com/<rinshafathimaapc-byte>) · rinshafathimaapc@gmail.com

⭐ If you found this project useful, please give it a star!

