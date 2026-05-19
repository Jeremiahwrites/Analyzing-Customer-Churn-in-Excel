# 📊 Telecom Customer Churn Analysis — Excel Dashboard

> An end-to-end customer churn analysis built entirely in Microsoft Excel — from raw data cleaning to an interactive dashboard with pivot tables, charts, and KPI cards.

![Dashboard Preview](WhatsApp_Image_2026-05-19_at_11_27_27_AM.jpeg)

---

## 📁 Project Structure

```
Churn_Analysis.xlsx
├── Overview          → KPI summary cards + pivot-based charts (the dashboard)
├── Churn Analysis    → Supporting pivot tables and chart data
├── Customer Pivots   → Age group, demographics, consumption breakdowns
├── Databel - Aggregate  → Cleaned, enriched aggregate dataset (primary working table)
└── Databel - Customer   → Raw customer-level data (deduplicated source)
```

---

## 🧹 Data Preparation Steps

The raw `Databel - Customer` dataset was cleaned and transformed before analysis:

- **Removed duplicates** across both the customer and aggregate worksheets
- **Converted data ranges to Excel Tables** (`Ctrl+T`) for structured referencing and auto-expansion
- **Created new columns using `IF()` formulas** to derive binary Yes/No flags:
  - `Under 30` — flags customers aged below 30
  - `Senior` — flags customers aged 65 and above
  - `Churned` — binary churn label derived from the Churn Label field
- **Grouped age data** into decade bands (19–28, 29–38, 39–48, 49–58, 59–68, 69–78, 79–88)
- **Grouped data consumption** into three tiers: `Less than 5GB`, `Between 5 and 10GB`, `10 or more GB`
- **Classified demographics** into three segments: `Under 30`, `Senior`, `Other`
- **Bucketed churn reasons** into high-level categories: Competitor, Attitude, Dissatisfaction, Price, Other

---

## 📌 Key Metrics

| Metric | Value |
|---|---|
| Total Customers | **6,687** |
| Churned Customers | **1,796** |
| Overall Churn Rate | **26.86%** |
| Highest-Risk State | **California (CA) — 75%** |
| Top Churn Driver | **Competitor made better offer** |

---

## 🔍 Key Insights

### 1. 🏆 Competitor Pressure is the #1 Churn Driver
Competitor-related reasons account for the **largest share of explained churn**:
- *Competitor made better offer* — 91 churned customers
- *Competitor had better devices* — 78 churned customers
- *Competitor offered more data* — 24 churned customers

Combined, competitor actions explain roughly **37% of categorised churn**, making this the single most critical area for retention strategy.

---

### 2. 📍 Geographic Concentration of High-Risk States
Churn is far from uniform across states. A cluster of states shows alarming rates:

| State | Churn Rate |
|---|---|
| CA | 75.00% |
| IN | 66.67% |
| NH | 62.50% |
| LA | 50.00% |
| KY | 50.00% |
| TX | 41.67% |

States like **California, Indiana, and New Hampshire** may have stronger competitive alternatives or service coverage gaps. Targeted retention campaigns in these markets could yield outsized returns.

---

### 3. 📱 Month-to-Month Contracts Drive Churn
Contract type is a strong predictor of churn. Out of 469 total churned customers with recorded contracts:
- **Month-to-Month**: 423 churned customers (~90% of all contract-based churn)
- **One Year**: 34
- **Two Year**: 12

Customers on flexible monthly contracts are dramatically more likely to leave. Incentivising annual or biennial commitments through discounts or perks is a high-impact retention lever.

---

### 4. 💳 Direct Debit Users Churn at Nearly Double the Rate
Payment method reveals a surprising behavioural pattern:

| Payment Method | Churn Rate |
|---|---|
| Direct Debit | **43.96%** |
| Paper Check | 31.91% |
| Credit Card | 24.70% |

Direct Debit customers — often less engaged with their billing — churn at nearly twice the rate of credit card users. This warrants investigation into whether billing friction, unexpected charges, or lack of engagement is driving this segment away.

---

### 5. 📶 Unlimited Data Plan Users Churn More
Counterintuitively, customers **with** an unlimited data plan churn at a significantly higher rate than those without:

| Plan | Churn Rate |
|---|---|
| Unlimited Plan: Yes | **32.11%** |
| Unlimited Plan: No | 16.10% |

This may indicate that unlimited plan holders are more cost-sensitive or are being poached by competitors offering similar plans at lower prices.

---

### 6. 👴 Older Customers Churn More
The median age of churned customers (**50 years**) is higher than that of retained customers (**46 years**). Churn rate rises steadily with age and peaks in the **69–88 age band**, consistent with the Senior demographic accounting for **469 churned customers** despite being a smaller segment. Senior customers may have higher price sensitivity or less loyalty to digital service ecosystems.

---

### 7. 📊 Moderate Data Users Are Most At Risk
Looking at churn by consumption tier:

| Consumption | Total Customers | Churned | Churn Rate |
|---|---|---|---|
| Less than 5GB | 3,242 | 741 | 22.9% |
| Between 5 and 10GB | 1,783 | 595 | **33.4%** |
| 10 or more GB | 1,662 | 460 | 27.7% |

The **mid-tier (5–10GB) segment has the highest churn rate**. These users are likely outgrowing their plans but not yet committed enough to upgrade, making them a prime target for proactive upsell outreach before they leave.

---

### 8. 😤 Attitude & Service Quality: A Hidden Churn Driver
Beyond competitors, **attitude-related churn** — poor support interactions — was responsible for 84 churned customers, with *Attitude of support person* being the single largest non-competitor churn reason (60 customers). This points to a **customer service quality gap** that's entirely within the company's control.

---

## 📈 Dashboard Features

The **Overview** sheet presents a fully interactive Excel dashboard including:

- **KPI Summary Cards** — Total Customers, Churned Customers, Churn Rate %
- **Churn Reasons Bar Chart** — Ranked horizontal bars across all churn reasons
- **Competitor Churn Donut Chart** — Breakdown of the four competitor sub-reasons
- **Churn by Demographics Donut** — Senior vs. Under 30 vs. Other segmentation
- **Age Group Analysis Combo Chart** — Customers (bar) and Churn % (line) by age band
- **Consumption Churn Stacked Bar** — Yes/No churn across the three data tiers
- **International Plan Churn Heat Table** — State-level churn rates filtered by Intl Plan = Yes, colour-coded from green (low) to red (high)

---

## 🛠️ Tools & Techniques Used

| Tool / Feature | Purpose |
|---|---|
| Excel Tables | Structured references, auto-expansion |
| `IF()` | Binary classification columns |
| `IFS()` / Nested `IF()` | Age grouping, consumption tiering |
| Pivot Tables | Aggregating churn by dimension |
| Pivot Charts | Dynamic visualisations |
| Conditional Formatting | Heat-map colouring on state churn table |
| Data Bars & Colour Scales | Visual ranking in pivot outputs |
| Slicers | (International Plan filter on Overview) |

---

## 💡 Recommendations

Based on the analysis, the following actions are recommended:

1. **Launch a contract upgrade campaign** targeting Month-to-Month customers with discounted annual plan offers.
2. **Investigate competitor pricing** in high-churn states (CA, IN, NH, LA, KY) and consider region-specific retention offers.
3. **Review direct debit billing experience** — simplify or add transparency to billing communications for this segment.
4. **Proactively contact mid-tier data users** (5–10GB) with personalised upgrade offers before they churn.
5. **Invest in customer service training**, particularly around *attitude* and *tone*, to reduce the 84 churns attributable to poor human interactions.
6. **Audit the unlimited data plan pricing** — if holders are churning to competitors, a price-match or loyalty reward may be warranted.

---

## 🚀 Getting Started

1. Download `Churn_Analysis.xlsx`
2. Open in **Microsoft Excel 2016 or later** (pivot charts and slicers require Excel desktop)
3. Navigate to the **Overview** sheet to explore the dashboard
4. Use the **Intl Plan slicer** on the right to filter the state heat-map
5. Explore individual pivot sheets (`Churn Analysis`, `Customer Pivots`) to drill into specific segments

---

## 📂 Dataset

The underlying data is based on the **Databel telecom churn dataset** — a fictional but realistic telecommunications company dataset commonly used for churn modelling exercises.

- **6,687 customers** across **50 US states + DC**
- **30 features** including demographics, plan details, usage metrics, and churn labels
- Data covers contract types, payment methods, international plans, data consumption, and customer service interaction history

---

*Built as an Excel skills refresh project — covering data cleaning, structured tables, IF-formula engineering, pivot analysis, and dashboard design.*
