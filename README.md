# 🛒 E-Commerce Customer Churn Analysis

**Python data cleaning and exploration + Power BI dashboard to find out which customers leave an e-commerce platform, and why.**

![Dashboard](images/dashboard.png)

---

## 🎯 Business Problem
An e-commerce company is losing customers and wants to know:
1. How many customers churn, and what is the overall churn rate?
2. Which customer groups (order category, marital status, tenure) churn the most?
3. Do complaints, satisfaction scores and cashback relate to churn?
4. Where should the retention team focus first?

## 🛠️ Tools & Skills
| Area | Details |
|---|---|
| Python (pandas, seaborn, scikit-learn) | Missing-value handling, duplicate removal, one-hot encoding, correlation analysis, IQR outlier detection, EDA |
| Excel | Cleaned dataset exported as `customer_churn_cleaned.xlsx` |
| Power BI | Interactive dashboard: 6 KPI cards, 6 charts, 5 slicers, Key Insights panel |

## 🗂️ Project Structure
```
E-Commerce-Customer-Churn-Analysis/
├── data/
│   ├── customer_churn.csv             # raw data (3,941 rows, 11 columns)
│   ├── customer_churn_cleaned.xlsx    # cleaned data (3,269 rows)
│   └── churn_analysis.ipynb           # cleaning + EDA notebook
├── images/
│   └── dashboard.png
├── .gitignore
└── README.md
```

## 🧹 Data Cleaning (`churn_analysis.ipynb`)
| Step | What was done |
|---|---|
| Missing values | `Tenure`, `WarehouseToHome` and `DaySinceLastOrder` had gaps. They were filled with the **median** of each column |
| Duplicates | **672 duplicate rows removed**, taking the dataset from **3,941 to 3,269** rows |
| Encoding | `MaritalStatus` and `PreferedOrderCat` were one-hot encoded (first category dropped) for the cleaned file |
| Checks | Box plots and **IQR outlier detection** on `Tenure`, `WarehouseToHome`, `DaySinceLastOrder` and `CashbackAmount`; value checks on satisfaction score, complaint flag and minimums |
| EDA | Churn rate by complaint, satisfaction, marital status and order category; correlation heatmap; average of every feature for churned vs retained customers |
| Export | Cleaned data saved to `customer_churn_cleaned.xlsx` |

## 📊 Headline KPIs
| KPI | Value |
|---|---|
| Total Customers | **3,269** |
| Retained Customers | **2,735** |
| Churned Customers | **534** |
| Churn Rate | **16.34%** |
| Avg Tenure | **10.13 months** |
| Avg Satisfaction Score | **3.02** |

## 🔍 Key Insights
1. **About 1 in 6 customers churns.** The churn rate is **16.34%** (534 of 3,269 customers).
2. **The first two months are the danger zone.** About **54%** of customers with 0 months of tenure and **49%** with 1 month churn, against **9%** at 2 months. Among customers beyond 20 months, churn is only about **1%**.
3. **Complaints are the strongest warning sign.** **31.8%** of customers who complained churned, against **10.3%** of those who did not. Complainers are 28% of customers but **55% of all churners** (293 of 534).
4. **Mobile categories have the highest churn.** "Mobile" (**27.1%**) and "Mobile Phone" (**26.9%**) churn far above Fashion (15.5%), Laptop & Accessory (9.8%), Others (7.4%) and Grocery (**4.2%**).
5. **Satisfaction behaves unexpectedly.** Churn rises from **11.2%** at score 1 to **22.8%** at score 5. This is the opposite of what you would expect, so the score may not be a reliable early-warning signal and deserves a closer look (for example, when the survey is collected).
6. **Single customers churn the most.** **25.9%** of single customers churn, against **15.5%** for divorced and **10.9%** for married customers.
7. **Cashback alone is not keeping people.** Churned customers received a lower average cashback (**160.5**) than retained customers (**180.7**), so cashback may help but is not the main driver.

> These are patterns in the data, not proof of cause.

## 💡 Recommendations
- **Build an onboarding programme** for the first 2 to 3 months (welcome offers, check-ins), since about half of the newest customers leave.
- **Treat every complaint as a churn-risk flag** and fast-track resolution.
- **Investigate the Mobile categories** to find out whether delivery, quality or pricing issues drive their ~27% churn.
- **Review the satisfaction survey:** check when it is collected and why high scores still churn.
- **Target single customers** with loyalty offers, as they are the highest-risk segment.

## 📐 Dashboard Features
- 6 KPI cards, 6 charts (churn by satisfaction, order category, complaint, tenure, marital status, and average cashback) and a Key Insights panel
- Slicers for Satisfaction Score, Complain, Order Category, Marital Status and Tenure, so every chart can be filtered interactively

## ▶️ How to Reproduce
1. Clone the repo and open `data/churn_analysis.ipynb` in Jupyter. It reads `customer_churn.csv` from the same folder.
2. Run all cells to clean the data and export `customer_churn_cleaned.xlsx`.
3. Load the cleaned data into Power BI Desktop and rebuild the visuals, or open your own copy of the dashboard.

## 👤 Author
**Irfan** - Aspiring Data Analyst
[LinkedIn](https://www.linkedin.com/) · [GitHub](https://github.com/iirfanshk)
