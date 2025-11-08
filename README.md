# 🛍 customer_behavior_analysis-SQL_Python_PowerBI

## 📝 Overview
This project explores customer purchasing behavior through end-to-end data analysis.  
The goal is to understand revenue patterns, customer segments, discount impacts, and subscription trends by combining **Python (EDA)**, **MySQL (SQL analysis)**, **Power BI (dashboard visualization)**, and **Gamma (presentation)**.

It showcases real-world data handling — from loading and cleaning datasets to building dashboards and presenting insights professionally.

---

## 📂 Data & Dataset
- **Name:** Customer Purchase Behavior Dataset  
- **Format:** CSV / Excel  
- **Size:** ~10,000+ transactions  
- **Source:** Synthetic retail data (for learning & analytics demonstration)  
- **Description:**  
  Each record represents a customer's purchase, including attributes such as gender, age group, category, shipping type, purchase amount, discounts, reviews, and subscription status.

| Column               | Description                          |
|----------------------|--------------------------------------|
| `customer_id`        | Unique ID for each customer          |
| `gender`             | Gender of the customer               |
| `age_group`          | Age bracket                          |
| `item_purchased`     | Product name                         |
| `category`           | Product category                     |
| `purchase_amount`    | Purchase amount in dollars           |
| `discount_applied`   | Whether a discount was used          |
| `review_rating`      | Rating given by the customer         |
| `shipping_type`      | Standard or Express                  |
| `previous_purchases` | Total past purchases                 |
| `subscription_status`| Subscriber or Non-subscriber         |

---

## 🧰 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python (Pandas, NumPy, Matplotlib, Seaborn)** | Data loading, cleaning, and exploratory data analysis (EDA) |
| **MySQL** | Advanced queries and business insights extraction |
| **Power BI** | Interactive dashboard creation |
| **Gamma** | Professional presentation for reporting insights |
| **Excel / CSV** | Data input format |

---

## 🧼 Data Cleaning
Performed using Python and Pandas to ensure data quality:
- Removed duplicates and null values  
- Standardized column names  
- Checked data types  
- Detected and handled outliers  
- Converted categorical fields into consistent formats  

```python
# Example: Data cleaning
import pandas as pd

df = pd.read_csv('customer_data.csv')
df.drop_duplicates(inplace=True)
df.dropna(inplace=True)
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')
```

---

## 🔍 Exploratory Data Analysis (EDA)
EDA was performed to uncover patterns and trends:
- Gender-based revenue comparison  
- Category-wise product performance  
- Age group spending patterns  
- Impact of discounts on total sales  
- Subscription behavior insights  

```python
# Example visualization
import seaborn as sns
import matplotlib.pyplot as plt

sns.barplot(x='gender', y='purchase_amount', data=df, estimator='sum')
plt.title('Total Revenue by Gender')
plt.show()
```

---

## 🧮 SQL Analysis
MySQL was used to query and validate insights directly from the database.  
Each question represents a business problem answered through SQL logic.

```sql
-- Q1: Total revenue by gender
SELECT gender, SUM(purchase_amount) AS revenue
FROM customer
GROUP BY gender;

-- Q5: Do subscribers spend more?
SELECT 
    subscription_status,
    COUNT(customer_id) AS total_customers,
    ROUND(AVG(purchase_amount), 2) AS avg_spend,
    ROUND(SUM(purchase_amount), 2) AS total_revenue
FROM customer
GROUP BY subscription_status;
```

📄 **File:** `customer_project.sql`  
Contains 10 SQL queries, including:
- Top products by ratings  
- Discount impact analysis  
- Customer segmentation (New / Returning / Loyal)  
- Age group revenue contribution  
- Category-wise top purchased items  

---

## 📈 Power BI Dashboard
A Power BI dashboard was designed to visualize the key findings interactively.

**Dashboard Highlights:**
- Total revenue overview  
- Gender-based revenue comparison  
- Category and product performance  
- Subscriber vs non-subscriber behavior  
- Discount impact visualization  
- Age group contribution  

---

## 📘 Statistical Insights
Statistical analysis was done using Python:
- Descriptive statistics (mean, median, mode)  
- Correlation between discount and purchase amount  
- Comparative analysis using grouped metrics  

```python
df.groupby('subscription_status')['purchase_amount'].describe()
```

---

## 📊 Results & Key Insights
- Subscribers spend significantly more than non-subscribers  
- Discounts attract customers but don’t always lead to higher revenue  
- Top 5 products hold majority of total sales volume  
- Age group 25–34 contributes the highest revenue  
- Loyal customers are the smallest group but spend the most  

---

## 🧾 Report & Presentation
- A structured report summarizing methodology, findings, and visuals  
- Gamma presentation created for professional storytelling of insights  

---

## 🚀 How to Run This Project

### 🐍 Python
1. Clone this repository  
   ```bash
   git clone https://github.com/yourusername/customer-behavior-analysis.git
   ```
2. Navigate into the folder  
   ```bash
   cd customer-behavior-analysis
   ```
3. Install dependencies  
   ```bash
   pip install -r requirements.txt
   ```
4. Open and run the Jupyter notebook  
   ```bash
   jupyter notebook customer_behavior_analysis.ipynb
   ```

### 💾 MySQL
1. Import `customer_project.sql` into your MySQL database  
2. Run queries in sequence to explore customer insights  

### 📊 Power BI
1. Open `customer_dashboard.pbix`  
2. Refresh the data connection to your dataset  

---

## 💡 Project Takeaways
This project demonstrates:
- Practical data cleaning and EDA skills  
- SQL-based analytical problem solving  
- Dashboard storytelling through Power BI  
- Business insight presentation with Gamma  

---

## 📧 Contact

👤 Your Name  
📩 Email: nishantkarakoti922@gmail.com  
🔗 [LinkedIn]:[https://www.linkedin.com/in/nishant-karakoti-890880241/]  
💻 [GitHub]:[https://github.com/Nishant9372]
