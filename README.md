# 📊 Data Analytics Mastery — Classroom & Project Resource Hub

Welcome to the **Data Analytics Notebook & Bootcamp Repository**! This repository houses a comprehensive, hands-on data analytics curriculum designed to take students and self-learners from absolute beginners to project-ready data analysts capable of driving real-world business decisions.

---

## 🗂️ Repository Structure

```text
data_analytics_notebook/
├── README.md                      # Primary resource & access guide (You are here)
├── .gitignore                     # Git configuration (ignores OS metadata)
├── day1/                          # Module 1: Foundations & Analytical Roadmap
│   ├── README.md                  # Comprehensive Day 1 lesson guide & roadmap
│   ├── ecommerce.csv              # Unified 100-row e-commerce transaction dataset
│   ├── customers.csv              # Relational table: Customer demographic master
│   ├── orders.csv                 # Relational table: Order details & transactions
│   └── quiz/                      # Assessment pack (25 questions)
│       ├── quiz.csv               # CSV format for LMS / Quizizz / Canvas import
│       └── quiz.xlsx              # Excel spreadsheet format with full quiz keys
└── day2/                          # Module 2: The Data Detective Challenge
    ├── README.md                  # Gamified forensic case study & mission guide
    └── mystery_ecommerce.csv      # Forensic raw dataset with glitches & anomalies
```

---

## 🚀 How to Access & Use the Resources

### Option 1: Zero Setup — Run in Google Colab (Recommended for Students)

You can launch a notebook directly in your browser without installing anything locally:

1. Open [Google Colab](https://colab.research.google.com/).
2. Create a **New Notebook**.
3. Clone this repository inside Colab by running this in the first cell:
   ```python
   !git clone https://github.com/Hari-Nikesh-R/data_analytics_notebook.git
   %cd data_analytics_notebook
   ```
4. Load any dataset directly using Pandas:
   ```python
   import pandas as pd

   # Load Day 1 E-Commerce dataset
   df_ecommerce = pd.read_csv("day1/ecommerce.csv")
   display(df_ecommerce.head())

   # Load Day 2 Detective Challenge dataset
   df_mystery = pd.read_csv("day2/mystery_ecommerce.csv")
   display(df_mystery.head())
   ```

---

### Option 2: Local Environment (VS Code, Cursor, or JupyterLab)

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Hari-Nikesh-R/data_analytics_notebook.git
   cd data_analytics_notebook
   ```

2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python3 -m venv venv
   source venv/bin/activate    # On Windows: venv\Scripts\activate
   ```

3. **Install required dependencies:**
   ```bash
   pip install pandas openpyxl matplotlib seaborn jupyterlab
   ```

4. **Launch JupyterLab or Notebook:**
   ```bash
   jupyter lab
   ```

---

## 📚 Curriculum Breakdown

### 📘 [Day 1: Foundations & The Data Analytics Mindset](day1/README.md)
*From raw data to actionable business insights.*

- **Concepts Covered:**
  - **The Analytics Mindset:** Converting raw data $\rightarrow$ metrics $\rightarrow$ information $\rightarrow$ insights $\rightarrow$ business decisions.
  - **Data Taxonomy:** Numerical, Categorical (Nominal vs Ordinal), Temporal (DateTime), and Relational Keys.
  - **Structured vs Unstructured:** Tabular vs JSON vs customer text reviews.
  - **Python & Pandas Basics:** Variables, loops, DataFrames, and inspection (`.head()`, `.info()`, `.describe()`, `.shape`).
  - **Data Cleaning Masterclass:** Handling missing values (`.fillna()`, mode vs median), removing duplicates (`.drop_duplicates()`), outlier handling, and string normalization (`.str.strip().str.title()`).
  - **Feature Engineering:** Calculating gross revenues, discount percentages, and net sales.
  - **Data Manipulation:** Compound filtering (`&`, `|`), custom sorting, and multi-metric aggregations (`.groupby()`).
  - **Relational Joins:** INNER, LEFT, RIGHT, and OUTER merges between customer and transaction tables.
  - **Pivoting & Reshaping:** Cross-tabulation revenue matrices with `pd.pivot_table()`.
  - **Statistics & EDA:** Mean vs Median in right-skewed distributions, scatter plots, histograms, and avoiding the *Correlation $\neq$ Causation* fallacy.
  - **The 4 Types of Analytics:** Descriptive, Diagnostic, Predictive, and Prescriptive.

- **Datasets in `day1/`:**
  - [`day1/ecommerce.csv`](day1/ecommerce.csv): 100 multi-category e-commerce transactions across top Indian cities.
  - [`day1/customers.csv`](day1/customers.csv): Customer demographic profiles (`customer_id`, `name`, `age`, `city`).
  - [`day1/orders.csv`](day1/orders.csv): Order transactions linked to customers via `customer_id`.

- **Student Quiz & Assessment:**
  - [`day1/quiz/quiz.xlsx`](day1/quiz/quiz.xlsx): Formatted Excel quiz file with 25 curriculum-aligned, interactive questions covering scenarios like RPG game economies, streaming platform drops, and sneaker price distributions.
  - [`day1/quiz/quiz.csv`](day1/quiz/quiz.csv): LMS-compatible CSV ready for import into Quizizz, Canvas, Moodle, or Google Forms.

---

### 🕵️ [Day 2: The Data Detective Challenge — The Mystery of QuickMart's Leaking Profits](day2/README.md)
*An immersive, gamified forensic investigation.*

Step into the shoes of the **Lead Data Analyst & Retail Detective** at QuickMart, an online shopping platform experiencing soaring top-line sales but bleeding cash every week.

- **The Investigation Roadmap (100 XP + 10 Bonus XP):**
  - **Mission 1 (20 XP) — The Crime Scene:** Inspect and sanitize tampered logs (identifying duplicate clicks, NaN values, and corrupted data).
  - **Mission 2 (20 XP) — The Red Herring:** Unmask the CEO's "Average Spend Trap" using robust descriptive statistics (Mean vs Median).
  - **Mission 3 (20 XP) — The Cyber Heist Trail:** Track down midnight coupon exploiter `C999` using compound boolean filtering.
  - **Mission 4 (20 XP) — The Money Blackhole:** Uncover product return drains and vendor quality defects using multi-level `groupby`.
  - **Mission 5 (20 XP) — Cracking the Case:** Quantify total preventable financial bleed and deliver prescriptive business decisions.
  - **Bonus Boss Level (10 XP):** The 3-minute executive board pitch to the CEO.

- **Dataset in `day2/`:**
  - [`day2/mystery_ecommerce.csv`](day2/mystery_ecommerce.csv): The raw transaction log containing genuine transactions, network glitches, exploited discount loops, and defective shipment batches.

---

## 💡 Quick Code Cheatsheet for Loading Data

```python
import pandas as pd

# 1. Day 1: Single Unified E-Commerce Table
ecommerce = pd.read_csv("day1/ecommerce.csv")

# 2. Day 1: Relational Customer & Order Tables
customers = pd.read_csv("day1/customers.csv")
orders = pd.read_csv("day1/orders.csv")

# Join customers and orders
merged_data = orders.merge(customers, on="customer_id", how="inner")

# 3. Day 2: Forensic Challenge Table
mystery_data = pd.read_csv("day2/mystery_ecommerce.csv")
```

---

## 👥 Guide for Instructors & Students

- **For Students:**
  1. Begin with [Day 1 Guide](day1/README.md) to understand foundational concepts and run the code walkthroughs.
  2. Test your knowledge using the 25-question [Day 1 Quiz](day1/quiz/quiz.xlsx).
  3. Put your analytical skills to the test in the [Day 2 Mystery Challenge](day2/README.md) and earn your detective rank!
- **For Instructors:**
  1. The quiz files in [`day1/quiz/`](day1/quiz/) are pre-formatted for seamless upload to LMS platforms (Quizizz, Canvas, Kahoot, or Google Classroom).
  2. Use [`day2/mystery_ecommerce.csv`](day2/mystery_ecommerce.csv) as an in-class hackathon or lab assessment where students calculate their XP Scorecards.

---

Collab link : https://colab.research.google.com/drive/1TBjc0IoVtpQOlI2ADGNQclqqSQmKIq-e?usp=sharing