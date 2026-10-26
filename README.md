# Matplotlib

# Matplotlib Complete Notes for Beginners

A beginner-friendly guide to **Matplotlib in Python**, including concepts, examples, chart types, and a practical Company Account Management mini-project.

## 📚 Table of Contents

- [1. Introduction](#1-introduction)
- [2. Installation](#2-installation)
- [3. Import Matplotlib](#3-import-matplotlib)
- [4. Basic Line Chart](#4-basic-line-chart)
- [5. Bar Chart](#5-bar-chart)
- [6. Horizontal Bar Chart](#6-horizontal-bar-chart)
- [7. Pie Chart](#7-pie-chart)
- [8. Scatter Plot](#8-scatter-plot)
- [9. Histogram](#9-histogram)
- [10. Multiple Lines](#10-multiple-lines)
- [11. Matplotlib with Pandas](#11-matplotlib-with-pandas)
- [12. Matplotlib with NumPy](#12-matplotlib-with-numpy)
- [13. Save Charts](#13-save-charts)
- [14. Company Account Mini-Project](#14-company-account-mini-project)
- [15. NumPy vs Pandas vs Matplotlib vs TensorFlow](#15-numpy-vs-pandas-vs-matplotlib-vs-tensorflow)
- [16. Interview Questions](#16-interview-questions)
- [17. Practice Exercises](#17-practice-exercises)

## 1. Introduction

**Matplotlib** is a Python library used to create graphs, charts, and data visualizations.

### Why use Matplotlib?

- Visualize financial data.
- Compare income and expenses.
- Analyze monthly financial trends.
- Create account-wise expense reports.
- Display charts in data analysis projects.

## 2. Installation

Install Matplotlib using pip:

```bash
pip install matplotlib
```

Install all required libraries for this tutorial:

```bash
pip install matplotlib pandas numpy
```

## 3. Import Matplotlib

```python
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
```

- `matplotlib.pyplot`: Creates charts and graphs.
- `plt`: Standard alias for pyplot.
- `pandas`: Handles tabular data.
- `numpy`: Performs numerical calculations.

## 4. Basic Line Chart

A line chart displays changes in data over time.

```python
import matplotlib.pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May"]
income = [50000, 60000, 55000, 75000, 80000]

plt.plot(months, income, marker="o")

plt.title("Monthly Company Income")
plt.xlabel("Month")
plt.ylabel("Income (INR)")

plt.grid(True)
plt.show()
```

### Important functions

| Function | Description |
|---|---|
| `plt.plot()` | Creates a line chart |
| `plt.title()` | Sets the chart title |
| `plt.xlabel()` | Labels the X-axis |
| `plt.ylabel()` | Labels the Y-axis |
| `plt.grid()` | Displays grid lines |
| `plt.show()` | Displays the chart |

## 5. Bar Chart

A bar chart compares values across categories.

```python
import matplotlib.pyplot as plt

accounts = ["Rent", "Travel", "Electricity", "Salary"]
expenses = [15000, 8000, 3000, 40000]

plt.bar(accounts, expenses)

plt.title("Account-Wise Expenses")
plt.xlabel("Account")
plt.ylabel("Amount (INR)")

plt.show()
```

**Real-world use:** Compare different expense categories in a company accounting system.

## 6. Horizontal Bar Chart

Use a horizontal bar chart when category names are long.

```python
import matplotlib.pyplot as plt

accounts = ["Office Rent", "Employee Salary", "Electricity", "Travel"]
expenses = [15000, 40000, 3000, 8000]

plt.barh(accounts, expenses)

plt.title("Company Expense Comparison")
plt.xlabel("Amount (INR)")
plt.ylabel("Account")

plt.show()
```

## 7. Pie Chart

A pie chart displays the proportion of each category within a total.

```python
import matplotlib.pyplot as plt

accounts = ["Rent", "Travel", "Electricity", "Salary"]
expenses = [15000, 8000, 3000, 40000]

plt.pie(
    expenses,
    labels=accounts,
    autopct="%1.1f%%",
    startangle=90
)

plt.title("Expense Distribution")
plt.show()
```

### Important parameters

- `labels`: Displays category names.
- `autopct`: Displays percentages.
- `startangle`: Rotates the chart.

## 8. Scatter Plot

A scatter plot helps explore relationships between two numerical variables.

```python
import matplotlib.pyplot as plt

transaction_numbers = [1, 2, 3, 4, 5, 6]
amounts = [1000, 5000, 3000, 12000, 8000, 20000]

plt.scatter(transaction_numbers, amounts)

plt.title("Transaction Amount Analysis")
plt.xlabel("Transaction Number")
plt.ylabel("Amount (INR)")

plt.show()
```

## 9. Histogram

A histogram shows the distribution of numerical data.

```python
import matplotlib.pyplot as plt

amounts = [
    1000, 1500, 2000, 3000, 3500,
    5000, 6000, 8000, 12000, 15000,
    20000, 25000, 30000
]

plt.hist(amounts, bins=5)

plt.title("Transaction Amount Distribution")
plt.xlabel("Amount Range (INR)")
plt.ylabel("Number of Transactions")

plt.show()
```

## 10. Multiple Lines

Compare monthly income and expenses in the same chart.

```python
import matplotlib.pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May"]

income = [50000, 60000, 55000, 75000, 80000]
expenses = [30000, 35000, 40000, 45000, 50000]

plt.plot(months, income, marker="o", label="Income")
plt.plot(months, expenses, marker="o", label="Expenses")

plt.title("Monthly Income vs Expenses")
plt.xlabel("Month")
plt.ylabel("Amount (INR)")

plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```

`plt.legend()` displays the labels for the plotted data series.

## 11. Matplotlib with Pandas

Pandas processes the data, and Matplotlib visualizes the results.

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.DataFrame({
    "Account": ["Rent", "Travel", "Electricity", "Salary"],
    "Amount": [15000, 8000, 3000, 40000]
})

account_totals = df.groupby("Account")["Amount"].sum()

account_totals.plot(kind="bar")

plt.title("Company Account Expense Report")
plt.xlabel("Account")
plt.ylabel("Amount (INR)")
plt.xticks(rotation=30)

plt.tight_layout()
plt.show()
```

## 12. Matplotlib with NumPy

NumPy generates numerical arrays, and Matplotlib displays the values graphically.

```python
import numpy as np
import matplotlib.pyplot as plt

months = np.arange(1, 13)

income = np.array([
    50000, 52000, 55000, 53000,
    60000, 65000, 62000, 70000,
    72000, 75000, 78000, 85000
])

plt.plot(months, income, marker="o")

plt.title("Yearly Income Trend")
plt.xlabel("Month Number")
plt.ylabel("Income (INR)")

plt.show()
```

## 13. Save Charts

Save a chart as an image file.

```python
import matplotlib.pyplot as plt

months = ["Jan", "Feb", "Mar"]
income = [50000, 60000, 55000]

plt.plot(months, income, marker="o")
plt.title("Monthly Income")

plt.savefig("monthly_income.png", dpi=300, bbox_inches="tight")
plt.show()
```

- `dpi=300`: Sets image resolution.
- `bbox_inches="tight"`: Reduces unnecessary whitespace.

## 14. Company Account Mini-Project

### Project Objective

Create a simple financial dashboard to analyze monthly company income and expenses.

### Features

- Monthly income report.
- Monthly expense report.
- Income-versus-expenses chart.
- Difference between income and expenses.
- Financial trend visualization.

### Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt

# Create sample financial data
df = pd.DataFrame({
    "Month": ["Jan", "Feb", "Mar", "Apr", "May"],
    "Income": [50000, 60000, 55000, 75000, 80000],
    "Expenses": [30000, 35000, 40000, 45000, 50000]
})

# Calculate the difference
df["Difference"] = df["Income"] - df["Expenses"]

# Display the report
print("Company Financial Report")
print(df)

print("\nTotal Income:", df["Income"].sum())
print("Total Expenses:", df["Expenses"].sum())
print("Total Difference:", df["Difference"].sum())

# Chart 1: Income vs Expenses
plt.figure(figsize=(9, 5))

plt.plot(df["Month"], df["Income"], marker="o", label="Income")
plt.plot(df["Month"], df["Expenses"], marker="o", label="Expenses")

plt.title("Monthly Income and Expenses")
plt.xlabel("Month")
plt.ylabel("Amount (INR)")
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.savefig("income_expenses.png", dpi=300)
plt.show()

# Chart 2: Difference
plt.figure(figsize=(9, 5))

plt.bar(df["Month"], df["Difference"])

plt.title("Monthly Income Minus Expenses")
plt.xlabel("Month")
plt.ylabel("Difference (INR)")
plt.tight_layout()
plt.savefig("monthly_difference.png", dpi=300)
plt.show()
```

### Sample Output

```text
Company Financial Report

  Month  Income  Expenses  Difference
0   Jan   50000     30000       20000
1   Feb   60000     35000       25000
2   Mar   55000     40000       15000
3   Apr   75000     45000       30000
4   May   80000     50000       30000

Total Income: 320000
Total Expenses: 200000
Total Difference: 120000
```

**Note:** This project demonstrates simple income-minus-expenses analysis. It is not a complete profit-and-loss statement or double-entry accounting system.

## 15. NumPy vs Pandas vs Matplotlib vs TensorFlow

| Library | Purpose | Example |
|---|---|---|
| NumPy | Numerical computing | Array calculations |
| Pandas | Data analysis | Voucher reports |
| Matplotlib | Data visualization | Financial charts |
| TensorFlow | Machine learning | Expense forecasting |

### Typical workflow

1. Load transaction data from PostgreSQL or CSV.
2. Use Pandas to clean and organize records.
3. Use NumPy for numerical calculations.
4. Use Matplotlib to create charts.
5. Use TensorFlow when you need a trained predictive model.

## 16. Interview Questions

**Q1. What is Matplotlib?**

Matplotlib is a Python library used to create charts, graphs, and data visualizations.

**Q2. What is pyplot?**

Pyplot is a Matplotlib module that provides functions for creating charts.

**Q3. What is the difference between a bar chart and a histogram?**

A bar chart compares categories, whereas a histogram displays the distribution of numerical data in intervals.

**Q4. What does `plt.show()` do?**

It displays the chart.

**Q5. How do you save a chart?**

Use `plt.savefig("chart.png")`.

**Q6. Why use Matplotlib with Pandas?**

Pandas organizes and analyzes tabular data, while Matplotlib visualizes the results.

**Q7. What does `plt.legend()` do?**

It displays labels for chart elements that have been assigned labels.

**Q8. What is a scatter plot?**

A scatter plot displays points representing pairs of numerical values.

**Q9. What is a histogram?**

A histogram displays the frequency distribution of numerical values.

**Q10. How can Matplotlib help in a Company Account system?**

It can visualize monthly income, expenses, account balances, and financial trends.

## 17. Practice Exercises

Try to solve these exercises yourself.

1. Create a line chart showing monthly income.
2. Create a bar chart comparing Rent, Travel, and Salary.
3. Create a pie chart showing expense percentages.
4. Create a scatter plot for transaction amounts.
5. Create a histogram of transaction values.
6. Display income and expenses on the same chart.
7. Save a chart as `report.png`.
8. Read financial data using Pandas and plot account-wise expenses.

## Quick Revision

| Function | Use |
|---|---|
| `plt.plot()` | Line chart |
| `plt.bar()` | Vertical bar chart |
| `plt.barh()` | Horizontal bar chart |
| `plt.pie()` | Pie chart |
| `plt.scatter()` | Scatter plot |
| `plt.hist()` | Histogram |
| `plt.title()` | Chart title |
| `plt.xlabel()` | X-axis label |
| `plt.ylabel()` | Y-axis label |
| `plt.legend()` | Display legend |
| `plt.grid()` | Display grid |
| `plt.savefig()` | Save chart |
| `plt.show()` | Display chart |

## Conclusion

Matplotlib is an important library for data visualization in Python. Combined with NumPy and Pandas, it helps build financial reports, data analysis projects, and dashboards.

**Next learning step:** Seaborn, followed by TensorFlow fundamentals and an AI-powered Company Account Management System.
