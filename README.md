#  Bike Sales Data Automation & Power BI Dashboard

##  Project Overview
This project demonstrates a complete **data automation workflow** using **MySQL, Python, and Power BI**.  
It connects to a MySQL database, cleans and merges sales data automatically, and exports a ready-to-use dataset for interactive visualization.

The goal was to automate the reporting process and provide management with real-time insights into sales performance, customer segments, and revenue trends.

---

##  Tech Stack
- **MySQL** – Data storage and querying  
- **Python** – Data cleaning, merging, and automation  
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, MySQL Connector  
- **Power BI** – Interactive dashboard visualization  
- **Excel/CSV** – Clean data export  

---

##  Workflow

### 1. Data Extraction
Connected Python to MySQL and retrieved data from multiple tables:
```python
import mysql.connector
import pandas as pd

conn = mysql.connector.connect(
    host='localhost',
    user='root',
    password='your_password',
    database='bike_sales_db'
)

customers = pd.read_sql('SELECT * FROM customers;', conn)
products = pd.read_sql('SELECT * FROM products;', conn)
sales = pd.read_sql('SELECT * FROM sales;', conn)
conn.close()
