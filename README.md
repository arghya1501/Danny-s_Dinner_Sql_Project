# Danny's Diner SQL Project

## 📌 Project Overview
Danny's Diner is a fictional restaurant where Danny wants to use his customer data to better understand the business. The goal of this project is to analyze customer behaviors and provide insights using SQL.

## 📊 Key Insights
This project focuses on answering critical business questions such as:
- Who are the most loyal customers?
- What menu items are the most popular?
- What is the total revenue generated by each customer?
- How does customer spending behavior change over time?

## 🛠️ Technologies Used
- **SQL (MySQL / PostgreSQL)** for querying data
- **Jupyter Notebook** for interactive analysis
- **Power BI / Tableau** (Optional) for data visualization

## 🗄️ Dataset Description
The dataset consists of three main tables:

### 1️⃣ `sales` Table
This table records each transaction made by customers.

```sql
SELECT * FROM sales LIMIT 5;
```

| customer_id | order_date | product_id |
|------------|------------|------------|
| A          | 2021-01-01 | 1          |
| A          | 2021-01-01 | 2          |
| A          | 2021-01-07 | 2          |
| B          | 2021-01-02 | 2          |
| C          | 2021-01-09 | 3          |

### 2️⃣ `menu` Table
This table provides details about the menu items including price.

```sql
SELECT * FROM menu LIMIT 5;
```

| product_id | product_name | price |
|------------|--------------|--------|
| 1          | sushi        | 10     |
| 2          | curry        | 15     |
| 3          | ramen        | 12     |

### 3️⃣ `members` Table
This table keeps track of the loyalty membership program.

```sql
SELECT * FROM members LIMIT 5;
```

| customer_id | join_date  |
|------------|------------|
| A          | 2021-01-07 |
| B          | 2021-01-09 |

## 🔍 Analysis Queries
### 1️⃣ Total Revenue per Customer
```sql
SELECT s.customer_id, SUM(m.price) AS total_revenue
FROM sales s
JOIN menu m ON s.product_id = m.product_id
GROUP BY s.customer_id
ORDER BY total_revenue DESC;
```

### 2️⃣ Most Popular Items
```sql
SELECT m.product_name, COUNT(s.product_id) AS order_count
FROM sales s
JOIN menu m ON s.product_id = m.product_id
GROUP BY m.product_name
ORDER BY order_count DESC;
```

### 3️⃣ Customer Purchase Frequency
```sql
SELECT customer_id, COUNT(*) AS total_orders
FROM sales
GROUP BY customer_id
ORDER BY total_orders DESC;
```

## 📈 Results & Findings
- The most loyal customer is **Customer A**, who has the highest total spending.
- **Curry** is the most popular dish.
- Customers tend to order more frequently after joining the loyalty program.

## 🚀 How to Run the Queries
1. Clone this repository:
   ```sh
   git clone https://github.com/arghya1501/Danny-s_Dinner_Sql_Project.git
   ```
2. Import the dataset into your SQL environment.
3. Run the provided SQL queries to analyze the data.

## 📝 Conclusion
This project demonstrates how SQL can be used to extract valuable insights from raw business data. The findings help Danny optimize menu pricing, understand customer preferences, and improve customer retention strategies.

---

🔗 **GitHub Repository**: [Danny's Dinner SQL Project](https://github.com/arghya1501/Danny-s_Dinner_Sql_Project)
