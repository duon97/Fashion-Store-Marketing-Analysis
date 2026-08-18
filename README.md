# Fashion Store Marketing Analysis

> Analyze marketing performance, customer behavior, and revenue to uncover growth opportunities and support data-driven decision making.

---

## I. Dataset Overview

### Data Model

The project uses a star schema with the following tables:

**Dim_danh_sach_san_pham** — Product dimension table storing product details including price, category, brand, and margin.

**Dim_mkt_camp_cost** — Campaign cost dimension table storing budget, impressions, clicks, and channel distribution.

**Fact_order** — Order fact table storing transaction details including revenue, cost, discount, and customer information.

**Fact_mkt_camp_by_sku_cost** — Campaign-SKU fact table storing detailed ad performance metrics per product including spend, clicks, CTR, CPM, and sales volume.

### Relationships
- `Dim_mkt_camp_cost (1)` → `Fact_mkt_camp_by_sku_cost (*)` via `Campaign id`
- `Dim_danh_sach_san_pham (1)` → `Fact_mkt_camp_by_sku_cost (*)` via `Mã Sản phẩm`
- `Dim_danh_sach_san_pham (1)` → `Fact_order (*)` via `Mã Sản phẩm`

---

## II. Business Problem

Build a tactical report to help company leadership:
- Understand budget spending and campaign performance
- Link sales revenue to marketing spend
- Optimize marketing budget efficiency based on KPIs
- Propose tactical improvements to campaign performance

---

## III. Design Thinking Approach

### Step 1 — Empathize
Identified key stakeholders (CMO, Marketing Manager) and their core questions around budget efficiency, campaign profitability, and product-level performance.

### Step 2 — Define Point of View
Defined 4 analytical perspectives:
- Overall campaign performance by week
- Performance by CustomerType (Lookalike / Open/Cold / Retargeting)
- Product and category-level margin analysis
- Campaign-level profit and ROAS ranking

### Step 3 — Ideate
Brainstormed metrics and chart types for each perspective, structured into 3 information tiers per page: critical → important → detail.

### Step 4 — Prototype & Review
Selected chart types, defined layout and color scheme, self-reviewed and refined the report before final delivery.

---

## IV. Dashboard

### Overview Page
Displays total Profit Ads, Ad Revenue, ROI, Total Spend, and Total Budget with weekly trend analysis and top/worst campaign ranking.

### Campaign Detail Pages (by CustomerType)
Each page shows Click, Impression, Revenue, Profit, and KPI table (AOV, Margin/order, Ads/order) broken down by week — with a Campaign Insight summary box.

### Product Analysis Page
Covers Revenue × AOV × Margin % by category and CustomerType, Profit × Margin by brand, and top SKU performance for Retargeting upsell opportunities.

---

## V. Key Insights

### Lookalike — Loss of ~107.9B VND
The root cause is not high ad spend or high COGS, but rather that Lookalike audiences are purchasing lower-value products (~200K lower AOV than other groups). With AOV at 1.17M and COGS/order at ~1.14M, gross margin per order is only 30–50K — insufficient to cover ad cost of 130–180K/order. Scaling budget amplifies the loss.

**AUDREY SHIRT** is the primary driver — generating ~108M in losses over 4 consecutive weeks while spend continued to increase, suggesting optimization was targeting revenue rather than profit.

Campaigns with consistent positive profit: **FLOWERS MAKE MY DAY**, **YOU DESERVE THE MOST BEAUTIFUL THINGS**, and **DELIA SET / MACY JUMPSUIT / MELI DRESS / KATY DRESS** in W4–W5.

### Open/Cold — Mixed Performance
Strong hero campaigns (AVIAN DRESS, KATY DRESS, DANICA DRESS, MARGNET DRESS) delivered significant profit but were offset by campaigns launched with negative margin that were scaled before profitability issues were identified (TH 5.5 NEW ARRIVAL, STAY ELEGANT, FABRIC FOR SUMMER).

### Retargeting — The Profitability Paradox
Retargeting theoretically should outperform Open/Cold (higher conversion, lower CPA, comparable AOV). However, it underperformed due to retargeting products with negative margin — notably **TH 5.5 NEW ARRIVAL** which lost 8.36M in W2 vs. 4.38M for the same campaign in Open/Cold.

### Product Analysis
| Action | Category / Brand / SKU |
|---|---|
| Stop immediately | Áo Tách Set, Chân Váy Tách Set (negative margin) |
| Scale | Set Váy Áo (margin 0.37, AOV 1.9M), Váy Chiết Eo Xoè (highest revenue in Open/Cold) |
| Increase budget | Brand Hoa (only profitable brand) |
| Stop | Brand Trừu Tượng (loss of ~0.2bn despite near-zero margin) |
| Retarget upsell | Green Flower Set (highest margin 0.35, underinvested), Nelia Set, Delia Set |

---

## VI. Recommendations

| Scenario | Action |
|---|---|
| High ROAS + Positive ROI | Scale budget 10–20%, maintain current creative and targeting |
| High ROAS + Negative ROI | Optimize CPM/CPC, A/B test creatives, or adjust product pricing before scaling |
| Low ROAS + Positive ROI | Expand audience or increase budget moderately to test growth potential |
| Low ROAS + Negative ROI | Pause or significantly reduce budget, re-analyze targeting and creative |

**System-level recommendation:** Set up automated alerts when ROAS drops below breakeven threshold or Profit turns negative — this alone could have prevented the majority of losses observed in this dataset.

---

## VII. Tools Used
- Power BI (data modeling, DAX, dashboard)
- Excel (data cleaning, validation)
- SQL (exploratory analysis)
