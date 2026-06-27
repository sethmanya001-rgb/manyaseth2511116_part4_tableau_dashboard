# Chart Selection Justification — Executive Sales Performance Dashboard

**Prepared by:** Business Analyst
**Dashboard Tool:** Tableau Desktop 2026.2

---

## Design Philosophy

Every chart in this dashboard was selected to answer a specific business question for a leadership audience. The guiding principle was: **if a chart does not support a decision, it does not belong in the dashboard.** Visual complexity was minimized, and business interpretability was maximized.

---

## Chart 1: Sales Trend — Line Chart

**Business Question Answered:** Is the business growing? Are there seasonal patterns leadership should plan for?

**Why Line Chart:**
A line chart is the most effective chart type for showing continuous data over time. It immediately communicates direction (up/down), momentum (slope), and volatility (peaks and valleys). Bar charts over time work for discrete comparisons but lose the "flow" that makes trends readable for executives.

**Fields Used:**
- X-Axis: Month of Order Date (continuous time dimension)
- Y-Axis: SUM(Sales) (quantitative measure)
- Reference Line: Average Sales (dashed line for benchmark comparison)
- Labels: Peak and trough values annotated

**Design Principle Applied:** Pre-attentive processing — the line direction is understood in under 1 second. The reference line gives instant context ("above or below average?") without requiring mental calculation.

**Mistake Avoided:** Did not use a dual-axis chart with both Sales and Profit on the same view — this confuses leadership with two competing stories. Profit trend is addressed separately in other views.

---

## Chart 2: Regional Performance — Horizontal Bar Chart

**Business Question Answered:** Which region is generating the most revenue? Where should leadership focus geographic investment?

**Why Horizontal Bar Chart:**
Bar charts are optimal for comparing discrete categorical values (regions) across a single metric (sales). Horizontal orientation was chosen because region names are text labels that read more comfortably left-to-right. A map was considered but rejected because the dataset uses region names (North/South/East/West), not state-level coordinates — a map would require geocoding and add complexity without adding insight.

**Fields Used:**
- Rows: Region (dimension)
- Columns: SUM(Sales) (measure)
- Color: SUM(Sales) — sequential blue palette (darker = higher sales)
- Labels: Sales value displayed on bars
- Sort: Descending by Sales

**Design Principle Applied:** Sorted descending so the highest-performing region appears at the top — consistent with how executives read ranked lists (best to worst). Color reinforces rank without requiring the reader to compare bar lengths precisely.

**Mistake Avoided:** Did not use a pie chart. Pie charts make regional comparison extremely difficult because humans cannot accurately judge angle differences. A bar chart makes the 18% gap between South (₹6.47Cr) and East (₹4.89Cr) immediately visible.

---

## Chart 3: Category Profitability — Horizontal Bar Chart with Diverging Color

**Business Question Answered:** Which product categories and sub-categories are making money, and which are loss leaders?

**Why Horizontal Bar Chart with Red-Green Diverging Color:**
This is the most critical chart for profit management. Horizontal bar chart was chosen because there are 13 sub-categories — a vertical bar chart would require angled labels and reduce readability. The diverging Red-Green color palette with center at zero is essential: it creates an instant visual split between profit (green) and loss (red) without requiring the reader to look at numbers.

**Fields Used:**
- Rows: Sub-Category (dimension)
- Columns: SUM(Profit) (measure)
- Color: SUM(Profit) — Red-Green Diverging, centered at 0
- Labels: Profit value on bars
- Sort: Descending by Profit
- Reference Line: Zero line (black) to anchor profit/loss boundary

**Design Principle Applied:** Zero reference line is the analytical anchor — everything to the right is profitable, everything to the left is a loss. This visual encoding follows traffic light logic (red = stop/problem, green = go/good) that is universally understood.

**Mistake Avoided:** Did not use a treemap. Treemaps are useful for showing proportional size but cannot show negative values — critical for this chart since some sub-categories may operate at a loss.

---

## Chart 4: Customer Segment View — Horizontal Bar Chart

**Business Question Answered:** Which customer segment generates the most revenue? Where should the sales team prioritize?

**Why Horizontal Bar Chart:**
With only three segments to compare (Home Office, Consumer, Corporate), a bar chart provides maximum clarity. Side-by-side comparison with profit encoded in color reveals both revenue size and profitability simultaneously.

**Fields Used:**
- Rows: Customer Segment (dimension)
- Columns: SUM(Sales) (measure)
- Color: SUM(Profit) — Red-Green Diverging
- Labels: Sales value on bars
- Sort: Descending by Sales

**Design Principle Applied:** Using color for a second variable (profit) without adding a second axis keeps the chart clean while conveying more information. This is the "dual encoding" principle — position communicates sales, color communicates profit.

**Mistake Avoided:** Did not use a stacked bar chart splitting sales by category within each segment — this would create 9 bars and make the segment-level comparison much harder to parse for an executive audience.

---

## Chart 5: Shipping Performance — Stacked Bar Chart

**Business Question Answered:** Which shipping mode has the most delivery delays? Where is the operational risk concentrated?

**Why Stacked Bar Chart:**
The shipping view needs to show two things simultaneously: (1) total order volume per shipping mode, and (2) the distribution of Fast/Normal/Delayed orders within each mode. A stacked bar chart achieves this efficiently — bar length = total volume, color segments = delay bucket breakdown.

**Fields Used:**
- Rows: Ship Mode (dimension)
- Columns: COUNT(Order ID) (measure)
- Color: Shipping Delay Bucket (calculated field — Fast/Normal/Delayed)
- Labels: Count values on each segment
- Sort: Descending by total count

**Design Principle Applied:** Color encodes the most important variable (delay severity) using an intuitive palette: green = fast, orange = normal, red = delayed. The reader's eye is immediately drawn to the red segments to assess delay risk by ship mode.

**Mistake Avoided:** Did not use a line chart — shipping mode is a categorical dimension, not a time series. A line chart would imply a sequential relationship between Standard Class, Second Class, etc., which does not exist.

---

## Chart 6: Discount vs Profit — Scatter Plot

**Business Question Answered:** Does giving more discount hurt profit? At what discount level does the business start losing money?

**Why Scatter Plot:**
A scatter plot is the only chart type that can show the relationship (correlation) between two continuous variables — discount rate and profit — at the sub-category level simultaneously. It immediately reveals the negative correlation between high discounts and profit, making the business case for a discount policy review undeniable.

**Fields Used:**
- X-Axis: AVG(Discount) (measure)
- Y-Axis: AVG(Profit) (measure)
- Detail: Sub-Category (to create one dot per sub-category)
- Color: Category (Furniture/Technology/Office Supplies)
- Labels: Sub-Category names

**Design Principle Applied:** Each dot represents one sub-category — this level of granularity shows which specific products are most discount-sensitive without overwhelming the chart with 4,200 individual order dots. Color by category allows pattern detection across product groups.

**Mistake Avoided:** Did not plot every individual order (4,200 dots) — this creates an over-plotted, unreadable chart. Aggregating to sub-category level provides the right analytical resolution for executive decision-making.

---

## Chart 7: Return Analysis — Stacked Bar Chart

**Business Question Answered:** Which product categories have the highest return rates? Is return risk concentrated in any particular customer segment?

**Why Stacked Bar Chart:**
Return rate varies by both category and customer segment simultaneously. A stacked bar chart shows both dimensions — category return rate (bar length) and segment breakdown within each category (color segments). This allows leadership to identify if returns are concentrated in a specific segment-category combination.

**Fields Used:**
- Rows: Category (dimension)
- Columns: AGG(Return Rate) — calculated field
- Color: Customer Segment
- Labels: Return Rate percentage on each segment

**Design Principle Applied:** Percentage formatting on the axis makes the numbers immediately meaningful — "7.67% return rate for Furniture" is more actionable than raw counts. Leadership can directly compare against industry benchmarks.

**Mistake Avoided:** Did not use a pie chart to show return distribution. A pie chart cannot show both the magnitude of the problem (how high is the rate?) and the composition (which segment?) simultaneously. A bar chart does both.

---

## KPI Cards — Big Number Text Tiles

**Business Question Answered:** What is the single-number summary of business performance that leadership checks first?

**Why KPI Cards:**
KPI cards (large number text tiles) serve as the "scoreboard" at the top of the dashboard. Executives look at these first to understand whether the overall business is on track before diving into chart details. They answer the question "are we winning or losing?" in under 2 seconds.

**Fields Used:**
- KPI 1: SUM(Sales) → Total Sales = ₹21,70,17,651.92
- KPI 2: SUM(Profit) → Total Profit = ₹3,33,06,312.84
- KPI 3: AGG(Profit Margin) → Profit Margin = 15.35%

**Design Principle Applied:** Three metrics were selected that together tell a complete story: how much money came in (Sales), how much we kept (Profit), and how efficient we were (Margin). Adding a 4th or 5th KPI card would dilute attention.

**Mistake Avoided:** Did not include KPIs for metrics like "Number of Orders" or "Average Discount" at the top — these are operational metrics, not executive-level scorecards. Leadership cares about financial outcomes first.

---

## Dashboard-Level Design Decisions

| Design Decision | Rationale |
|---|---|
| Fixed layout 1200×800 | Ensures consistent rendering across devices; no scrolling required |
| Minimal color palette | Each color has one meaning (red = loss/risk, green = profit/good, blue = neutral) |
| All charts labeled | Leadership should not need to hover for basic values |
| 3 interactive filters | Region, Category, Segment — the three most common "slice" questions |
| Consistent font sizes | Hierarchy: Title (18pt) > Chart Title (12pt) > Labels (10pt) |
| No 3D charts | 3D charts distort perception of values — never used in professional dashboards |
| No pie charts | Angle comparison is cognitively harder than length comparison |

---

*Chart selection follows principles from Edward Tufte's "The Visual Display of Quantitative Information" and Stephen Few's "Show Me the Numbers."*
