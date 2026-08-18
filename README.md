# Fashion-Store-Marketing-Analysis

Analyze marketing performance, customer behavior, and revenue to identify growth opportunities and support data-driven decision-making.

# Market-Expansion-and-Product-Strategy

Use Power BI to analyze business data to identify new market opportunities and find strategic products.

## I. Introduction

### 1. Dataset

#### Orders Table

## 🧩 Dim_danh_sach_san_pham

| Column Name | Data Type | Description |
|------------------------|--------------|-------|
| Material | STRING | Material used to make the product (fabric, plastic, metal, etc.) |
| Category | STRING | Product group based on business classification |
| COGS | FLOAT | Production or purchasing cost of the product |
| Selling Price | FLOAT | Listed selling price of the product |
| Selling Price + VAT | FLOAT | Selling price including VAT |
| Purchase Price | FLOAT | Purchase price from the supplier |
| ID | INTEGER | Unique product identifier |
| Product Type | STRING | Product classification (e.g., fashion, electronics, household products) |
| Category Code | STRING | Product category identifier |
| Internal Category Code | STRING | Category code used in the internal system |
| Product Code | STRING | Unique SKU or product code |
| Barcode | STRING | Product barcode |
| margin % new | FLOAT | New profit margin calculated based on COGS and selling price |
| Color | STRING | Product color |
| Product Name | STRING | Display name of the product |
| Brand | STRING | Brand or manufacturer name |
| Status | STRING | Product status (active, discontinued, out of stock) |

---

### 💡 **Purpose**

> This table stores detailed information about **products**, including pricing, categories, brands, and physical characteristics.  
> It helps analyze **business performance**, **profit margins**, and **product trends**.

## 📊 Dim_mkt_camp_cost

| Column Name | Data Type | Description |
|--------------------------|--------------|-------|
| Campaign id | STRING | Marketing campaign identifier |
| Click | INTEGER | Number of clicks on advertisements |
| CPC | FLOAT | Average cost per click |
| CPM | FLOAT | Average cost per 1,000 impressions |
| CustomerType | STRING | Target customer type of the campaign |
| Campaign Budget Type | STRING | Budget classification (Branding, Conversion, Retargeting, etc.) |
| Impressions | INTEGER | Total number of ad impressions |
| Campaign Budget | FLOAT | Total budget allocated to the campaign |
| Date | DATE | Date when campaign data occurred or was recorded |
| Campaign Distribution | STRING | Advertising distribution channel (Facebook, Google, TikTok, etc.) |
| Amount Spent | FLOAT | Total amount spent on the campaign |
| Campaign Name | STRING | Marketing campaign name |

---

### 💡 **Purpose**

> This table stores general information about **marketing campaigns**, including budget, spending, impressions, and engagement performance.  
> It helps analyze **advertising performance**, **cost by channel**, and **return on investment (ROI)**.

---

# 💰 Fact_order

| Column Name | Data Type | Description |
|-----------------------|-----------|--------------|
| Ad/direct sales | STRING | Sales channel (advertising or direct sales) |
| Customer Level | STRING | Customer classification (VIP, loyal, new, etc.) |
| Discount | FLOAT | Discount value applied to the order |
| Product Category | STRING | Product group based on business classification |
| factData.Product Code | STRING | Product code linked to the factData table |
| Price | FLOAT | Actual selling price of the product |
| COGS | FLOAT | Cost of goods sold or production cost of the product |
| ID | INTEGER | Unique order identifier |
| Cancellation Reason | STRING | Reason for order cancellation, if any |
| Customer ID | STRING | Customer identifier |
| Product Code | STRING | Product SKU code in the order |
| Parent Product Code | STRING | Main product code, if the product is a variant or child version |
| Barcode | STRING | Product barcode |
| margin new | FLOAT | New profit margin calculated based on COGS and selling price |
| Source | STRING | Order source (website, Facebook, Shopee, etc.) |
| Ward/Commune | STRING | Detailed customer address (ward/commune) |
| District | STRING | Customer district |
| Product | STRING | Product name in the order |
| Birthday | DATE | Customer date of birth, if available |
| Quantity | INTEGER | Quantity of products purchased |
| Customer Name | STRING | Customer full name |
| Parent Product Name | STRING | Main product name, if it is a variant |
| City | STRING | Customer's city of residence |
| Time | DATE | Order date and time |
| Status | STRING | Order status (delivered, processing, cancelled, etc.) |

---

### 💡 **Purpose**

> This table stores detailed **order and customer data**, including product information, pricing, discounts, addresses, and order status.  
> It helps analyze **revenue, profit, purchasing behavior**, and **sales channel performance**.

---

## 📈 Fact_mkt_camp_by_sku_cost

| Column Name | Data Type | Description |
|-----------------------------|-----------|--------------|
| Comments by AM | INTEGER | Number of comments according to the Account Manager |
| Inbox + Comments by AM | INTEGER | Total messages and comments according to the Account Manager |
| Inbox by AM | INTEGER | Number of messages according to the Account Manager |
| Spend by Product | FLOAT | Advertising cost for each product |
| Post Running Date | DATE | Date when the advertisement was run by post |
| Post Comments | INTEGER | Total comments on the advertising post |
| Campaign id | STRING | Marketing campaign identifier |
| Click | INTEGER | Number of clicks on advertisements |
| Click by AM | INTEGER | Number of clicks according to the Account Manager |
| Cost/Result by AM | FLOAT | Cost per result according to the Account Manager |
| CPC | FLOAT | Cost Per Click |
| CPC by AM | FLOAT | CPC according to the Account Manager |
| CPM | FLOAT | Cost Per Mille – Cost per 1,000 impressions |
| CPM by AM | FLOAT | CPM according to the Account Manager |
| CTR | FLOAT | Click-Through Rate |
| CTR by AM | FLOAT | CTR according to the Account Manager |
| Currency | STRING | Currency used (VND, USD, etc.) |
| Selling Price | FLOAT | Selling price of the product related to the campaign |
| Existing Customers by AM | INTEGER | Number of existing customers according to the Account Manager |
| New Customers by AM | INTEGER | Number of new customers according to the Account Manager |
| Started Conversations | INTEGER | Number of conversations initiated through advertisements |
| Campaign Budget Type | STRING | Budget classification (Branding, Conversion, etc.) |
| Impressions | INTEGER | Total number of ad impressions |
| Impressions by AM | INTEGER | Number of impressions according to the Account Manager |
| Product Code | STRING | SKU code of the product related to the campaign |
| Campaign Budget | FLOAT | Total marketing campaign budget |
| Product Budget | FLOAT | Budget allocated to each product |
| Date | DATE | Date when campaign cost or performance was recorded |
| Campaign Distribution | STRING | Advertising distribution channel (Facebook, Google, etc.) |
| Allocated Units Sold | INTEGER | Number of units sold allocated to each campaign |
| Total Units Sold | INTEGER | Total number of products sold |
| Stock Quantity | INTEGER | Inventory quantity related to the campaign |
| Amount Spent (VND) | FLOAT | Total campaign spending in VND |
| Post Name | STRING | Name of the advertising post |
| Campaign Name | STRING | Marketing campaign name |
| Product Name | STRING | Product name related to the campaign |
| Product Name 2 | STRING | Additional product name or another version |
| New Messages | INTEGER | Number of new messages generated from the campaign |
| Total Comments on Product | INTEGER | Total number of comments on the product |
| Total Units Sold by Campaign | INTEGER | Total number of units sold by campaign |

---

### 💡 **Purpose**

> This table stores detailed data on **marketing campaign performance by SKU**, including cost, impressions, engagement, and sales.  
> It helps analyze **advertising performance** and **optimize budget allocation** for each product.

### 🔗 **Data Relationships**

<img width="1112" height="343" alt="image" src="https://github.com/user-attachments/assets/a01be390-3388-4ef3-8790-bf0b9e75ed09" />

### 🔗 **Relationship Structure**

- **Dim_mkt_camp_cost (1)** → **Fact_mkt_camp_by_sku_cost (*)**  
  → Relationship based on `Campaign id` to analyze campaign cost and performance.

- **Dim_danh_sach_san_pham (1)** → **Fact_mkt_camp_by_sku_cost (*)**  
  → Relationship based on `Product Code` to compare advertising performance by product.

- **Dim_danh_sach_san_pham (1)** → **Fact_order (*)**  
  → Relationship based on `Product Code` to analyze actual revenue and profit.

---

### 2. Problem to Be Solved

Build a tactical report to help company leaders understand the marketing budget spending process and campaign performance, link sales revenue with marketing spending, and optimize marketing budget performance based on KPIs. From there, propose tactics to improve performance.

## II. Design Thinking

## STEP 1: Empathize

<img width="1176" height="627" alt="image" src="https://github.com/user-attachments/assets/1df5b4e0-bc87-4230-b910-310893790a87" />

<img width="1060" height="643" alt="image" src="https://github.com/user-attachments/assets/c748daeb-b301-4a46-b95c-d2907f2bdfcd" />

## STEP 2: Define POV

<img width="1344" height="639" alt="image" src="https://github.com/user-attachments/assets/4c8497b9-c58f-4937-9d02-61bb25af4fde" />

<img width="1266" height="584" alt="image" src="https://github.com/user-attachments/assets/14e01408-42f4-4b40-97be-790169b44ed4" />

## STEP 3: Ideate

<img width="1792" height="570" alt="image" src="https://github.com/user-attachments/assets/e34ba597-d8b6-4f19-8e44-dd4d947f3411" />

## STEP 4: Prototype and Review

Choose the type of chart suitable for the questions.

Presentation and layout of each part of the report (size, chart arrangement, etc.).

Choose the color of the report.

Self-review and edit the report.

## III. VISUALIZATION

## OVERVIEW

<img width="1325" height="719" alt="image" src="https://github.com/user-attachments/assets/1e99c1ca-2ae9-4541-8f7e-b25b0c4c7d2a" />

## CAMPAIGN

<img width="1032" height="685" alt="image" src="https://github.com/user-attachments/assets/55ed8707-7279-46bc-9103-e4da74fa216f" />

<img width="1037" height="682" alt="image" src="https://github.com/user-attachments/assets/909051d6-7fe1-409f-aea0-20c6e7aeca42" />

<img width="1072" height="678" alt="image" src="https://github.com/user-attachments/assets/ba7c52bb-1cbd-4765-8756-7364ca6d0ada" />

## PRODUCT ANALYSIS

<img width="1103" height="695" alt="image" src="https://github.com/user-attachments/assets/836f4472-1dc7-4f05-aaff-21d26e0a93b9" />

## IV. INSIGHT AND RECOMMENDATION

## I. Insight

### 1. Campaign Insight: Lookalike

**Overview:** Lookalike recorded a loss of approximately **107.9 billion**. The main reason did not come from high advertising costs or high COGS, but from Lookalike focusing on products with an order value approximately **200K lower** than the other two segments.

AOV was only **1.17M**, while COGS per order was approximately **1.14M**, resulting in only around **30–50K gross margin per order**, which was not enough to cover the **130–180K advertising cost per order**.

Therefore, the more the budget was scaled, the more the losses increased.

**AUDREY SHIRT:** Recorded a loss of approximately **108M for four consecutive weeks** and was the campaign with the largest impact on the entire segment. Spend increased from W2 to W3 instead of being turned off, indicating that the campaign may have been optimized for revenue rather than profit.

**NALANI & MIRENA SKIRT:** Recorded a loss of approximately **15M in W2 and W3**, with negative margin per order ranging from **50K to 139K**. The campaign was turned off after W3, which was an appropriate decision.

**Campaigns with stable positive profit:** FLOWERS MAKE MY DAY achieved **2.57M in W1, 2.36M in W2, and 4.69M in W3**, showing the most sustainable performance. YOU DESERVE THE MOST BEAUTIFUL THINGS also maintained positive profit from W1 to W3. DELIA SET, MACY JUMPSUIT, MELI DRESS, and KATY DRESS all recorded profit from W4 to W5.

**Conclusion:** Lookalike was not completely ineffective but was dragged down by several campaigns with large losses. AUDREY SHIRT was the main problem due to unsuitable COGS, causing each order to generate negative profit. Continuing to scale the campaign caused the losses to increase more rapidly.

**System Issue:** A negative margin per order of approximately **140K** is an issue related to the product pricing structure and does not directly depend on advertising. In addition, the campaign had already had ROAS below the break-even threshold since W2 but continued to scale for three weeks. Setting up automated alerts when ROAS falls below the threshold or Profit becomes negative could help significantly limit losses.

### 2. Campaign Insight: Open/Cold

AUDREY SHIRT not only affected Lookalike but also had a negative impact on Open/Cold.

Some other campaigns with large losses included **TH 5.5 NEW ARRIVAL, STAY ELEGANT, FABRIC FOR SUMMER, NEVA SHIRT & ZUZIE SHORT, and SERINA & MANDY OUTFIT OF TODAY**.

The common pattern was that new campaigns were launched with negative margins and then heavily scaled before profitability issues were identified.

**Notable Hero campaigns:** AVIAN DRESS achieved **9.79M**, KATY DRESS achieved **7.49M**, and DANICA DRESS achieved **5.65M** in W3. MARGNET DRESS achieved **15.67M** in W4. LISA DRESS achieved **9.94M and 5.24M**, while NEVIN DRESS achieved **6.37M** in W5.

**Conclusion:** Open/Cold has the ability to generate high profit when combined with the right products, but overall performance was affected by negative-margin campaigns running simultaneously.

### 3. Campaign Insight: Retargeting

AUDREY SHIRT appeared in all three segments and negatively affected the entire system. TH 5.5 NEW ARRIVAL was the campaign with the second-largest impact, especially in Retargeting.

In W3, the Hero campaigns included **AVIAN, KATY, and DANICA** in Open/Cold and **SENSE OF ELEGANCE, LUCIE DRESS, and VERENA SET** in Retargeting. Open/Cold had more strong Hero campaigns and therefore had a greater ability to offset losses.

**Retargeting Paradox:** In theory, Retargeting has the potential to generate higher profit than Open/Cold due to higher conversion, lower advertising cost per order, and comparable AOV. However, in reality, Retargeting suffered significant losses because it focused on retargeting products with negative margins.

**TH 5.5 NEW ARRIVAL** is a typical example, recording a loss of **8.36M in W2 Retargeting**, while Open/Cold for the same campaign recorded a loss of only **4.38M**.

### 4. Product Insight

**Categories to Stop:** Áo Tách Set and Chân Váy Tách Set had negative margins and were the main reasons why Lookalike recorded large losses.

**Categories to Scale:** Set Váy Áo had the highest margin at **0.37** and an AOV of **1.9M**. Váy Chiết Eo Xoè had a margin of **0.25** and the highest revenue in Open/Cold. These are the two categories with strong potential to generate profit.

**Brand:** Hoa was the only brand with positive profit. Trừu Tượng recorded a loss of approximately **0.2bn** despite having a margin close to zero, showing that using volume to compensate for low margins is not sustainable.

**Retargeting SKU:** Green Flower Set had the highest margin at **0.35** but was not fully utilized. Nelia Set and Delia Set were the two best-performing SKUs.

## II. Recommendation Based on ROAS/ROI

**High ROAS, Positive ROI**  
→ Scale the budget in a controlled manner (**increase by 10–20%**) while maintaining the current creative and targeting.

**High ROAS, Negative ROI**  
→ Optimize **CPM/CPC**, conduct **creative A/B testing**, or adjust the **product price** before scaling.

**Low ROAS, Positive ROI**  
→ Expand the **customer audience** or slightly increase the budget to test growth potential.

**Low ROAS, Negative ROI**  
→ Temporarily pause or significantly reduce the budget, re-analyze the target and creative, and only continue when there is a clear improvement.
