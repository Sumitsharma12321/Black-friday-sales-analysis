# 🛍️ Black Friday Sales — Exploratory Data Analysis

A complete Exploratory Data Analysis (EDA) of Black Friday retail transaction data. This project digs into customer purchasing behavior by examining demographics, product categories, city types, occupations, and more — using Python, Pandas, Matplotlib, and Seaborn.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset Description](#-dataset-description)
- [Project Structure](#-project-structure)
- [Key Questions Explored](#-key-questions-explored)
- [Notebooks Breakdown](#-notebooks-breakdown)
- [Technologies Used](#-technologies-used)
- [How to Run](#-how-to-run)
- [Key Findings](#-key-findings)

---

## 📖 Project Overview

Black Friday is one of the biggest retail sales events of the year. This project analyzes a large dataset of Black Friday transactions to uncover patterns in **who buys what, how much they spend, and why**.

The analysis is structured across multiple focused notebooks, each tackling a specific dimension of the data — from gender and age to occupation and product category performance.

---

## 📊 Dataset Description

**File:** `BlackFriday.csv`

| Stat | Value |
|---|---|
| Total Transactions | 537,577 |
| Unique Users | 5,891 |
| Unique Products | 3,623 |
| Total Revenue | $5,017,668,378 |

### Columns

| Column | Description |
|---|---|
| `User_ID` | Unique identifier for each customer |
| `Product_ID` | Unique identifier for each product |
| `Gender` | Customer gender — `M` (Male) or `F` (Female) |
| `Age` | Age group — `0-17`, `18-25`, `26-35`, `36-45`, `46-50`, `51-55`, `55+` |
| `Occupation` | Occupation code (0–20, anonymized) |
| `City_Category` | City tier — `A`, `B`, or `C` |
| `Stay_In_Current_City_Years` | Years lived in current city — `0`, `1`, `2`, `3`, `4+` |
| `Marital_Status` | `0` = Unmarried, `1` = Married |
| `Product_Category_1` | Primary product category (18 categories) |
| `Product_Category_2` | Secondary product category *(166,986 nulls — dropped)* |
| `Product_Category_3` | Tertiary product category *(373,299 nulls — dropped)* |
| `Purchase` | Purchase amount in dollars |

> **Note:** `Product_Category_2` and `Product_Category_3` were dropped in all analyses due to a high proportion of missing values.

---

## 📁 Project Structure

```
BlackFriday-EDA/
│
├── BlackFriday.csv                        # Raw dataset
│
├── Walkthrough.ipynb                      # Initial data loading, inspection & cleaning
├── Analyse_columns.ipynb                  # Column-by-column exploration & unique value counts
├── Analysing_gender.ipynb                 # Gender-based purchase analysis
├── Analysing_Age___Marital_status.ipynb   # Age and marital status analysis
├── Combining_Age___Marital_Status.ipynb   # Combined gender + marital status feature analysis
├── Multicolumn_analysis.ipynb             # City category, age-gender cross-analysis
├── Occupation___Products_Analysis.ipynb   # Occupation, stay-in-city, and product deep dive
│
└── README.md
```

---

## ❓ Key Questions Explored

- Do male or female customers spend more on Black Friday?
- Which age group makes the most purchases and spends the most?
- How does marital status influence spending patterns?
- Which city tier (A, B, C) generates the highest revenue?
- Which occupations are the biggest spenders?
- How long a customer has lived in their city — does it affect their purchases?
- Which product categories are most popular and most profitable?
- What are the top 10 best-selling and highest-revenue products?

---

## 📓 Notebooks Breakdown

### 1. `Walkthrough.ipynb` — Data Loading & Cleaning
The entry point for the project.
- Loads the raw CSV with Pandas
- Inspects data shape, types, and null values using `df.info()` and `df.isnull().sum()`
- Drops `Product_Category_2` and `Product_Category_3` due to excessive missing data
- Previews the cleaned dataset

---

### 2. `Analyse_columns.ipynb` — Column Exploration
A systematic scan of every column in the dataset.
- Counts unique values per column
- Lists all categories for Gender, Age, Occupation, City, Marital Status, and Product Category
- Computes total purchase revenue (`$5.01 Billion`)
- Gives a complete picture of the dataset's cardinality before deep-diving

---

### 3. `Analysing_gender.ipynb` — Gender Analysis
- Pie and bar charts showing male vs. female transaction count ratio
- Comparison of **total purchase amount** by gender
- Comparison of **average purchase amount** per transaction by gender
- Reveals whether one gender spends more per transaction or simply transacts more

---

### 4. `Analysing_Age___Marital_status.ipynb` — Age & Marital Status Analysis
- Bar charts of purchase volume and total spend by age group
- Number of **unique products purchased** per age group
- Average spend per transaction across age brackets
- Pie chart of marital status distribution
- Identifies which demographic is the most commercially active

---

### 5. `Combining_Age___Marital_Status.ipynb` — Combined Feature Analysis
- Engineers a new feature: `MaritalGender` — combines Gender + Marital_Status (e.g., `M_0`, `F_1`)
- Count plots for the new feature across:
  - Age groups
  - Product categories
  - Years in current city
  - City category
- Enables a richer, intersectional view of customer demographics

---

### 6. `Multicolumn_analysis.ipynb` — City Category & Cross-Variable Analysis
- Count plots for City Category distribution
- Cross-analysis of City Category with Age, Gender, and Marital Status
- Pie charts for city-wise total and average purchase value
- Age vs. Gender interaction plots
- Examines which city types drive the most revenue

---

### 7. `Occupation___Products_Analysis.ipynb` — Occupation, City Stay & Products
The most comprehensive notebook in the project.

**Stay in Current City:**
- Distribution of customers by years lived in city
- Cross-plots with Gender, Marital Status, City Category, and Age
- Total and average purchase by years stayed

**Occupation:**
- Customer count, total spend, and average spend per occupation
- Occupation breakdown by Gender and Marital Status
- Number of unique products purchased per occupation

**Product Analysis:**
- Purchase volume and revenue by `Product_Category_1`
- **Top 10 products** by total revenue, sales volume, and average price
- Gender and marital status split across product categories

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| Python 3 | Core programming language |
| Pandas | Data loading, cleaning, and groupby analysis |
| Matplotlib | Bar charts and pie charts |
| Seaborn | Count plots and hue-based cross-variable visualizations |
| Jupyter Notebook | Interactive development environment |

---

## ▶️ How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/blackfriday-eda.git
   cd blackfriday-eda
   ```

2. **Install dependencies**
   ```bash
   pip install pandas matplotlib seaborn jupyter
   ```

3. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

4. **Run notebooks in this recommended order:**
   ```
   Walkthrough.ipynb
   Analyse_columns.ipynb
   Analysing_gender.ipynb
   Analysing_Age___Marital_status.ipynb
   Combining_Age___Marital_Status.ipynb
   Multicolumn_analysis.ipynb
   Occupation___Products_Analysis.ipynb
   ```

> Make sure `BlackFriday.csv` is in the same directory as all notebooks before running.

---

## 💡 Key Findings

- **Male customers dominate** in both transaction count and total spend, but the average spend per transaction difference with female customers is narrower than expected.
- **Age group 26–35** is the largest buyer segment — both in number of transactions and total money spent.
- **City B** has the highest number of customers, but per-transaction spend varies by city tier.
- **Product Category 1 and 5** are among the most purchased categories.
- Customers who have **stayed 1 year in their city** show the highest purchase activity.
- **Occupation codes 4 and 0** consistently show up among the highest spenders.
- The engineered `MaritalGender` feature reveals that **unmarried males (M_0)** make up the largest and highest-spending customer segment.

---

## 📬 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
