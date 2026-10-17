---
title: "Preservation"
teaching: 30
exercises: 15
---

:::::::::::::::::::::::::::::::::::::: questions

- Why does digital data need active preservation?
- Which file formats are safest for the long term?
- How can I tell whether a file has changed or been corrupted?
- What makes a repository trustworthy?
- How are very large datasets stored and moved?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain the threats to long-term access to digital data
- Choose preservation-friendly formats for geospatial data
- Explain fixity and checksums
- Describe the OAIS model and the signs of a trustworthy repository
- Recognize the tools and challenges of preserving very large datasets

::::::::::::::::::::::::::::::::::::::::::::::::

## Digital data does not keep itself

A printed map in a drawer can last centuries. A digital file can become unusable in a few years, without anyone
deleting it. The main threats are:

| Threat | Example |
|---|---|
| **Media failure** | Hard drives, USB sticks and optical discs fail with age, and a single failed drive can hold years of work |
| **Bit rot** (silent corruption) | A few bits flip during storage or copying, and a file no longer opens or, worse, opens with wrong values |
| **Format obsolescence** | No current software can read a format any more |
| **Loss of context** | The file survives but nobody knows what it means (no metadata or documentation) |
| **Organizational failure** | A lab closes, a student graduates, a cloud account lapses, a website goes offline |
| **Human error** | Accidental deletion or overwriting |

**Digital preservation** is the set of activities that keep data **accessible, readable, unchanged and
understandable** for as long as it is needed. Backups (covered in the Data Management module) protect against
media failure and human error; preservation also deals with formats, integrity and context over decades.

## Preservation-friendly formats

Formats most likely to remain readable are:

- **open**, with a published specification anyone can implement
- **widely used**, with many programs that can read them
- **well documented** and **stable** over time
- **not encrypted** or locked to particular software
- **lossless**, keeping all the original information

The U.S. Library of Congress publishes a **Recommended Formats Statement**, and many repositories publish
their own lists of preferred formats. For geospatial data, good choices are:

| Data | Preferred for preservation | Acceptable, or convert if possible |
|---|---|---|
| Vector | GeoPackage, GeoJSON (for modest sizes), and shapefile (complete with `.prj`) | File geodatabase, KML |
| Raster | GeoTIFF, including Cloud Optimized GeoTIFF; NetCDF for multidimensional data | Proprietary image formats; JPEG (lossy) |
| Tables | CSV (UTF-8 text) | Excel workbooks |
| Documents | PDF/A, plain text, Markdown | Word documents |
| Maps and project files | Export final maps as PDF/A or PNG | QGIS or ArcGIS project files (they depend on software versions and data paths) |

Keep a copy in the **original** format too, if conversion might lose something, and note the conversion in the
documentation.

## Fixity: has anything changed?

**Fixity** means being able to show that a file has not changed since it was stored. It is checked with a
**checksum** (or hash): a short code calculated from the file's contents, such as a SHA-256 or MD5 value. If even
one bit of the file changes, the checksum changes completely.

```
sha256  3f1a9c...e7b2  grocery_stores.gpkg
sha256  a84d02...19fc  data_dictionary.csv
```

Repositories calculate checksums when data is deposited and recheck them regularly, repairing any damaged copy
from another. You can do the same for important files: record checksums in a text file alongside the data, and
compare them after copying or moving data. Free tools exist on every operating system (for example
`certutil -hashfile file SHA256` on Windows, or `shasum -a 256 file` on macOS and Linux).

## Strategies for keeping data usable

- **Multiple copies in different places**, regularly checked (fixity), so that a damaged copy can be replaced
- **Migration**: converting data to a current format before the old one becomes unreadable
- **Emulation**: running old software on a simulated old computer (mostly used for software and complex
  digital objects)
- **Metadata and documentation**: so that the data can still be understood when its creators are gone
- **Persistent identifiers** (DOIs): so that the data can still be found even if web addresses change

## Repositories and the OAIS model

For most researchers, the best preservation strategy is to **deposit data in a repository** whose job is
preservation. Many repositories follow the **Open Archival Information System (OAIS)** reference model
(ISO 14721), which describes an archive in terms of the packages of information it handles:

| Package | What it is |
|---|---|
| **Submission Information Package (SIP)** | What the depositor provides: data, documentation, metadata |
| **Archival Information Package (AIP)** | What the archive stores long term, with added preservation metadata and checksums |
| **Dissemination Information Package (DIP)** | What users receive when they download |

OAIS also stresses that an archive must preserve data for a **designated community**: the people expected to use
it. For social scientists, that means documentation written for researchers who know the field but not your
project.

### Signs of a trustworthy repository

- It assigns **persistent identifiers** (DOIs) and keeps the landing page available even if data is withdrawn
- It has a clear **preservation policy** and commitment (how long, and what happens if it closes)
- It keeps **multiple copies** and checks **fixity**
- It requires **metadata** and reviews deposits
- It holds a certification such as **CoreTrustSeal**, which assesses repositories against a set of requirements
  for trustworthiness

## Very large datasets

Some datasets, such as satellite image archives, climate model output or national lidar, are far too large for
email, USB drives or ordinary cloud folders. Curating them raises new problems:

| Challenge | Approaches |
|---|---|
| **Storage cost** | Institutional research storage; cloud object storage (such as Amazon S3, Google Cloud Storage or Microsoft Azure); choosing what really needs keeping |
| **Moving data** | High-speed transfer services such as **Globus**, used by many universities and computing centers to move terabytes reliably between institutions |
| **Using without moving** | Cloud-optimized formats (Cloud Optimized GeoTIFF, Zarr, GeoParquet) let users read only the part they need over the web |
| **Describing collections** | Machine-readable metadata and catalogs, such as STAC for imagery |
| **Preservation over decades** | Format migration plans, documented processing so that derived products can be regenerated |

A useful question for large data: **does it need to be preserved, or can it be recreated?** Raw satellite
images are preserved by space agencies; a project may only need to preserve its code and the small derived
products.

::::::::::::::::::::::::::::::::::::: challenge

## Format choices for an archive

You are depositing a project's final data. Which formats would you use for each item?

1. Census tract polygons joined to ACS estimates, currently in an Esri file geodatabase
2. A land cover raster, currently in a proprietary image format
3. A survey spreadsheet with several tabs and colored cells marking problems
4. The final maps from your thesis, made in QGIS

:::::::::::::::: solution

1. **GeoPackage** (or GeoJSON if small), plus a CSV of the attribute table with GEOIDs as text
2. **GeoTIFF** with lossless compression, with its CRS and NoData value recorded
3. One **CSV** per tab, with the meaning of the colors turned into an explicit column (for example `flag_reason`),
   and a codebook
4. **PDF/A** or high-resolution **PNG** exports, plus the QGIS project and its data for anyone who wants to remake
   them (noting the QGIS version)

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

## Why checksums?

A collaborator copies 300 GB of imagery to an external drive and mails it to you. How can you be sure every file
arrived intact?

:::::::::::::::: solution

Ask the collaborator to calculate a checksum (such as SHA-256) for every file before sending, and to include the
list. After copying the files from the drive, calculate the checksums again and compare. Any file whose checksum
differs was corrupted and must be sent again. Transfer services such as Globus check integrity automatically.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Digital data is threatened by media failure, silent corruption, format obsolescence, loss of context and organizational change
- Preserve data in open, widely used, well-documented, lossless formats such as GeoPackage, GeoTIFF and CSV
- Checksums provide fixity: proof that a file has not changed
- Deposit data in a trustworthy repository that assigns persistent identifiers and has a preservation commitment
- Very large data needs research storage, transfer services such as Globus, and cloud-optimized formats

::::::::::::::::::::::::::::::::::::::::::::::::
