---
title: "Introduction to Data Curation"
teaching: 45
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions

- What is data curation?
- Why is data curation important in data science?
- What are the stages of the data curation lifecycle?
- How does good curation improve research quality and reproducibility?
- What are common challenges in managing data?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Define data curation and its purpose
- Understand the lifecycle of curated data
- Recognize best practices for organizing and managing datasets
- Identify common metadata and documentation standards
- Appreciate the role of data curation in reproducible science

::::::::::::::::::::::::::::::::::::::::::::::::

## What is Data Curation?

**Data curation** is the process of organizing, documenting, preserving, and maintaining data so that it remains useful, understandable, and reusable over time.

It includes:
- Cleaning and validating data
- Organizing files and formats
- Creating metadata
- Preserving datasets for long-term access

::::::::::::::::::::::::::::::::::::: callout

### Key Idea
Data curation is not just storing files — it is making data usable for future analysis.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Why Data Curation Matters

Poorly curated data can lead to:
- Lost files
- Confusing variable names
- Missing context
- Irreproducible research

Well-curated data helps:
- Ensure reproducibility
- Enable collaboration
- Improve data quality
- Support long-term preservation

### Example:
A dataset named `final_data_v2_revised_REAL_final.csv` gives little confidence or clarity.

A curated alternative:
`soil_moisture_2025_stationA_clean.csv`

---

## The Data Curation Lifecycle

Data curation happens throughout the life of a dataset.

### Typical Lifecycle Stages:

1. **Create / Collect**
2. **Organize**
3. **Document**
4. **Store / Backup**
5. **Preserve**
6. **Share / Publish**
7. **Reuse / Reanalyze**



::::::::::::::::::::::::::::::::::::: callout

### Important
Curation begins when data is created — not after the project ends.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Core Principles of Good Data Curation

### 1. Organization

Use clear folder structures.

Example:

project/
├── data_raw/
├── data_clean/
├── scripts/
├── outputs/
└── documentation/

---

### 2. Naming Conventions

Good file names should be:
- Descriptive
- Consistent
- Machine-readable

Example:
`river_discharge_monthly_2024.csv`

Avoid:
`data_new_latest2.csv`

---

### 3. Documentation

Every dataset should include documentation:
- README file
- Variable descriptions
- Units of measurement
- Data source notes

Example README includes:
- Project title
- Author
- Date created
- File descriptions

---

### 4. Metadata

Metadata = “data about data”

Examples:
- Who created the dataset?
- When was it collected?
- What instruments were used?
- What do columns mean?

::::::::::::::::::::::::::::::::::::: challenge

Why is metadata essential if someone else uses your dataset five years later?

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Data Cleaning vs Data Curation

These are related but different:

### Data Cleaning:
Fixes errors in data
- Missing values
- Typos
- Duplicates

### Data Curation:
Maintains long-term usability
- Documentation
- Preservation
- Versioning

Both are necessary.

---

## File Formats Matter

Choose formats that are:
- Open
- Reusable
- Non-proprietary

Preferred:
- CSV instead of XLSX
- TXT instead of DOCX for plain text
- GeoJSON instead of closed GIS formats when possible

---

## Version Control in Data Curation

Track changes to files over time.

Methods:
- Version numbering (`v1`, `v2`)
- Git / GitHub
- Changelogs

Example:
`survey_cleaned_v3.csv`

::::::::::::::::::::::::::::::::::::: callout

### Tip
Never overwrite original raw data.

Keep raw data unchanged.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Backup and Preservation

Use the 3-2-1 Rule:

- 3 copies of data
- 2 different storage types
- 1 offsite backup

Example:
- Local computer
- External drive
- Cloud storage

---

## FAIR Principles

Good curated data should be:

### F — Findable
Easy to locate

### A — Accessible
Available to authorized users

### I — Interoperable
Compatible with other systems

### R — Reusable
Well-documented and understandable

::::::::::::::::::::::::::::::::::::: callout

### FAIR Data = Better Science
The FAIR framework is widely used in research data management.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Common Challenges in Data Curation

- Inconsistent naming
- Missing metadata
- Lost context over time
- Proprietary formats
- Lack of backup

---

## Real-World Example

Imagine sharing a climate dataset without:
- Units
- Dates
- Sensor details

Even accurate data becomes nearly useless without context.

---

## Hands-On Exercise

### Task:
Create a curated folder structure for a sample project.

Include:
- Raw data folder
- Clean data folder
- README file
- Metadata sheet

---

## Accessibility and Ethics in Data Curation

Remember:
- Protect sensitive data
- Remove personal identifiers
- Follow privacy guidelines
- Respect licensing restrictions

---

## Final Takeaways

Good data curation:
- Saves time later
- Prevents mistakes
- Improves collaboration
- Makes research reproducible

::::::::::::::::::::::::::::::::::::: discussion

- Have you ever struggled with poorly organized data?
- What curation practice would improve your current workflow most?

::::::::::::::::::::::::::::::::::::::::::::::::