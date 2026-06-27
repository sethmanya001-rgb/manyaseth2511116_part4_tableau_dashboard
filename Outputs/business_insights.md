# Business Insights — Executive Sales Performance Dashboard

**Dataset:** dashboard_sales_data.xlsx | **Period:** January 2024 – December 2025 | **Total Records:** 4,200 orders

---

## Calculated Fields Used

| Field | Formula | Purpose |
|---|---|---|
| Profit Margin | SUM([Profit]) / SUM([Sales]) | Measures profitability efficiency |
| Cost | SUM([Sales]) - SUM([Profit]) | Identifies cost structure |
| Avg Order Value | SUM([Sales]) / COUNTD([Order ID]) | Tracks customer spend per order |
| Return Rate | SUM([Return Flag]) / COUNT([Order ID]) | Flags quality/service risk |
| Shipping Delay Bucket | IF [Delivery Days] <=2 THEN "Fast" ELSEIF [Delivery Days] <=5 THEN "Normal" ELSE "Delayed" END | Categorizes delivery performance |

---

## Insight 1: Sales Trend — Consistent Growth with Seasonal Peaks

**Observation:** Total sales reached ₹21.7 Crore over the 2024–2025 period, with a visible peak in late 2025 reaching ₹1.08 Crore in a single month.

**Data Evidence:** Monthly sales ranged from a low of ₹63 Lakh to a high of ₹1.08 Crore. The average monthly sales line sits at approximately ₹85–90 Lakh.

**Business Interpretation:** The business shows consistent revenue generation, with Q4 2025 showing the strongest performance — likely driven by year-end procurement cycles in corporate and government accounts.

**Recommended Action:** Plan inventory and staffing 6–8 weeks before Q4 to capitalize on peak demand. Investigate low-performing months to identify if they correlate with supply chain gaps or campaign inactivity.

---

## Insight 2: Regional Performance — South Leads, East Underperforms

**Observation:** South region is the top-performing region with ₹6.47 Crore in sales, followed by North (₹5.46 Crore), West (₹4.89 Crore), and East (₹4.89 Crore).

**Data Evidence:**
- South: ₹6,46,93,706.73
- North: ₹5,45,55,800.53
- West: ₹4,89,08,980.24
- East: ₹4,88,59,164.42

**Business Interpretation:** South region outperforms East by 32%, indicating stronger customer relationships, better sales coverage, or higher demand density in that geography.

**Recommended Action:** Conduct a root cause analysis on East region — evaluate sales team performance, customer concentration, and competitor presence. Replicate South region's sales playbook in East.

---

## Insight 3: Category Profitability — Technology Dominates, Office Supplies Underperforms

**Observation:** Technology contributes ₹2.80 Crore in profit (84% of total profit), while Office Supplies contributes only ₹17 Lakh despite being a high-volume category.

**Data Evidence:**
- Technology Profit: ₹2,80,43,309.91
- Furniture Profit: ₹35,57,835.43
- Office Supplies Profit: ₹17,05,167.50

**Business Interpretation:** Technology products deliver significantly higher margins. Office Supplies likely suffers from deep discounting and high competition, making it a volume play rather than a profit driver.

**Recommended Action:** Increase focus on Technology upselling to existing customers. Review Office Supplies pricing strategy — consider reducing discount depth or bundling with high-margin tech accessories.

---

## Insight 4: Sub-Category Profitability — Copiers & Phones Drive Profit, Binders & Storage Are Laggards

**Observation:** Top 4 profitable sub-categories (Copiers, Accessories, Phones, Machines) contribute the majority of profit. Bottom sub-categories like Binders, Storage, Paper, and Art generate minimal returns.

**Data Evidence:**
- Copiers: ₹73,10,055.11 profit
- Accessories: ₹71,86,862.70 profit
- Phones: ₹70,97,290.89 profit
- Binders: ₹3,25,668.13 profit
- Storage: ₹3,42,231.21 profit

**Business Interpretation:** The business has a "star product" concentration risk — if Copiers or Phones face supply disruption, overall profitability takes a significant hit.

**Recommended Action:** Develop Accessories as a cross-sell companion to Copiers and Phones. Consider discontinuing or repricing Storage and Binders if they do not serve a strategic bundling purpose.

---

## Insight 5: Customer Segment — Home Office Leads Revenue, All Segments Profitable

**Observation:** Home Office is the highest revenue segment at ₹7.45 Crore, closely followed by Consumer (₹7.19 Crore) and Corporate (₹7.06 Crore).

**Data Evidence:**
- Home Office: ₹7,45,00,746.01
- Consumer: ₹7,18,86,173.19
- Corporate: ₹7,06,30,732.72

**Business Interpretation:** Revenue is well-distributed across all three segments, indicating healthy customer diversification. However, Corporate segment typically offers larger deal sizes and long-term contracts — it may be underutilized.

**Recommended Action:** Launch a dedicated B2B sales motion targeting Corporate accounts. Offer volume-based pricing or annual contracts to increase Corporate share from 32% to 38% of revenue.

---

## Insight 6: Discount Impact — High Discounts Destroy Profit

**Observation:** As discount levels increase beyond 30%, average profit per order turns negative.

**Data Evidence:**
- Discount 0–10%: Avg Profit ₹10,010 per order
- Discount 10–20%: Avg Profit ₹6,336 per order
- Discount 20–30%: Avg Profit ₹3,181 per order
- Discount 30–50%: Avg Loss ₹1,601 per order

**Business Interpretation:** Discounts above 30% are loss-generating. Sales team may be using excessive discounts to close deals, which erodes company profitability without a proportional increase in volume.

**Recommended Action:** Implement a discount approval policy — any discount above 20% requires manager sign-off. Introduce value-based selling training to reduce discount dependency.

---

## Insight 7: Shipping Performance — Standard Class Dominates but Has Highest Delay Risk

**Observation:** Standard Class accounts for 2,435 orders (58% of all orders), while Same Day shipping is used for only 241 orders (5.7%).

**Data Evidence:**
- Standard Class: 2,435 orders
- Second Class: 894 orders
- First Class: 630 orders
- Same Day: 241 orders

**Business Interpretation:** Most customers are comfortable with Standard Class shipping, but this mode likely carries the highest delay risk based on delivery day distribution. Delayed shipments negatively impact customer ratings and increase return probability.

**Recommended Action:** Set SLA benchmarks for Standard Class (e.g., max 5 days). Alert operations team when orders exceed the benchmark. Promote First Class upgrade offers to high-value customers to improve satisfaction.

---

## Insight 8: Return Patterns — Furniture Has Highest Return Risk (7.67%)

**Observation:** Furniture category has a return rate of 7.67%, which is more than double the Technology return rate of 3.03%.

**Data Evidence:**
- Furniture Return Rate: 7.67%
- Office Supplies Return Rate: 3.65%
- Technology Return Rate: 3.03%
- Overall Return Rate: 4.55%

**Business Interpretation:** High Furniture return rates signal potential quality issues, poor product-market fit, or mismatched customer expectations (e.g., size, color, assembly difficulty). Every return costs the company in reverse logistics and lost profit.

**Recommended Action:** Conduct exit surveys on returned Furniture orders to identify root causes. Improve product descriptions and 3D visualization on the sales platform. Set a return rate KPI target of below 5% for Furniture by Q2 2026.

---

## Insight 9: Campaign Channel — Organic Drives Majority of Revenue

**Observation:** Organic channel contributes ₹8.88 Crore in sales (40.9% of total), significantly outperforming Paid (₹4.01 Crore) and Social (₹3.11 Crore).

**Data Evidence:**
- Organic: ₹8,87,83,980.90
- Paid: ₹4,01,11,108.72
- Email: ₹3,45,12,356.53
- Social: ₹3,11,04,556.50
- Referral: ₹2,12,11,566.38

**Business Interpretation:** Strong organic performance indicates good brand recognition and word-of-mouth. However, over-reliance on organic (40.9%) is a risk — any SEO algorithm change or brand reputation issue could significantly impact revenue.

**Recommended Action:** Diversify customer acquisition by increasing investment in Email and Referral programs, which have lower CAC (Customer Acquisition Cost) compared to Paid. Build a referral incentive program targeting existing Home Office and Corporate customers.

---

*Document prepared by: Business Analyst | Dashboard Tool: Tableau Desktop 2026.2 | Last Updated: June 2026*
