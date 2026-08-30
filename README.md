# 📊 Superstore Data Analysis — Weekend Data Challenges

This repository contains my analysis of the **Superstore dataset** through a series of Weekend Data Challenges.

The first challenge focused on **profitability and business performance**, while the second explored **sales trends, seasonality, and year-over-year growth**.

---

## 📂 Dataset

The **Superstore Dataset Final** was used for both challenges.

**Source:** Kaggle — Superstore Dataset Final

The dataset contains **9,994 retail order records** with information about:

* Order dates
* Products
* Categories
* Regions
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

---

# 🏁 Overall Conclusion

These two challenges show that **sales and profitability tell different parts of the business story**.

Challenge #01 showed that:

> **High sales do not necessarily mean high profit.**

Challenge #02 showed that:

> **Low sales do not necessarily mean something is wrong. They may reflect predictable seasonality.**

Together, the analyses provide a broader view of business performance by examining both **what is profitable** and **when sales occur**.

---

# 🛠️ Tools Used

* Python
* Pandas
* Matplotlib
* Jupyter Notebook
* Google Colab

## 🚀 Learning Progress

| Challenge | Focus                                | Status      |
| --------- | ------------------------------------ | ----------- |
| #01       | Profitability & business performance | ✅ Completed |
| #02       | Sales trends, seasonality & growth   | ✅ Completed |

**More challenges coming soon.**
