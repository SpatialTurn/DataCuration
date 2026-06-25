---
title: "Additional Readings"
teaching: 30
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions

- What is data curation and why does it matter for research?
- What practical steps can I take to keep my data organized and reusable?
- What are the FAIR principles?
- How do I publish and share research data at scale?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand the purpose and lifecycle of data curation
- Apply practical organization, naming, and documentation standards to research data
- Describe the FAIR principles and why they matter for reproducibility
- Know how to use institutional repositories (PURR) and data transfer tools (Globus) to publish and share data

::::::::::::::::::::::::::::::::::::::::::::::::

## What Is Data Curation?

**Data curation** is the process of organizing, documenting, preserving, and maintaining data so that it remains useful, understandable, and reusable over time. It is not just storing files — it is making data usable for future analysis, whether by you, your collaborators, or researchers you have never met.

Poorly curated data leads to lost files, confusing variable names, missing context, and irreproducible results. Well-curated data saves time, prevents mistakes, enables collaboration, and makes research reproducible.

Consider the difference:

- `final_data_v2_revised_REAL_final.csv` — tells you almost nothing
- `soil_moisture_2025_stationA_clean.csv` — tells you the variable, year, location, and processing stage

Curation begins when data is created, not after the project ends.

---

## The Data Curation Lifecycle

Data curation is not a one-time task. It happens throughout the life of a dataset:

1. **Create / Collect** — data is generated from instruments, surveys, fieldwork, APIs, or computational models
2. **Organize** — files are structured into a logical folder hierarchy
3. **Document** — metadata and README files are written to explain what the data contains
4. **Store / Backup** — data is saved redundantly across multiple locations
5. **Preserve** — data is archived in stable, open formats for long-term access
6. **Share / Publish** — data is deposited in a repository and assigned a permanent identifier
7. **Reuse / Reanalyze** — others discover, cite, and build on the data

For small projects this cycle may happen on a single laptop. For large collaborative projects it may span multiple institutions, countries, and automated pipelines. The principles are the same — the infrastructure scales.

---

## Practical Data Organization

### Folder Structure

A clear folder hierarchy makes it easy to find files and reproduce your workflow. A common pattern:

```
project/
├── data_raw/        ← original, untouched data
├── data_clean/      ← processed and analysis-ready data
├── scripts/         ← code that transforms raw → clean
├── outputs/         ← figures, maps, tables
└── documentation/   ← README, metadata, data dictionary
```

Write your scripts so that they read from `data_raw/` and save results to `outputs/`. This way you can always reproduce the full workflow from the original data.

### Naming Conventions

Good file names are descriptive, consistent, and machine-readable:

- `river_discharge_monthly_2024.csv` — clear
- `data_new_latest2.csv` — unclear

Avoid spaces, special characters, and ambiguous version labels. Use dates in `YYYY-MM-DD` format so files sort chronologically.

### Documentation

Every dataset should include a **README** file that covers:

- Project title and author
- Date created and last updated
- Description of each file
- Variable names and units of measurement
- Data source and collection method
- Any known limitations or gaps

The README is the single most important piece of documentation you can write. If someone finds your dataset five years from now, the README is what makes it usable or useless.

### Metadata

Metadata is "data about data" — structured information that describes what a dataset contains, how it was collected, and what the fields mean. Good metadata answers: who created it, when, with what instruments, and what do the columns represent?

For geospatial data, metadata also includes the coordinate reference system, spatial extent, and resolution.

---

## File Formats

Choose formats that are open, widely supported, and non-proprietary whenever possible:

- **CSV** over XLSX for tabular data
- **GeoJSON** or **GeoPackage** over proprietary GIS formats
- **GeoTIFF** for raster data (already georeferenced and widely supported)
- **Plain text** (TXT, MD) over DOCX for documentation

Open formats ensure your data remains readable regardless of which software is available in the future.

---

## Version Control

Track changes to your data and code over time. Two complementary approaches:

- **Version numbering** for data files — `survey_cleaned_v1.csv`, `survey_cleaned_v2.csv`, with a changelog documenting what changed between versions
- **Git / GitHub** for code and documentation — tracks every change with a full history

::::::::::::::::::::::::::::::::::::: callout

### Never Overwrite Raw Data

Keep your original raw data unchanged in `data_raw/`. All cleaning and transformation should produce new files in `data_clean/`. If something goes wrong, you can always start over from the original.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Backup: The 3-2-1 Rule

- **3** copies of your data
- **2** different storage types (e.g., local drive + cloud)
- **1** offsite backup

For example: your laptop, an external hard drive, and a cloud service. If any one fails, you still have two copies.

---

## FAIR Principles

The FAIR framework is the widely adopted standard for research data management. Curated data should be:

- **Findable** — stored in a searchable repository with a persistent identifier (like a DOI)
- **Accessible** — available to authorized users through standard protocols
- **Interoperable** — uses open formats and standard vocabularies so it works with other tools and datasets
- **Reusable** — documented thoroughly enough that someone else can understand and use it without contacting you

FAIR does not mean all data must be public — it means data should be *as open as possible and as closed as necessary*, with clear access conditions.

---

## Publishing Data: Institutional Repositories

When curated data is deposited into a repository, it receives a permanent identifier, becomes discoverable worldwide, and can be cited in publications just like a journal article.

### PURR (Purdue University Research Repository)

[PURR](https://purr.purdue.edu/) is Purdue University's platform for publishing and preserving research data. It allows researchers to:

- Store curated datasets securely
- Assign DOIs (Digital Object Identifiers) so others can cite the data
- Share data publicly or with restricted access
- Meet data management requirements from funding agencies and journals

Repositories like PURR protect data from loss and make it reusable beyond the original project. Many universities and funding agencies now require a data management plan that includes repository deposit.

---

## Sharing Large Datasets: Globus

Some datasets — satellite imagery archives, climate model simulations, high-resolution remote sensing data — are too large for email, USB drives, or standard cloud sharing. These require dedicated transfer infrastructure.

### What Is Globus?

[Globus](https://www.globus.org/) is a research data transfer platform widely used in academia. It supports:

- Secure, high-volume transfers (terabytes between institutions)
- Automatic retry and verification (no babysitting long transfers)
- Scheduled and automated workflows
- Transfers between institutional HPC clusters, cloud storage, and personal machines

For example, a researcher in Indiana can transfer 5 TB of satellite data to collaborators in Europe reliably and securely, without worrying about interrupted connections or corrupted files.

---

## Ethics and Privacy

Research data often contains sensitive information. Before sharing:

- Remove personal identifiers from survey and demographic data
- Follow your institution's IRB (Institutional Review Board) guidelines
- Respect licensing restrictions on data you did not collect yourself
- Consider aggregation levels carefully for geospatial data — fine-grained location data can expose individuals even when names are removed

---

:::::::::::::::::::::::::::::::::::: challenge

### Exercise: Curate a Sample Project

Create a folder structure for a hypothetical research project on urban heat islands in your city. Include:

1. A `data_raw/` folder (what files would go here?)
2. A `data_clean/` folder
3. A `scripts/` folder
4. A `documentation/` folder containing a brief README (3–5 sentences describing the project, data sources, and key variables)

If time allows, discuss with a partner: what metadata would someone need to reuse your dataset five years from now?

::::::::::::::::::::::::::::::::::::::::::::::::

---

::::::::::::::::::::::::::::::::::::: keypoints

- Data curation is an ongoing process that begins when data is created, not after a project ends.
- Practical habits — clear folder structures, descriptive file names, README files, and open formats — are the foundation of good curation.
- The FAIR principles (Findable, Accessible, Interoperable, Reusable) are the standard framework for research data management.
- Institutional repositories like PURR provide permanent, citable homes for research data.
- Large-scale data sharing relies on tools like Globus that handle high-volume transfers reliably.

::::::::::::::::::::::::::::::::::::::::::::::::
