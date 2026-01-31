#  Food Delivery Data Integration & Analysis

##  Project Overview
This project focuses on integrating data from multiple real-world sources (CSV, JSON, and SQL) to build a unified dataset for analysis. The final dataset is used to analyze user behavior, restaurant performance, and revenue trends in a food delivery .

---

##  Dataset Overview

The project uses three different datasets, each stored in a different format:

### 1️) orders.csv (Transactional Data)
Contains order-level information:
- order_id  
- user_id  
- restaurant_id  
- order_date  
- total_amount  

### 2️) users.json (User Master Data)
Contains user details:
- user_id  
- city  
- membership (Gold / Regular)  

### 3️) restaurants.sql (Restaurant Master Data)
Stored in SQL format and includes:
- restaurant_id  
- restaurant_name  
- cuisine  
- restaurant_rating  

---

## Data Integration Workflow

### Step 1: Load CSV Data
Orders data is loaded using Pandas.

### Step 2: Load JSON Data
User data is read from a JSON file.

### Step 3: Load SQL Data
Restaurant data is extracted from a SQLite database using SQL scripts.

### Step 4: Merge the Data
The datasets are combined using **left joins**:
- orders.user_id → users.user_id  
- orders.restaurant_id → restaurants.restaurant_id  

Left join ensures all orders are retained even if user or restaurant data is missing.

### Step 5: Create Final Dataset
A consolidated dataset containing:
- Order details  
- User information  
- Restaurant information  

 **Output File:**   final_food_delivery_dataset.csv
