# Executive Sales Performance Dashboard
### Part 4 — Tableau Executive Dashboard & Data Storytelling
**BITSoM × Masai School | Business Analytics with Generative AI**

---

## Business Problem Summary

The leadership team of a retail company needed a single, executive-facing dashboard to monitor sales performance, profitability, customer segments, shipping efficiency, discount impact, and return patterns across a 24-month period. The goal was to move from scattered reports to one decision-support tool that answers the question: **"Where should we focus to grow profitably?"**

---

## Dataset Description

| Attribute | Detail |
|---|---|
| File Name | dashboard_sales_data.xlsx |
| Sheet | dashboard_sales_data |
| Total Records | 4,200 orders |
| Time Period | January 2024 – December 2025 |
| Geography | 4 Regions (North, South, East, West) |
| Categories | Furniture, Office Supplies, Technology |
| Sub-Categories | 13 (Copiers, Phones, Accessories, Machines, Chairs, etc.) |
| Customer Segments | Home Office, Consumer, Corporate |
| Ship Modes | Standard Class, Second Class, First Class, Same Day |
| Campaign Channels | Organic, Paid, Email, Social, Referral |

**Key Fields:**
- `order_id`, `order_date`, `ship_date` — Order and time tracking
- `customer_segment`, `region`, `state`, `city` — Customer and geography
- `category`, `sub_category`, `product_name` — Product hierarchy
- `ship_mode`, `delivery_days` — Shipping and logistics
- `sales`, `quantity`, `discount`, `profit` — Financial measures
- `return_flag` — Binary return indicator (1 = returned)
- `customer_rating` — Post-delivery satisfaction score
- `campaign_channel` — Marketing attribution

---

## Tableau Workbook Description

**File:** `tableau/executive_dashboard.twbx`
**Tool:** Tableau Desktop 2026.2
**Type:** Packaged Workbook (includes embedded data source)

The workbook contains:
- 7 analytical worksheets
- 3 KPI card sheets
- 1 Executive Dashboard (main view)

---

## Calculated Fields Created

| Field Name | Formula | Purpose |
|---|---|---|
| Profit Margin | `SUM([profit]) / SUM([sales])` | Measures overall profitability efficiency |
| Cost | `SUM([sales]) - SUM([profit])` | Identifies cost structure per category/region |
| Avg Order Value | `SUM([sales]) / COUNTD([order_id])` | Tracks revenue per transaction |
| Return Rate | `SUM([return_flag]) / COUNT([order_id])` | Flags quality and service risk by segment |
| Shipping Delay Bucket | `IF [delivery_days] <= 2 THEN "Fast" ELSEIF [delivery_days] <= 5 THEN "Normal" ELSE "Delayed" END` | Categorizes delivery performance for operations review |

---

## Dashboard Components

### KPI Cards (Top Row)
| KPI | Value | Meaning |
|---|---|---|
| Total Sales | ₹21,70,17,651.92 | Total revenue across all regions and segments |
| Total Profit | ₹3,33,06,312.84 | Net profit after discounts |
| Profit Margin | 15.35% | Overall business efficiency |

### Analytical Charts
| View | Chart Type | Key Insight |
|---|---|---|
| Sales Trend | Line Chart | Q4 2025 peak at ₹1.08Cr/month |
| Regional Performance | Horizontal Bar | South leads (₹6.47Cr), East lags |
| Category Profitability | Horizontal Bar + Diverging Color | Technology = 84% of total profit |
| Customer Segment | Horizontal Bar | Home Office leads at ₹7.45Cr |
| Shipping Performance | Stacked Bar | Standard Class highest volume + delay risk |
| Discount vs Profit | Scatter Plot | Discounts >30% generate negative profit |
| Return Analysis | Stacked Bar | Furniture return rate 7.67% — highest risk |

---

## Filters and Interactions

### Global Filters (applied to all worksheets):
1. **Region** — Filter by North / South / East / West
2. **Category** — Filter by Furniture / Office Supplies / Technology
3. **Customer Segment** — Filter by Home Office / Consumer / Corporate

### Dashboard Actions:
- Clicking on a region in Regional Performance filters all other charts to show data for that region only
- Clicking on a category in Category Profitability cross-filters segment and shipping views

---

## Key Business Insights

1. **Technology drives 84% of profit** — Copiers, Phones, and Accessories are star products
2. **South region outperforms East by 32%** — Execution gap in East needs investigation
3. **Discounts above 30% destroy value** — Average loss of ₹1,601 per order at 30–50% discount
4. **Furniture returns at 7.67%** — Double the Technology return rate; quality issue likely
5. **Home Office is the highest revenue segment** — ₹7.45Cr vs ₹7.06Cr Corporate
6. **Standard Class carries 58% of orders** — Delay risk concentrated in this mode
7. **Organic channel generates 40.9% of revenue** — Strong brand pull but concentration risk
8. **Office Supplies margins are thin** — ₹17L profit on ₹1.15Cr sales (14.8% margin)

---

## Dashboard Story Summary

The business is fundamentally healthy — ₹21.7Cr in revenue with a 15.35% margin — but three structural risks require urgent leadership attention:

1. **Discount policy is losing money on 30%+ discount orders** — needs an approval gate
2. **Furniture returns are elevated** — costing reverse logistics and reducing customer LTV
3. **Technology profit concentration** — 84% of profit from one category is a supply chain risk

The biggest growth opportunity is the **Corporate segment**, which is currently the lowest revenue contributor despite having the highest deal size potential. A dedicated B2B sales motion could add ₹1–1.5Cr in annual revenue within 12 months.

---

## Assumptions and Limitations

**Assumptions:**
- `profit` field in dataset is treated as gross profit (Sales - Cost of Goods); additional operating expenses not included
- `return_flag = 1` indicates a confirmed return; reason for return not captured
- `delivery_days` is calculated as ship_date minus order_date; actual customer-facing delivery time may differ
- Campaign channel attribution is last-touch; multi-touch attribution not available

**Limitations:**
- No customer-level cohort data — cannot calculate Customer Lifetime Value (LTV)
- No benchmark data — regional and segment comparisons are internal only, not vs. industry
- Static dataset — dashboard shows historical 2024–2025 data, not real-time feed
- Return reasons not captured — cannot distinguish quality returns from logistics returns

---

## Screenshots Included

| File | Description |
|---|---|
| `screenshots/full_dashboard.png` | Complete executive dashboard view |
| `screenshots/sales_trend_view.png` | Monthly sales trend with average reference line |
| `screenshots/regional_performance_view.png` | Sales by region, sorted descending |
| `screenshots/category_profitability_view.png` | Sub-category profit with Red-Green diverging colors |
| `screenshots/filter_interaction_view.png` | Dashboard showing active filter interaction |

---

## Repository Structure

```
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```

---

*Submitted by: Manya Seth | Program: BITSoM × Masai School — Business Analytics with Generative AI | Date: June 2026*
