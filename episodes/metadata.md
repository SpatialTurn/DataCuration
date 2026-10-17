---
title: "Metadata"
teaching: 30
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- What is metadata, and what kinds are there?
- What should a metadata record for a geospatial dataset include?
- Which metadata standards are used for geospatial and social science data?
- How can I create metadata in QGIS?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Define metadata and distinguish descriptive, administrative, structural and technical metadata
- List the essential elements of geospatial metadata
- Recognize the main metadata standards and when each is used
- Write a basic metadata record for a dataset

::::::::::::::::::::::::::::::::::::::::::::::::

## Data about data

**Metadata** is structured information that describes a dataset. It answers the questions a stranger would
ask before using your data: *What is it? Who made it? When and where does it describe? How was it made? How
accurate is it? Can I use it, and how do I cite it?*

Imagine finding a file called `stores.gpkg` with 64 points and no description. Are they grocery stores or
hardware stores? Verified or guessed? From 2015 or 2026? Without metadata, even accurate data is close to
useless, and it cannot be found by searching a catalog.

## Kinds of metadata

| Kind | Describes | Examples |
|---|---|---|
| **Descriptive** | What the data is, so it can be found and understood | Title, abstract, keywords, creator, subject, spatial and temporal coverage |
| **Administrative** | How it can be managed and used | License and rights, access restrictions, contact, funding, **provenance** |
| **Structural** | How it is organized | Files and how they relate, layers in a GeoPackage, tables and keys |
| **Technical** | How it is encoded | File format, size, coordinate reference system, resolution, software used |

**Provenance** (or **lineage**) deserves special mention: the record of where data came from and every
process applied to it. It is what allows others to judge quality and reproduce results.

## What geospatial metadata should include

| Element | Example for the grocery store dataset |
|---|---|
| **Title** | Grocery and food stores, Lafayette and West Lafayette, Indiana, 2026 |
| **Abstract** | What the data contains, why it was created and how it can be used |
| **Keywords** | food access, grocery stores, SNAP, Indiana, Tippecanoe County |
| **Creator and contact** | Names, affiliation and an email or ORCID |
| **Spatial extent** | A bounding box: west -86.97, east -86.77, south 40.35, north 40.50 |
| **Temporal extent** | The period the data describes: October 2026 |
| **Coordinate reference system** | EPSG:4326 (WGS 84) |
| **Scale or resolution** | Positional accuracy about 5 to 10 m |
| **Lineage** | Downloaded from OpenStreetMap on a stated date; filtered to food stores; cleaned in QGIS; spot-checked in the field |
| **Attribute information** | Each field, its meaning, type and allowed values (or a link to the data dictionary) |
| **Data quality** | Completeness, known gaps and how it was checked |
| **License and constraints** | Open Database License (because it derives from OpenStreetMap) |
| **Distribution** | Where and in which formats it can be obtained; a DOI if published |
| **Metadata date** | When the metadata itself was written or updated |

## Metadata standards

A **metadata standard** defines which elements to record, what they are called and how they are encoded, so
that catalogs and software can read metadata from many sources.

| Standard | Used for | Notes |
|---|---|---|
| **ISO 19115** (19115-1 content, with XML encoding in 19115-3) | Geospatial data worldwide | The main international standard; endorsed by the U.S. Federal Geographic Data Committee (FGDC) in 2016 |
| **FGDC CSDGM** | U.S. geospatial data, especially older federal data | The former U.S. standard; still widely found, now maintained as a legacy standard while agencies move to ISO |
| **ISO 19110** | Feature catalogs | Describes the feature types and attributes of a dataset (a formal data dictionary) |
| **Dublin Core** | General resources of any kind | Fifteen simple elements (title, creator, date, coverage, rights...); used by many library and repository systems |
| **DataCite Metadata Schema** | Datasets with DOIs | The metadata registered whenever a DOI is minted; required by repositories such as PURR and Zenodo |
| **DDI** (Data Documentation Initiative) | Social science surveys and statistical data | Used by ICPSR and many statistical agencies; describes variables, questions and samples in detail |
| **STAC** (SpatioTemporal Asset Catalog) | Satellite imagery and other geospatial "assets" | A modern JSON-based specification for searchable imagery catalogs |

You rarely write these formats by hand. Repositories ask for metadata through web forms and convert it to
standard formats, and GIS software has metadata editors.

### Controlled vocabularies

Free-text keywords vary ("food desert", "food deserts", "food access"), which makes searching unreliable.
**Controlled vocabularies** provide agreed terms: for example the ISO 19115 topic categories (such as
"society", "health" or "transportation"), the Library of Congress Subject Headings, or place names from
GeoNames. Use them where a repository or standard asks for them.

## Creating metadata in QGIS

QGIS has a built-in metadata editor based on ISO 19115:

1. Right-click a layer and choose **Properties**, then open the **Metadata** tab.
2. Fill in **Identification** (title, abstract, type and language), **Categories** and **Keywords**, **Access**
   (license, rights, constraints), **Extent** (spatial and temporal), **Contact**, **Links** and **History**
   (lineage).
3. Save it: the metadata can be stored next to the layer as a `.qmd` file or, for a GeoPackage layer, inside the
   GeoPackage, so it travels with the data.

Projects have metadata too, under **Project > Properties > Metadata**.

::::::::::::::::::::::::::::::::::::: callout

## Metadata for downloaded data

When you download data, **save its metadata** at the same time (most portals offer an XML or PDF file) and note
the date, the URL and the version. Sources change: the Census Bureau releases new TIGER/Line files every year,
and OpenStreetMap changes every minute.

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

## What is missing?

A dataset in a repository has this metadata:

> **Title:** Bus stops
> **Creator:** J. Smith
> **Format:** Shapefile
> **Description:** Bus stops with amenities.

List at least five important pieces of information that are missing.

:::::::::::::::: solution

- **Where**: which city or region (a spatial extent)
- **When**: the date of the data, not just of the upload
- **Coordinate reference system**
- **Lineage**: how the stops were mapped (field survey, transit agency data, imagery) and processed
- **Attribute information**: what the amenity fields mean and their allowed values
- **Quality**: positional accuracy and completeness
- **License** and any access constraints
- **Contact** details, affiliation, and a persistent identifier for citation
- A more specific **title**: "Bus stops and amenities, Lafayette, Indiana, 2026"

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

## Which standard?

Which metadata standard would you most likely meet in each situation?

1. Publishing a dataset with a DOI in Purdue's repository
2. Archiving a national household survey with hundreds of questions
3. Describing a statewide land cover layer for a state GIS clearinghouse
4. Building a searchable catalog of drone images

:::::::::::::::: solution

1. **DataCite** (the repository's form produces DataCite metadata for the DOI)
2. **DDI**, used by ICPSR and statistical agencies
3. **ISO 19115** (or the older FGDC CSDGM, which many state clearinghouses still use)
4. **STAC**

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Metadata is structured information that lets others find, understand, judge and cite a dataset
- Metadata can be descriptive, administrative, structural or technical; provenance records where data came from and what was done to it
- Geospatial metadata must include the spatial and temporal extent, coordinate reference system, resolution or accuracy, lineage and license
- ISO 19115 is the main geospatial standard; DataCite, Dublin Core, DDI and STAC serve other needs
- QGIS has an ISO-based metadata editor; save the metadata with the data

::::::::::::::::::::::::::::::::::::::::::::::::
