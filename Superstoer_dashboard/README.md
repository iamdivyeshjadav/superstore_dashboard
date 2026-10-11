<div align="center">

# -- ! SuperStore Sales Dashboard ! --
### *Interactive Power BI Dashboard for Sales, Profit & Discount Analysis*

[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/Analysis-KPIs%20%26%20Aggregations-FF6F00?style=for-the-badge&logo=powerbi&logoColor=white)](https://powerbi.microsoft.com/)
[![Dataset](https://img.shields.io/badge/Dataset-Sample%20Superstore-4CAF50?style=for-the-badge&logo=databricks&logoColor=white)](https://powerbi.microsoft.com/)
[![Design](https://img.shields.io/badge/Design-Dark%20Glass%20Theme-9C27B0?style=for-the-badge&logo=figma&logoColor=white)](https://powerbi.microsoft.com/)

<br/>

> *"Data tells you what happened — a good dashboard tells you what to do next."*

</div>

---

## 📋 Table of Contents

- [📌 Overview](#-overview)
- [🎯 Problem Statement](#-problem-statement)
- [✨ Key Features](#-key-features)
- [🏗️ Project Structure](#️-project-structure)
- [🔄 Project Workflow](#-project-workflow)
- [📊 Part A — Dashboard Page](#-part-a--dashboard-page)
- [📑 Part B — Data Table Page](#-part-b--data-table-page)
- [🗃️ Dataset Fields](#️-dataset-fields)
- [🛠️ Tech Stack](#️-tech-stack)
- [📈 Results & Insights](#-results--insights)
- [🏆 Advantages](#-advantages)
- [🚀 How to Run](#-how-to-run)
- [📄 License](#-license)
- [👤 Author](#-author)
- [🙏 Acknowledgements](#-acknowledgements)

---

## 📌 Overview

The **SuperStore Sales Dashboard** is a beginner-friendly, interactive **Power BI** report built on the well-known **Sample - Superstore** retail dataset. It summarizes business performance through **KPI cards**, **bar charts**, **slicers**, and a **detailed transaction table**, all wrapped in a custom dark "glass" themed canvas.

This project is designed to:
- Practice building a **multi-page Power BI report** from a single data table
- Apply **aggregations** (Sum, Average) to create business KPIs
- Use **slicers** and **visual-level filters** (Top N) for interactive analysis
- Present **key insights** in plain language next to the charts

---

## 🎯 Problem Statement

> **Objective:** Build an interactive dashboard that helps a retail manager quickly understand sales, profit, quantity sold, and discounting behaviour across regions and product categories.

You are building a reporting tool for a retail business. The dashboard must answer questions such as *"Which category sells the most?"*, *"Which region earns the highest profit?"*, and *"How much discount are we giving on average?"*

| 📂 Component | 📄 Type | 🔍 Description |
|--------------|---------|----------------|
| KPI Cards | Summary | Total Sales, Total Profit, Total Quantity, Average Discount |
| Region Slicer | Filter | Filter the whole page by region |
| Category Slicer | Filter | Filter the whole page by product category |
| Sales by Category | Bar Chart | Sales compared across categories (Top 5 sub-categories by sales) |
| Profit by Region | Bar Chart | Profit compared across regions |
| Key Insights | Text Boxes | Four plain-language takeaways |
| Data Table | Table | Row-level order details on a dedicated page |

The goal is to demonstrate **fundamental Power BI skills** — data modelling, visuals, filtering, and design — in one clean report.

---

## ✨ Key Features

| Feature | Description |
|--------|-------------|
| 🧮 **4 KPI Cards** | Sales, Profit, Quantity, and Average Discount at the top of the page |
| 🎚️ **2 Slicers** | Region and Category slicers that cross-filter every visual |
| 📊 **2 Bar Charts** | *Sales by Category* and *Profit by Region* with bold titles |
| 🏅 **Top N Filter** | Sales chart is limited to the **Top 5 Sub Categories** by sales |
| 🚚 **Ship Mode Filter** | Page-level filter keeps only **Second Class** and **Standard Class** orders |
| 💡 **Key Insights Panel** | Four text boxes summarising margin, top category, top region, and discount |
| 🎨 **Custom Canvas** | Dark navy-to-purple glass background image with icons, 1920 × 1080 |
| 📑 **2 Report Pages** | `DASHBOARD` (overview) and `TABAL` (detailed table) |

---

## 🏗️ Project Structure

```
📦 superstore-powerbi-dashboard/
│
├── 📄 Superstore_dashboard.pbix   ← Main Power BI report (open in Power BI Desktop)
│
└── 📄 README.md                   ← Project documentation
```

**Inside the `.pbix` file:**

```
📊 Superstore_dashboard.pbix
│
├── 🗃️ Data Model
│   └── Sample - Superstore          ← Single fact table
│
├── 📄 Page 1: DASHBOARD             ← KPIs, slicers, charts, insights
│
├── 📄 Page 2: TABAL                 ← Detailed order-level table
│
└── 🖼️ Registered Resources
    ├── superstore_canvas_v5_dynamic.png        ← Dashboard background
    └── superstore_sales_table_compact.png      ← Table page background
```

---

## 🔄 Project Workflow

```
Load "Sample - Superstore" Data
            │
            ▼
┌─────────────────────────────┐
│   Build Data Model          │  ← Single table with sales, profit, dates
└────────────┬────────────────┘
             │
     ┌───────┴────────┐
     ▼                ▼
┌─────────────┐   ┌──────────────────┐
│   Page 1    │   │     Page 2       │
│  DASHBOARD  │   │      TABAL       │
└──────┬──────┘   └────────┬─────────┘
       │                   │
       ▼                   ▼
┌─────────────┐   ┌──────────────────┐
│ KPI Cards   │   │ Detailed Table   │
│ Slicers     │   │ (11 columns)     │
│ Bar Charts  │   │                  │
│ Insights    │   │                  │
└──────┬──────┘   └────────┬─────────┘
       │                   │
       ▼                   ▼
┌─────────────────────────────┐
│  Interact: Slice & Filter   │
└────────────┬────────────────┘
             │
             ▼
   Publish / Share Insights ✅
```

---

## 📊 Part A — Dashboard Page

### 📝 1. Page Layout

The `DASHBOARD` page uses a **1920 × 1080** canvas (Fit to Page) with a custom background image. Visuals are placed in four horizontal bands:

```
┌──────────────────────────────────────────────────────────────┐
│  🛒 SuperStore                                  (header)      │
├────────────┬────────────┬────────────┬───────────────────────┤
│  💰 Sales  │  📈 Profit │ 📦 Quantity│  🏷️ Avg Discount      │  ← KPI cards
├────────────┴────────────┼────────────┴───────────────────────┤
│  📍 Region Slicer       │  🧩 Category Slicer                 │  ← Slicers
├─────────────────────────┼────────────────────────────────────┤
│                         │                                    │
│   Sales by Category     │      Profit by Region              │  ← Bar charts
│                         │                                    │
├─────────────────────────┴────────────────────────────────────┤
│  💡 Key Insights:  Top Category | Top Region | Margin | Discount │
└──────────────────────────────────────────────────────────────┘
```

---

### 🧮 2. KPI Cards

> Four card visuals show the headline numbers for the current filter selection.

| KPI | Field | Aggregation |
|-----|-------|-------------|
| 💰 **Sales** | `Sales` | Sum |
| 📈 **Profit** | `Profit` | Sum |
| 📦 **Quantity** | `Quantity` | Sum |
| 🏷️ **Avg Discount** | `Discount` | Average |

**Logic (equivalent DAX):**
```dax
Total Sales    = SUM('Sample - Superstore'[Sales])
Total Profit   = SUM('Sample - Superstore'[Profit])
Total Quantity = SUM('Sample - Superstore'[Quantity])
Avg Discount   = AVERAGE('Sample - Superstore'[Discount])
```

> 💡 In the report these are implicit measures created by dragging the column into a card and choosing the aggregation.

---

### 🎚️ 3. Slicers

| Slicer | Field | Effect |
|--------|-------|--------|
| 📍 Region | `Region` | Filters all visuals on the page by region |
| 🧩 Category | `Category` | Filters all visuals on the page by product category |

---

### 📊 4. Sales by Category

> Clustered bar chart comparing **total sales** across categories.

| Setting | Value |
|---------|-------|
| 📐 Visual Type | Clustered Bar Chart |
| 🗂️ Axis (Category) | `Category` |
| 📏 Value | Sum of `Sales` |
| 🏅 Visual Filter | **Top 5** `Sub Category` by Sum of `Sales` |

---

### 🗺️ 5. Profit by Region

> Clustered bar chart comparing **total profit** across the four regions.

| Setting | Value |
|---------|-------|
| 📐 Visual Type | Clustered Bar Chart |
| 🗂️ Axis (Category) | `Region` |
| 📏 Value | Sum of `Profit` |

---

### 🚚 6. Page-Level Filter

| Field | Allowed Values |
|-------|----------------|
| `Ship Mode` | **Second Class**, **Standard Class** |

> ⚠️ Orders shipped via *First Class* and *Same Day* are excluded from every number on the DASHBOARD page.

---

### 💡 7. Key Insights Panel

Four text boxes at the bottom of the page summarise the story in one line each:

| Insight | Message on Dashboard |
|---------|----------------------|
| 🧩 **Top Category** | Furniture has the highest sales. |
| 📍 **Top Region** | West earns the highest profit. |
| 📈 **Profit Margin** | 11.9% of total sales is profit. |
| 🏷️ **Avg Discount** | Average discount given is 16%. |

> 📝 **Note:** These insights are **static text boxes**. If you change filters or refresh the data, update the text manually (or convert them into DAX-driven cards).

---

## 📑 Part B — Data Table Page

### 🔍 8. TABAL Page

> A full-width **table visual** (1920 × 955) showing row-level details, placed on its own page with a matching compact background.

| # | Column | Description |
|---|--------|-------------|
| 1 | `Customer Name` | Who placed the order |
| 2 | `Order Date` | Date the order was placed |
| 3 | `Ship Date` | Date the order was shipped |
| 4 | `Product Name` | Name of the product |
| 5 | `Category` | Furniture / Office Supplies / Technology |
| 6 | `Sub Category` | More specific product group |
| 7 | `Region` | Sales region |
| 8 | `Sales` | Revenue from the line item |
| 9 | `Quantity` | Units sold |
| 10 | `Discount` | Discount applied |
| 11 | `Profit` | Profit from the line item |

---

## 🗃️ Dataset Fields

All visuals read from one table: **`Sample - Superstore`**.

| Field | Used In |
|-------|---------|
| `Sales` | KPI card, Sales by Category, Data table |
| `Profit` | KPI card, Profit by Region, Data table |
| `Quantity` | KPI card, Data table |
| `Discount` | KPI card, Data table |
| `Category` | Slicer, Sales by Category, Data table |
| `Sub Category` | Top 5 filter, Data table |
| `Region` | Slicer, Profit by Region, Data table |
| `Ship Mode` | Page-level filter |
| `Customer Name`, `Order Date`, `Ship Date`, `Product Name` | Data table |

---

## 🛠️ Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| 📊 **Power BI Desktop** | Latest | Report authoring and data modelling |
| 🧮 **DAX / Aggregations** | Built-in | Sum and Average KPIs |
| 🎚️ **Slicers** | Built-in | Interactive Region and Category filtering |
| 📊 **Clustered Bar Chart** | Built-in | Category and region comparisons |
| 📋 **Table Visual** | Built-in | Order-level detail view |
| 🎨 **Fluent 2 Base Theme** | Built-in | Default colour and font styling |
| 🖼️ **Custom PNG Backgrounds** | 1920 × 1080 | Dark glass-style canvas design |

---

## 📈 Results & Insights

After exploring the dashboard, the following conclusions are shown:

- ✅ **Furniture** is the top category by sales
- 🗺️ **West** is the most profitable region
- 📈 **Profit margin** is about **11.9%** of total sales
- 🏷️ **Average discount** is about **16%** across orders
- 🔁 **Everything is interactive** — slicers re-calculate all cards and charts instantly
- 📑 **Drill to detail** — the TABAL page lists the underlying orders

---

## 🏆 Advantages

| Advantage | Detail |
|-----------|--------|
| 🎓 **Beginner Friendly** | Single table, simple aggregations, easy to follow |
| 👀 **At-a-Glance Insights** | KPIs and takeaways visible without scrolling |
| 🎚️ **Interactive** | Region and Category slicers reshape the whole page |
| 🎨 **Polished Design** | Dark glass theme with consistent icons and colours |
| 📑 **Summary + Detail** | Overview page plus a full data table page |
| 🧪 **Extensible** | Easy to add Sub-Category, Time Trend, or Customer Segment visuals |
| 📱 **Fit to Page** | Scales cleanly to any screen size |
| 🔄 **Refreshable** | Reload the source data and all visuals update (except static insight text) |

---

## 🚀 How to Run

1. **Download** `Superstore_dashboard.pbix` from this repository
2. **Install** [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows)
3. **Open** the `.pbix` file by double-clicking it
4. **Explore** — click the slicers, hover over bars, and switch to the `TABAL` page

> 💡 No setup is needed — the data is embedded inside the file.

---
# img 

## Dashboard img

<img src="img/Dashboard img.png" alt="SuperStore Dashboard" width="200%">

---

## Tabal img

<img src="img/Table img.png" alt="SuperStore Dashboard" width="200%">

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for full details.

```
MIT License — Free to use, modify, and distribute with attribution.
```

---

## 👤 Author

<div align="center">

### Jadav Divvyesh

> *"Every chart starts with a single row of data — just like every insight starts with a single question."*

**🎓 Role:** Data Analytics Enthusiast | Power BI Learner \
**📍 Location:** India\
**🛠️ Skills:** Power BI · DAX · Data Visualization · Dashboard Design · Business Analytics
---



</div>

###  video link : https://drive.google.com/file/d/1W-IRlyy9QlGFKChr1ifmqe2QmUwAs9ld/view?usp=sharing


---

## 🙏 Acknowledgements

Special thanks to the following resources and communities that made this project possible:

- 📚 [Power BI Documentation](https://learn.microsoft.com/power-bi/) — Official Microsoft Power BI reference
- 📊 [Microsoft Learn — Power BI](https://learn.microsoft.com/training/powerplatform/power-bi) — Guided learning paths
- 🧮 [DAX Guide](https://dax.guide/) — Complete DAX function reference
- 🛒 [Sample Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) — Popular retail dataset for practice
- 🎨 [Power BI Community](https://community.fabric.microsoft.com/) — Questions, tips, and design ideas
- 💬 [Stack Overflow Community](https://stackoverflow.com/) — Problem-solving support
- 📖 [Kaggle Learn](https://www.kaggle.com/learn) — Data analysis courses

---

<div align="center">

---

*Made with ❤️ and ☕ — Last updated: 8 October, 2026*

</div>
