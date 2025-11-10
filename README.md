# Business Sales Dashboard (Power BI)

A clean, interactive *Power BI* dashboard to analyze sales performance across *Categories, Regions, Products, and Segments* with slicers for quick exploration.

---

## 🖼️ Preview
![Dashboard Screenshot](./assets/business-sales-dashboard.png) <!-- replace with your path -->

---

## ✨ Highlights (KPIs)
- *Average Sales:* 229.86  
- *Total Sales:* 2.30M  
- *Total Profit:* 286.40K  
- *Total Quantity:* 38K

> Values shown are sample results from the dataset used in this report.

---

## 📊 Visuals Included
1. *Total Profit by Category* (Technology, Furniture, Office Supplies)
2. *Total Sales by Product Name* (Top products)
3. *Sum of Sales by Category*
4. *Profit Margin by Category*
5. *Sum of Sales by Region* (West, East, Central, South)
6. *Top Sales by Segment* (Pie: Consumer, Corporate, Home Office)
7. *Slicers:* Order Date, Region, Category

## 🛠️ Tools & Stack
- Power BI Desktop
- Power Query (data cleaning & shaping)
- DAX (measures & KPIs)
- Excel/CSV as data source

## 🧮 DAX Measures (Core)
```DAX
Total Sales = SUM(Sales[Sales])

Total Profit = SUM(Sales[Profit])

Average Sales = AVERAGE(Sales[Sales])

Total Quantity = SUM(Sales[Quantity])

Profit Margin = 
VAR _sales = [Total Sales]
RETURN IF(_sales = 0, BLANK(), DIVIDE([Total Profit], _sales))

Top N Sales (Products) = 
CALCULATE([Total Sales], TOPN(10, ALL('Products'[Product Name]), [Total Sales], DESC))# FUTURE_DS_01
