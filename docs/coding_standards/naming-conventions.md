# 🧾 Naming Conventions

Consistent naming improves collaboration, readability, and maintenance. This guide outlines our team’s naming conventions for variables, files, columns, functions, and other elements used across data and analytics work.

## 🔤 General Principles

- Be descriptive, concise, and unambiguous
- Use lowercase where possible
- Avoid acronyms unless universally understood (e.g., `URL`, `API`)
- Maintain consistency within and across projects
- Prefer clarity over cleverness

## 🐍 Variables & Function Names (Python, SQL)

- Use `snake_case`
- Names should reflect the variable’s purpose
- Avoid overly abbreviated names

```python
# ✅ Good
total_sales = 10000
def calculate_growth(current, previous):

# ❌ Avoid
TotalSales = 10000
def calcG(c, p):
```

## 📄 File & Folder Names (Markdown, Docs)

- Use kebab-case
- Keep names short and scoped to the content
- Avoid spaces or underscores
- Prefix numerically for ordered content if needed

```markdown
# ✅ Good
data-quality.md
01-introduction.md
visualization-guidelines/

# ❌ Avoid
DataQuality.md
data_quality.md
My Document.md
```

## 🗃️ SQL Table and Column Names

- Use snake_case, all lowercase
- Use plural for table names, singular for columns
- Avoid SQL reserved keywords

```sql
-- ✅ Good
SELECT order_id, customer_id FROM orders;

-- ❌ Avoid
SELECT OrderID, CustomerID FROM Orders;
```

## 📓 Notebooks & Scripts

- Combine topic + purpose + optional version
- Use snake_case or kebab-case, depending on tooling

```bash
explore_churn_drivers_v1.ipynb
generate_monthly_summary.py
```

## 📊 Metric & Model Naming

- Be explicit: include what, how, and units where helpful

```bash
churn_rate_pct
avg_session_length_minutes
model_accuracy_score
```

## 📈 Dashboard & Report Titles

- Use title case for readability
- Be clear and scoped (what + when or what + by what)

```markdown
✅ Customer Acquisition Trends – Q1 2025  
✅ Sales by Product and Region  
❌ Final Dashboard  
❌ Monthly Stuff  
```

## 🧼 Prefixes, Suffixes, and Other Notes

- Use tmp_, stg_, prod_ prefixes to indicate data pipeline stages
- Prefix files if order matters: 01-overview.md, 02-guidelines.md
- Avoid:
    - Reserved keywords (type, select, from)
    - Special characters or emojis in filenames

By following these conventions, we help ensure our work is clean, consistent, and easy for teammates and future-you to understand. 🙌