---
title: "Documentation"
teaching: 25
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- What documentation should accompany a dataset?
- What goes in a README file?
- How do I document variables, sources and processing steps?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Write a README file for a geospatial dataset
- Document variables in a codebook or data dictionary
- Record provenance: sources, processing steps and software
- Explain how to cite the data you use

::::::::::::::::::::::::::::::::::::::::::::::::

## Metadata and documentation

**Metadata** (the previous episode) is structured and short, so that catalogs and search engines can read it.
**Documentation** is the fuller, human-readable explanation that lets someone actually *use* the data:
how it was collected, what every variable means, what was done to it, and what to watch out for.

A well-documented dataset usually has:

| Document | Answers |
|---|---|
| **README** | What is this, who made it, how is it organized, and how do I use and cite it? |
| **Data dictionary or codebook** | What does each field mean, in what units, with what allowed values? |
| **Methods and provenance notes** | How was the data collected and processed, step by step? |
| **Code** | Exactly how outputs were produced from inputs |
| **License** | What others may do with it |

## The README file

A **README** is a plain-text file (often `README.md` or `README.txt`) at the top level of a dataset. It is the
first thing anyone opens. Write it as if for a capable stranger who knows nothing about your project.

A template for a geospatial dataset:

```markdown
# Grocery and Food Stores, Lafayette and West Lafayette, Indiana, 2026

## Overview
Point locations of 64 grocery and food stores, compiled to study food access.
Created by: A. Researcher (Purdue University), ORCID 0000-0000-0000-0000
Contact: a.researcher@example.edu
Date of data: October 2026. Date of this version: 2026-11-01 (version 1.0)

## Files
- grocery_stores.gpkg    the store points (layer: grocery_stores)
- data_dictionary.csv    description of every field
- methods.md             collection and processing steps
- LICENSE.txt            Open Database License (ODbL) 1.0

## Coordinate reference system
EPSG:4326 (WGS 84, latitude and longitude)

## Sources
Store locations: (c) OpenStreetMap contributors, downloaded 2026-10-17 via the Overpass API.
City limits: U.S. Census Bureau, 2024 cartographic boundary files (places).

## Methods (summary)
Food stores were extracted from OpenStreetMap; 12 were verified in the field in
March 2026. See methods.md for details.

## Known limitations
Not all stores were field verified. Small or new stores may be missing.

## How to cite
Researcher, A. (2026). Grocery and Food Stores, Lafayette and West Lafayette,
Indiana, 2026 (Version 1.0) [Data set]. Purdue University Research Repository.
https://doi.org/10.xxxx/xxxxx

## License
Open Database License (ODbL) 1.0, because the data derives from OpenStreetMap.
```

Keep it current: a README that describes an old version of the data is worse than none.

## Codebooks and data dictionaries

A **codebook** (the usual term for survey data) or **data dictionary** (the usual term in GIS and databases)
describes every variable. For each one, record:

- the **name** exactly as it appears in the file
- a **label** or description in plain language
- the **type** (text, integer, decimal, date)
- **units** (meters, dollars, percent) and, for money, the year of the dollars
- **allowed values** and what each code means (`1 = Yes`, `2 = No`, `9 = Not asked`)
- how **missing values** are coded and why they occur
- the **source** of the variable, especially if it was calculated or came from another dataset

Compare:

| Poor | Better |
|---|---|
| `pct2`: percent | `pct_no_vehicle`: Percent of occupied housing units with no vehicle available. Decimal, 0 to 100. Calculated as B08201_002E / B08201_001E x 100 from ACS 2020-2024 5-year estimates. Null where the tract has no households. |

The **Designing Your Data** episode of the Data Management module shows how to build a data dictionary before
collecting data; when you curate the data, that same dictionary becomes part of the documentation.

## Provenance: sources and processing

To trust or reproduce a dataset, others need its **provenance**: every source and every step.

### Record your sources precisely

For each input, note:

- the **publisher** and **product name**
- the **version**, **vintage** or **year** (for example "TIGER/Line 2024" or "ACS 2020-2024 5-year estimates")
- the **URL** or API request
- the **date you downloaded** it
- its **license**

### Record what you did

Processing steps are easy to forget. Record them as you go:

- **Scripts** are the best record: they document every step exactly and can be rerun. Comment them, and number
  them in the order they run.
- For work done by pointing and clicking, keep a **processing log**: the date, the tool, its settings, and the
  input and output file names. QGIS also keeps a **history** of Processing tools you have run (Processing >
  History), including their parameters.
- Note the **software and versions** used (for example, QGIS 3.40 or Python 3.12 with geopandas 1.0), because
  results can change between versions.

::::::::::::::::::::::::::::::::::::: callout

## Document decisions, not just steps

The most valuable notes record **why**: why 800 m was chosen as the walking threshold, why two stores were
removed, why a particular census year was used. Steps can sometimes be reconstructed from code; reasons cannot.

::::::::::::::::::::::::::::::::::::::::::::::::

## Citing data

Cite datasets the way you cite articles, so their creators receive credit and readers can find the exact data.
A data citation usually includes:

**Creator (Year). *Title* (Version) [Data set]. Publisher. Persistent identifier or URL.**

For example:

> U.S. Census Bureau. *American Community Survey 5-Year Estimates, 2020-2024*, Table B08201: Household Size by
> Vehicles Available [Data set]. Census Data API. Retrieved 2026-10-17 from https://api.census.gov/data/2024/acs/acs5

For data without a DOI, include the access date, since the content behind a URL can change.

::::::::::::::::::::::::::::::::::::: challenge

## Improve the codebook entries

Rewrite each of these as a useful codebook entry:

1. `inc`: income
2. `dist`: distance to store
3. `type`: 1, 2, 3

:::::::::::::::: solution

1. `med_hh_income`: Median household income in the past 12 months, in 2024 inflation-adjusted U.S. dollars.
   Integer. Source: ACS 2020-2024 5-year estimates, variable B19013_001E. Null where the Census Bureau could not
   calculate an estimate (annotation code -666666666 in the source).
2. `dist_nearest_supermarket_m`: Distance along the road network from the tract's population-weighted center to
   the nearest supermarket, in meters. Decimal. Calculated in QGIS with the Shortest path tool on TIGER/Line 2024
   roads.
3. `store_type`: Type of store. Text. Allowed values: `Supermarket`, `Small market`, `Convenience`, `Other`.
   (Better still, store the words rather than numeric codes; if codes are kept, list what each number means.)

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

## Write a README

Write a short README for a dataset you have created or used (or for the census tract map of households
without a car from the Data Collection module). Include at least: a title, creator and contact, the files, the
coordinate reference system, sources, a summary of methods, limitations, how to cite it and the license.

:::::::::::::::: solution

Answers will vary. Check your README against these questions:

- Could a stranger tell what the data is and where and when it describes, in under a minute?
- Are all files listed and explained?
- Is the coordinate reference system given as an EPSG code?
- Is every source named, with its version and download date?
- Are known limitations stated?
- Is there a citation and a license?

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Documentation is the human-readable explanation that lets others use data correctly
- Every dataset needs a README covering what, who, when, where, files, CRS, sources, methods, limitations, citation and license
- A codebook or data dictionary describes each variable's meaning, type, units, values and missing-value codes
- Record provenance: precise sources, every processing step, software versions, and the reasons for decisions
- Cite datasets with creator, year, title, version, publisher and a persistent identifier or URL with access date

::::::::::::::::::::::::::::::::::::::::::::::::
