# 📊 Superstore Data Analysis — Weekend Data Challenges

This repository contains my analysis of the **Superstore dataset** through a series of Weekend Data Challenges.

The first challenge focused on **profitability and business performance**, the second explored **sales trends, seasonality, and year-over-year growth**, and the third dug into **who the business's best customers actually are**.

---

## 📂 Dataset

The **Superstore Dataset Final** was used for all three challenges.

**Source:** Kaggle — Superstore Dataset Final

The dataset contains **9,994 retail order records** with information about:

* Order dates
* Products
* Categories
* Regions
* Customers
* Segments
* Sales
* Discounts
* Profit
* Quantity

---

# 🔥 Challenge #01 — What Is Actually Profitable?

## 🎯 Objectives

The first challenge investigated:

1. Which products and categories are the most profitable?
2. Which region performs best?
3. Which products have high sales but low profit?

## 1. Most Profitable Products & Categories

Profit was aggregated by **Category** and **Product Name**.

### Key findings

* **Technology** was the most profitable category.
* **Canon imageCLASS 2200 Advanced Copier** was the most profitable product.

## 2. Best-Performing Region

Sales, quantity, and profit were aggregated by region.

The **West region** generated the highest total profit.

The **Coefficient of Variation (CV)** was also calculated to compare the relative variation of Sales, Quantity, and Profit across regions.

### Key finding

> **Profit showed the highest relative variation across regions compared with Sales and Quantity.**

## 3. High Sales but Low Profit

Products were analyzed using:

* Total Sales
* Total Profit
* Average Discount
* Profit Margin

Profit margin was calculated as:

```text
Profit Margin = Profit / Sales × 100
```

Several products had negative profit margins.

Among the high-sales products, the **Cisco TelePresence System EX90 Videoconferencing Unit** stood out because it generated substantial sales while still having a negative profit margin.

## 🕵️ Mystery Question

### What looked successful but wasn't?

The **Cisco TelePresence System EX90 Videoconferencing Unit** appeared successful because of its high sales, but its negative profit margin showed that high revenue did not necessarily translate into profitability.

---

# 📈 Challenge #02 — When Does This Business Actually Make Its Money?

## 🎯 Objectives

The second challenge used the `Order Date` column to investigate:

1. Monthly sales trends
2. Seasonal patterns
3. Year-over-year growth
4. A month that initially looks problematic but is actually normal

## 1. Monthly Sales Trend

Sales were aggregated by month from **2014 to 2017**.

The results show substantial variation throughout the period, with sales generally becoming stronger toward the later part of the year.

### Key finding

> Sales show noticeable seasonal fluctuations, with stronger performance generally occurring toward the end of the year.

## 2. Seasonality

Average sales were calculated for each calendar month across all available years.

### Key findings

* **November** had the highest average sales: **88,115.27**
* **December** was the second strongest: **81,323.38**
* **September** also showed strong performance: **76,912.49**
* **February** had the lowest average sales: **14,937.81**

Overall, sales tend to strengthen significantly toward the end of the year.

## 3. Year-over-Year Growth

Annual sales growth was calculated to understand how the business changed over time.

| Year |  YoY Growth |
| ---- | ----------: |
| 2014 |           — |
| 2015 |  **-2.83%** |
| 2016 | **+29.47%** |
| 2017 | **+20.36%** |

### Key findings

* Sales declined by **2.83% in 2015**.
* Sales increased by **29.47% in 2016**.
* Sales increased by **20.36% in 2017**.

The business experienced a small decline in 2015 followed by strong growth in 2016 and 2017.

---

# 🕵️ Challenge #02 Mystery

## What looks like a problem but is actually normal?

**February** initially looks problematic because it repeatedly records relatively low sales.

| Year | February Sales |
| ---- | -------------: |
| 2014 |       4,519.89 |
| 2015 |      11,951.41 |
| 2016 |      22,978.82 |
| 2017 |      20,301.13 |

However, the lower performance occurs consistently across multiple years.

### 💡 Insight

> **February's low sales appear to be a predictable seasonal pattern rather than an unexpected business failure.**

A recurring seasonal decline should therefore be planned for rather than treated as an unexpected crisis.

---

# 👥 Challenge #03 — Who Are This Business's Best Customers?

## 🎯 Objectives

The third challenge used the `Customer Name` and `Segment` columns to investigate:

1. Which customers drive the most sales, profit, and orders?
2. Who are the top 10 customers by total sales?
3. Who are the top 10 customers by order frequency?
4. Which segment performs best by sales and profit?
5. Is the biggest spender actually the most valuable customer?

## 1. Customer-Level Aggregation

Customers were grouped to calculate total sales, total profit, and order count:

```text
customer_detail = df.groupby('Customer Name').agg(
    sales=('Sales','sum'),
    profit=('Profit','sum'),
    order=('Order ID','nunique')
)
```

## 2. Top 10 Customers by Sales

| Customer | Sales | Profit | Avg Discount |
| --- | ---: | ---: | ---: |
| Sean Miller | 25,043.05 | **-1,980.74** | 24.7% |
| Tamara Chand | 19,052.22 | 8,981.32 | 11.7% |
| Raymond Buch | 15,117.34 | 6,976.10 | 9.4% |
| Tom Ashbrook | 14,595.62 | 4,703.79 | 8.0% |
| Adrian Barton | 14,473.57 | 5,444.81 | 24.0% |
| Ken Lonsdale | 14,175.23 | 806.86 | 20.0% |
| Sanjit Chand | 14,142.33 | 5,757.41 | 6.4% |
| Hunter Lopez | 12,873.30 | 5,622.43 | 1.8% |
| Sanjit Engle | 12,209.44 | 2,650.68 | 11.1% |
| Christopher Conant | 12,129.07 | 2,177.05 | 28.2% |

### Key finding

> The top customer by sales, **Sean Miller**, is actually **losing the business money** (-$1,980.74 profit), driven by an average discount of 24.7% — nearly double most other top-10 customers.

## 3. Top 10 Customers by Order Frequency

| Customer | Orders | Sales | Profit |
| --- | ---: | ---: | ---: |
| Emily Phan | 17 | 5,478.06 | 144.96 |
| Zuschuss Carroll | 13 | 8,025.71 | **-1,032.15** |
| Noel Staavos | 13 | 2,964.82 | **-234.77** |
| Patrick Gardner | 13 | 3,086.91 | 137.46 |
| Joel Eaton | 13 | 6,760.82 | 221.80 |
| Erin Ashbrook | 13 | 2,846.71 | **-52.74** |
| Chloris Kastensmidt | 13 | 3,154.86 | 141.28 |
| Sally Hughsby | 13 | 3,406.84 | 558.47 |
| Suzanne McNair | 12 | 5,563.39 | 581.57 |
| Rick Bensley | 12 | 4,715.47 | 640.55 |

### Key finding

> High order frequency doesn't guarantee profitability either. Three of the top 10 most frequent customers — **Zuschuss Carroll, Noel Staavos, and Erin Ashbrook** — are net-unprofitable despite ordering regularly.

## 4. Performance by Segment

| Segment | Sales | Profit | Margin |
| --- | ---: | ---: | ---: |
| Consumer | 1,161,401 | 134,119.21 | 11.5% |
| Corporate | 706,146 | 91,979.13 | 13.0% |
| Home Office | 429,653 | 60,298.68 | 14.0% |

### Key finding

> **Consumer** drives the most sales and profit overall, but has the **lowest margin** of the three segments. **Home Office** is the smallest by volume but the most efficient per dollar sold.

## 📊 Visualizations

1. **Top 10 Customers by Sales**, colored by profitability (green = profitable, red = loss-making) — visually highlights that the #1 customer by sales is a loss-maker.
2. **Sales vs Profit by Segment** — grouped bar chart comparing all three segments.

---

# 🕵️ Challenge #03 Mystery

## Is the biggest spender the most valuable customer?

**No.** Sean Miller generates the most total sales ($25,043) but posts a **loss of -$1,980.74**, driven by a 24.7% average discount rate — nearly the highest in the top 10.

By comparison, **Tamara Chand** generates $6K less in sales but delivers **$8,981 in profit** on an 11.7% average discount — almost $11,000 more profitable than the "top" customer.

### 💡 Insight

> **Total sales is a vanity metric. Profit — not spend or order count — is what actually separates a valuable customer from a costly one.**

---

# 💼 Business Recommendations

### 1. Focus on highly profitable products

Technology was the strongest category, while products such as the Canon imageCLASS 2200 Advanced Copier generated substantial profit.

The business should maintain availability of highly profitable products and use targeted promotions to support their performance.

### 2. Review high-sales, low-profit products

Products such as the Cisco TelePresence System EX90 should be reviewed for pricing, discounting, costs, and profit margins.

High sales alone should not be treated as a measure of success.

### 3. Plan for seasonal demand

November and December have the strongest average sales, while February is consistently weaker.

The business should prepare inventory, staffing, and marketing resources before the **September–December peak**, while using targeted campaigns to stimulate demand during weaker periods.

### 4. Cap or tier discounts for high-volume customers

Introduce a discount ceiling (e.g., no discretionary discount above 15%) for customers who order frequently, especially in the Consumer segment. Sean Miller-type accounts should trigger a review before another deep discount is approved.

### 5. Re-rank "top customers" by profit and margin, not sales

Replace or supplement the sales leaderboard with a profit-based one for account management, loyalty rewards, and VIP treatment. This prevents rewarding customers who look valuable on the surface but cost the business money.

### 6. Protect and invest in Corporate and Home Office relationships

These segments have the best margins per dollar sold. Rather than pouring more discount incentives into Consumer to chase volume, shift retention effort and account management resources toward Corporate/Home Office, where profitability is structurally healthier.

---

# 🏁 Overall Conclusion

These three challenges show that **sales, timing, and customer behavior each tell a different part of the business story**.

Challenge #01 showed that:

> **High sales do not necessarily mean high profit.**

Challenge #02 showed that:

> **Low sales do not necessarily mean something is wrong. They may reflect predictable seasonality.**

Challenge #03 showed that:

> **The biggest spender or the most frequent buyer is not always the most valuable customer — profit is the real measure of value.**

Together, the analyses provide a broader view of business performance by examining **what is profitable**, **when sales occur**, and **who actually drives sustainable value**.

---

# 🛠️ Tools Used

* Python
* Pandas
* Matplotlib
* Jupyter Notebook
* Google Colab

## 🚀 Learning Progress

| Challenge | Focus                                 | Status      |
| --------- | -------------------------------------- | ----------- |
| #01       | Profitability & business performance   | ✅ Completed |
| #02       | Sales trends, seasonality & growth     | ✅ Completed |
| #03       | Customer value & segment performance   | ✅ Completed |

**This was the final challenge with the Superstore dataset — next week, a brand-new dataset begins!** 🎉
