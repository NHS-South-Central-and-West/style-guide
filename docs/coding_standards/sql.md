# SQL Style Guide

> A gold-standard guide for writing clean, consistent, and maintainable SQL across all NHS South, Central, and West projects.

## 📘 General Principles

- Prioritise **readability** and **clarity** over cleverness.
- Be **consistent** – follow this guide for all SQL code (scripts, notebooks, embedded SQL).
- Use **comments** to clarify complex logic and assumptions.
- Where possible, write **declarative** SQL (what, not how).

## 🆙 Capitalisation

- **SQL keywords:** `UPPERCASE`  
  ✅ `SELECT`, `FROM`, `WHERE`, `JOIN`, `GROUP BY`

- **Identifiers (tables, columns, aliases):** `snake_case`  
  ✅ `patient_id`, `appointment_date`

## 🧱 Formatting & Layout

### 1. Line Breaks and Indentation

- Break long queries into blocks with **consistent indentation**.
- One clause per line, one column per line in `SELECT`.

```sql
SELECT
    patient_id,
    first_name,
    last_name
FROM
    patients
WHERE
    status = 'active'
ORDER BY
    last_name;
```

### 2. Joins
- Always specify the type of join (INNER, LEFT, etc.).
- Align ON with JOIN.

```sql
SELECT
    a.patient_id,
    b.appointment_date
FROM
    patients a
INNER JOIN
    appointments b ON a.patient_id = b.patient_id;
```

### 3. Commas
- Place commas at the end of lines, not the beginning.

✅ Good:

```sql
SELECT
    first_name,
    last_name
FROM patients;
```

❌ Avoid:

```sql
SELECT
    first_name
  , last_name
FROM patients;
```

### 🧾 Aliases
- Use short but meaningful aliases (p for patients, a for appointments).
- Avoid single-letter aliases unless in small subqueries.

```sql
SELECT
    p.patient_id,
    p.full_name
FROM
    patients p;
```

### 🏷 Naming Conventions
- Use snake_case for all table and column names.
- Recommended prefixes:
    - dim_ for dimension tables (dim_patient)
    - fact_ for fact tables (fact_appointments)
    - stg_ for staging tables
- Avoid reserved words: user, date, etc.

### 💬 Comments
- Use -- for short comments.
- Use /* */ for longer explanations or blocks.

```sql
-- Get patients born before 2000
SELECT * FROM patients WHERE birth_date < '2000-01-01';

/*
This block retrieves recent appointments
from the past 30 days.
*/
```

### 📦 CTEs (Common Table Expressions)
- Prefer CTEs over subqueries for readability.
- Use descriptive names for CTEs.

```sql
WITH recent_appointments AS (
    SELECT * FROM appointments
    WHERE appointment_date >= CURRENT_DATE - INTERVAL '30 days'
)
SELECT * FROM recent_appointments;
```

### ⚠️ NULL Handling
- Always handle NULL explicitly.

```sql
WHERE discharge_date IS NOT NULL
```

### 🚫 Avoid
- SELECT * – list required columns explicitly.
- Non-standard SQL unless necessary.
- Implicit joins (FROM a, b WHERE a.id = b.id)
- Unqualified columns in multi-table queries.

### 📁 Version Control & Documentation
- All SQL scripts must be in version control (e.g. Git).
- Use a README.md in each SQL directory to document:
    - Script purpose
    - Inputs/outputs
    - Data source or dependencies
- Use inline comments for complex joins or logic.

### ✅ Optional Extras
- Integrate SQLFluff or another SQL linter in your CI pipeline.
- Consider pre-commit hooks to catch linting/style issues before merging.
- Maintain example queries for NHS-specific data pipelines.
