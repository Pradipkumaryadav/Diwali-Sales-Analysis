# 🪔 Diwali Sales Analysis – Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.14-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange)
![NumPy](https://img.shields.io/badge/NumPy-Data%20Processing-blue)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-green)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-purple)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)

## 📌 Project Overview

This project performs Exploratory Data Analysis (EDA) on a Diwali sales dataset to understand customer purchasing behavior and identify patterns across customer demographics, locations, occupations, and product categories.

The analysis was performed using Python and its major data analysis and visualization libraries: **Pandas, NumPy, Matplotlib, and Seaborn**.

The objective is to transform raw sales data into meaningful insights that can help businesses understand their customers and make better decisions related to marketing, product targeting, and sales strategy.


## 🎯 Project Objectives

The main objectives of this project are:

* Analyze customer purchasing behavior during the Diwali sales period.
* Understand purchasing patterns across different genders and age groups.
* Identify the states generating the highest number of orders and sales.
* Analyze purchasing behavior based on marital status.
* Identify occupations associated with higher purchasing activity.
* Determine the most popular product categories.
* Identify the most frequently ordered products.
* Generate actionable business insights from the data.



## 📊 Dataset Overview

The dataset contains customer-level Diwali sales information.

### Original Dataset

* **Rows:** 11,251
* **Columns:** 15

The dataset contains information about:

| Column             | Description                                    |
| ------------------ | ---------------------------------------------- |
| `User_ID`          | Unique customer identifier                     |
| `Cust_name`        | Customer name                                  |
| `Product_ID`       | Product identifier                             |
| `Gender`           | Customer gender                                |
| `Age Group`        | Customer age group                             |
| `Age`              | Customer age                                   |
| `Marital_Status`   | Customer marital status                        |
| `State`            | Customer state                                 |
| `Zone`             | Geographical zone                              |
| `Occupation`       | Customer occupation                            |
| `Product_Category` | Product category                               |
| `Orders`           | Number of orders                               |
| `Amount`           | Purchase amount                                |
| `Status`           | Blank/unrelated column removed during cleaning |
| `unnamed1`         | Blank/unrelated column removed during cleaning |



## 🧹 Data Cleaning

The following data-cleaning operations were performed:

### 1. Removed unnecessary columns

The `Status` and `unnamed1` columns were removed because they did not contain useful information for the analysis.

```python
df.drop(['Status', 'unnamed1'], axis=1, inplace=True)
```

### 2. Checked missing values

Missing values were identified using:

```python
pd.isnull(df).sum()
```

The `Amount` column contained 12 missing values.

### 3. Removed missing records

Rows containing missing values were removed:

```python
df.dropna(inplace=True)
```

After cleaning, the dataset contained **11,239 records and 13 columns**.

### 4. Converted Amount to integer

The `Amount` column was converted from floating-point format to integer:

```python
df['Amount'] = df['Amount'].astype(int)
```



# 🔎 Exploratory Data Analysis

## 1. Gender Analysis

The analysis compares the number of buyers and total purchasing amount between male and female customers.

   <img width="750" height="323" alt="Screenshot 2026-09-25 111136" src="https://github.com/user-attachments/assets/dac0f8ce-4d7a-493a-8d94-04caf8dacf24" />

### Finding

Female customers represent the larger share of buyers and also contribute substantially more to total sales than male customers.

In the cleaned dataset:

* Female customers: **7,832**
* Male customers: **3,407**
* Female sales: approximately **₹74.34 million**
* Male sales: approximately **₹31.91 million**


   <img width="1090" height="427" alt="image" src="https://github.com/user-attachments/assets/a92e08c0-7efd-4c42-99c0-52945059d47f" />


This indicates that female customers were the dominant purchasing group in the dataset.



## 2. Age Group Analysis

Customer purchasing behavior was analyzed across different age groups.

### Finding

The **26–35 age group** is the strongest customer segment.

The 26–35 age group generated approximately **₹42.61 million** in sales, making it the highest-sales age group in the dataset.

   <img width="712" height="323" alt="Screenshot 2026-09-25 111416" src="https://github.com/user-attachments/assets/b21c18e5-86ca-4920-91b2-7ca630ed2629" />


This segment should therefore receive particular attention when developing customer-targeted marketing campaigns.



## 3. State Analysis

The analysis examined both the number of orders and total sales across states.

### Top states by orders

The leading states include:

1. Uttar Pradesh
2. Maharashtra
3. Karnataka
4. Delhi
5. Madhya Pradesh

   <img width="777" height="394" alt="Screenshot 2026-09-25 111717" src="https://github.com/user-attachments/assets/a706fb09-fb2a-4422-8344-02ea3ac3eb82" />
   

### Finding

**Uttar Pradesh, Maharashtra, and Karnataka** are among the strongest-performing states in terms of both orders and sales.

   <img width="759" height="300" alt="Screenshot 2026-09-25 112003" src="https://github.com/user-attachments/assets/91539bbc-1d9a-4298-b4ee-b39e3982d805" />


Uttar Pradesh generated approximately **₹19.37 million** in sales in the cleaned dataset.



## 4. Marital Status Analysis

The project analyzes purchasing behavior based on customer marital status and gender.

### Finding

The analysis indicates that married customers, particularly women, form an important customer segment and demonstrate strong purchasing activity.


   <img width="791" height="332" alt="Screenshot 2026-09-25 112305" src="https://github.com/user-attachments/assets/eac56590-30f4-4f58-bb14-9eb2d4bdd7df" />


This suggests that family-oriented promotions and targeted offers could be useful during major festive shopping periods.



## 5. Occupation Analysis

Customer occupations were analyzed to understand which professional groups contribute most to sales.

### Top occupations by sales

1. IT Sector
2. Healthcare
3. Aviation
4. Banking
5. Government

   <img width="755" height="352" alt="image" src="https://github.com/user-attachments/assets/ef515bf4-5494-4129-a79a-1c63349e7d75" />


### Finding

Customers working in the **IT, Healthcare, and Aviation sectors** represent some of the strongest purchasing groups in the dataset.

   <img width="758" height="355" alt="Screenshot 2026-09-25 112501" src="https://github.com/user-attachments/assets/a539006c-4eb2-4242-98e9-360191ed4406" />

The IT sector generated approximately **₹14.76 million** in sales.



## 6. Product Category Analysis

Product categories were analyzed based on sales and order volume.

### Top categories by sales

1. Food
2. Clothing & Apparel
3. Electronics & Gadgets
4. Footwear & Shoes
5. Furniture
   
   <img width="759" height="351" alt="Screenshot 2026-09-25 112647" src="https://github.com/user-attachments/assets/e0d0683d-97c3-4f04-9d4a-5b9f45849f92" />

### Finding

**Food, Clothing & Apparel, and Electronics & Gadgets** are among the strongest product categories in terms of sales.

   <img width="752" height="361" alt="image" src="https://github.com/user-attachments/assets/502ffef8-37b0-410c-9e43-122288d22781" />

Food generated approximately **₹33.93 million** in sales, making it the highest-sales product category in the cleaned dataset.



## 7. Product-Level Analysis

The project also identifies the top products based on the number of orders.

   <img width="754" height="349" alt="image" src="https://github.com/user-attachments/assets/e9259182-6baa-4e21-901d-49b28070d60d" />


The analysis uses product-level aggregation to identify frequently ordered products and understand customer product preferences.



# 📈 Key Business Insights

The EDA generated the following major insights:

### 👩 Gender

Female customers are the dominant purchasing group and contribute significantly more to total sales than male customers.

### 👥 Age

Customers aged **26–35** represent the strongest age segment.

### 📍 Geography

**Uttar Pradesh, Maharashtra, and Karnataka** are among the highest-performing states.

### 💼 Occupation

Customers working in the **IT, Healthcare, and Aviation sectors** show strong purchasing activity.

### 🛍️ Product Categories

**Food, Clothing & Apparel, and Electronics & Gadgets** are the leading product categories by sales.

### 💍 Marital Status

Married customers, particularly women, represent an important purchasing segment.



# 💡 Business Recommendations

Based on the analysis, the following strategies could be considered:

### 1. Target the 26–35 Age Group

Marketing campaigns and festive offers can be specifically designed for customers aged 26–35 because this group demonstrates the strongest purchasing activity.

### 2. Focus on Female Customers

Since female customers represent the larger customer and sales segment, businesses can develop targeted promotions and product recommendations for this audience.

### 3. Strengthen Regional Marketing

Uttar Pradesh, Maharashtra, and Karnataka should receive strong marketing and inventory attention because they are among the highest-performing states.

### 4. Target High-Value Occupations

Promotional campaigns can be targeted toward customers working in IT, Healthcare, Aviation, and Banking sectors.

### 5. Prioritize High-Performing Categories

Inventory and promotional strategies can focus on Food, Clothing & Apparel, and Electronics & Gadgets because these categories generate strong sales.

### 6. Use Customer Segmentation

Combining gender, age, marital status, occupation, and location can help create more personalized marketing campaigns.



# 🛠️ Technologies Used

| Technology       | Purpose                        |
| ---------------- | ------------------------------ |
| Python           | Data analysis                  |
| Pandas           | Data cleaning and manipulation |
| NumPy            | Numerical operations           |
| Matplotlib       | Data visualization             |
| Seaborn          | Statistical visualization      |
| Jupyter Notebook | Analysis environment           |



# 📷 Visualizations

The notebook contains visualizations covering:

* Gender distribution
* Gender vs total sales
* Age group distribution
* Age group vs sales
* Top states by orders
* Top states by sales
* Marital status distribution
* Marital status and gender vs sales
* Occupation distribution
* Occupation vs sales
* Product category distribution
* Product category vs sales
* Top products by orders

# 📌 Project Takeaways

This project demonstrates practical experience in:

* Data cleaning
* Missing-value handling
* Data type conversion
* Exploratory Data Analysis
* GroupBy operations
* Aggregation
* Customer segmentation
* Sales analysis
* Data visualization
* Business insight generation
* Business recommendations



# 👨‍💻 Author

## Pradip Kumar Yadav

**B.Tech – Computer Science & Technology**

Aspiring Data Analyst / Data Scientist

### Skills

Python | SQL | Pandas | NumPy | Matplotlib | Seaborn | Power BI | Excel



⭐ If you found this project useful, feel free to star the repository.

