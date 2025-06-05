# 🔢 Versioning Guidelines

Consistent versioning helps teams understand what’s changed, when, and how much risk is involved. This guide outlines how we use **Semantic Versioning (SemVer)** across code, datasets, and deliverables.

## 🎯 Why Versioning?

- Communicates the impact of changes
- Improves collaboration and reproducibility
- Supports rollback and auditability
- Helps consumers of your work (colleagues, stakeholders, downstream tools)

## 📐 What Is Semantic Versioning?

We follow [Semantic Versioning 2.0.0](https://semver.org/):

**MAJOR.MINOR.PATCH**

- **MAJOR** – Breaking changes (structure, logic, API, format)
- **MINOR** – New features or additions (non-breaking)
- **PATCH** – Fixes, tweaks, or small changes (bug fixes, doc updates)

### Examples:
- `1.0.0` – First stable release
- `1.2.0` – Added a new column to the dataset
- `1.2.1` – Fixed a typo in the report
- `2.0.0` – Changed data format from CSV to Parquet (breaking)

## 🛠️ What to Version

### 📦 Code / Scripts
- Version in the `README.md` or inside the script (`__version__`)
- Tag versions in Git (e.g. `git tag v1.0.0`)
- Store changelogs in a `CHANGELOG.md`

### 🗃️ Datasets
- Store version in metadata (e.g. `metadata.yaml`, filename, or data catalog)
- Filename pattern: `dataset-name_v1.0.0.csv`
- Increment:
  - MAJOR – Changes to schema (column names, types)
  - MINOR – Add new fields or sources
  - PATCH – Fix typos, formatting, or refresh

### 📊 Dashboards & Reports
- Add version label to exported reports or titles
- Example: `Customer Trends Report v2.1.0 – Q2 2025`
- Consider versioning published dashboard URLs if needed

## ✏️ How to Track Versions

- Use Git tags (`v1.0.0`) for scripts and models
- Include version in:
  - `README.md`
  - `metadata.yaml` or `dataset_description.md`
  - Dashboard footers or file headers
- Optional: Use a `CHANGELOG.md` for ongoing edits

## 🔒 Tips and Reminders

- Don’t reset versions — they tell a story!
- Use consistent formatting (`v1.2.0`, not `V1.2` or `1_2`)
- Avoid using "final", "latest", or "new" in filenames

```bash
✅ model_output_v1.1.0.pkl
❌ model_output_final.pkl
```

- Archive old versions in a clear folder structure (e.g. /archive/)

📚 Example: Dataset Versioning Over Time
| Version | Change Type     | Description                           |
|---------|------------------|---------------------------------------|
| 1.0.0   | Initial Release  | First schema, 10 fields, 100K rows    |
| 1.1.0   | Minor Addition   | Added `region` and `signup_date`      |
| 1.1.1   | Patch Fix        | Corrected missing values in `age`     |
| 2.0.0   | Breaking Change  | Split into two linked datasets        |

By adopting semantic versioning, we ensure transparency, reliability, and ease of collaboration across data and analytics projects.