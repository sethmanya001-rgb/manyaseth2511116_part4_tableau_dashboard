# Dashboard Story — Executive Sales Performance Dashboard

**Prepared for:** Senior Leadership Team
**Period Covered:** January 2024 – December 2025
**Prepared by:** Business Analyst
**Tool:** Tableau Desktop 2026.2

---

## Executive Summary

The Executive Sales Performance Dashboard provides a comprehensive view of the company's retail business across ₹21.7 Crore in total sales and ₹3.33 Crore in profit, representing a 15.35% overall profit margin. The dashboard covers 4,200 orders across 4 regions, 3 customer segments, 3 product categories, and 4 shipping modes over a 24-month period.

The headline story is one of **technology-driven profitability, geographic concentration risk, and a discount problem that is silently eroding margins.** The business is healthy overall, but several structural issues require leadership attention before they become material risks.

---

## What Is Performing Well

### 1. Technology Is a Profit Engine
Technology category alone generates ₹2.80 Crore in profit — that is 84% of total company profit from a category that represents 70% of total sales. Sub-categories like Copiers (₹73 Lakh profit), Accessories (₹71 Lakh), and Phones (₹70 Lakh) are consistently high performers. These products carry strong margins and appear to be resilient to discount pressure compared to other categories.

### 2. South Region Shows Strongest Momentum
The South region leads all four regions with ₹6.47 Crore in sales, outperforming the next-best region (North at ₹5.46 Crore) by 18.6%. This suggests that South either has stronger market penetration, a better-performing sales team, or higher customer density in profitable segments.

### 3. Revenue Is Well-Distributed Across Customer Segments
All three customer segments — Home Office (₹7.45 Crore), Consumer (₹7.19 Crore), and Corporate (₹7.06 Crore) — contribute roughly equally to total revenue. This diversification is a business strength; the company is not overly dependent on any single segment.

### 4. Organic Channel Demonstrates Brand Strength
40.9% of total revenue comes through the Organic channel — a strong signal that the brand has genuine market pull without requiring heavy paid acquisition spend. This is a valuable competitive asset.

---

## What Is Underperforming

### 1. Office Supplies Delivers Minimal Profit Despite Volume
Office Supplies generates only ₹17 Lakh in profit on ₹1.15 Crore in sales — a thin margin of approximately 14.8%. While the category drives transaction volume, it is not contributing proportionally to profitability. This suggests the category may be heavily discounted or carrying high fulfilment costs.

### 2. East Region Consistently Lags
East region at ₹4.89 Crore in sales is the weakest performer alongside West (₹4.89 Crore), both trailing South by over ₹1.5 Crore. If East has similar market potential but lower sales, it points to an execution gap rather than a market gap.

### 3. Bottom Sub-Categories Are Margin Drags
Sub-categories including Binders (₹3.26 Lakh profit), Storage (₹3.42 Lakh), Paper (₹3.19 Lakh), and Art (₹3.50 Lakh) generate minimal profit despite occupying SKU space, warehouse capacity, and sales team attention. These may be "catalogue fillers" that exist for customer convenience but do not contribute to business health.

---

## What Risks Are Visible

### 1. Discount Policy Is Destroying Profit at the Margin
The scatter plot analysis reveals a clear and concerning pattern: orders with discounts above 30% generate negative average profit (₹-1,601 per order). This means the company is actively losing money on a subset of its transactions. If the sales team is using discounts as a primary closing tool, this is a systemic risk that will worsen as competitive pressure increases.

### 2. Furniture Return Rate Is Elevated at 7.67%
The Furniture category has a return rate of 7.67% — more than twice the Technology return rate. Returns represent direct cost (reverse logistics, restocking, lost margin) and indirect cost (customer dissatisfaction, reduced lifetime value). At 4,200 orders, even a 1% reduction in return rate saves significant operational cost.

### 3. Standard Class Shipping Carries Delay Risk
Standard Class handles 58% of all orders but shows the highest proportion of delayed deliveries in the shipping delay bucket analysis. Customer ratings may be negatively correlated with Standard Class delays — a risk to repeat purchase rates and long-term revenue.

### 4. Revenue Concentration in Technology Is a Single-Point Risk
With 84% of profit coming from Technology, any supply chain disruption (global chip shortage, logistics delay, regulatory change on electronics) could materially impact the company's bottom line within a single quarter.

---

## What Opportunities Are Visible

### 1. Corporate Segment Is Under-Indexed — Significant Upside
At ₹7.06 Crore, Corporate is the lowest revenue segment despite typically offering the highest deal values, lowest acquisition costs, and most predictable revenue through contracts. A focused B2B sales motion with volume-based incentives could move Corporate from 32% to 38% of revenue within 12 months.

### 2. Referral Channel Is Underinvested
The Referral channel generates ₹2.12 Crore in sales but likely has the lowest Customer Acquisition Cost of any channel. A structured referral incentive program (e.g., discount on next purchase for both referrer and referee) could amplify this channel significantly with minimal incremental spend.

### 3. Cross-Selling Accessories to Technology Buyers
Accessories is the second-most profitable sub-category at ₹71 Lakh. If every Copier or Phone buyer is presented with an Accessories recommendation at checkout, attach rates could meaningfully increase average order value and total profit.

### 4. East Region Has the Most Room for Growth
Since East region lags despite presumably similar market conditions to other regions, a targeted intervention — additional sales headcount, revised incentive structure, or focused marketing campaigns — could unlock ₹1–2 Crore in incremental annual revenue.

---

## Recommended Business Actions

| Priority | Action | Expected Impact | Owner |
|---|---|---|---|
| 1 | Implement discount approval policy above 20% | Recover ₹50–80 Lakh in lost annual profit | Sales Director |
| 2 | Launch Corporate B2B sales motion | +₹1–1.5 Crore incremental revenue | Sales & Marketing |
| 3 | Investigate and address Furniture returns | Reduce return rate from 7.67% to below 5% | Product & Ops |
| 4 | East region performance review | Identify and close execution gap | Regional Manager |
| 5 | Build referral incentive program | Grow referral revenue by 30–40% | Marketing |
| 6 | Cross-sell Accessories with Tech products | Increase AOV by 8–12% | Sales Ops |

---

## Limitations of the Dashboard

1. **No customer-level data:** The dashboard shows segment-level performance but cannot identify individual high-value customers or churn risk at a customer level.
2. **No cost of goods data:** Profit figures are calculated as Sales minus Discount but do not include COGS, logistics costs, or marketing spend — actual net margins may differ.
3. **Return reasons not captured:** The return_flag field identifies that a return occurred but does not capture the reason (quality issue, wrong item, buyer's remorse), limiting root cause analysis.
4. **Campaign channel attribution:** Campaign channel data may have attribution gaps — Organic channel could include orders that were influenced by Paid or Social campaigns but converted without clicking a tracked link.
5. **Static snapshot:** The dashboard reflects 2024–2025 historical data. It does not include forward-looking forecasts or real-time data feeds.

---

## Suggested Next Analysis

1. **Customer Cohort Analysis:** Identify retention rates and lifetime value by segment and acquisition channel to prioritize where to invest in customer success.
2. **Product-Level Margin Analysis:** Deep dive into individual SKU profitability within Technology to identify which specific products drive margins versus which are drag.
3. **Shipping Delay vs. Customer Rating Correlation:** Quantify how much each additional day of delivery delay reduces customer rating scores and subsequent repeat purchase probability.
4. **Discount Elasticity Study:** Analyze whether orders with 10–20% discounts close at higher volumes than 0–10% discounts, to determine the revenue-profit optimal discount level.
5. **Geographic Expansion Analysis:** Map current customer density by state to identify white-space geographies where the company has low penetration but high market potential.

---

*This dashboard story is intended for strategic decision-making by the leadership team. Data covers the period January 2024 to December 2025. All figures in Indian Rupees (₹).*
