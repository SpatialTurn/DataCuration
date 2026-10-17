---
title: "Sharing and Publishing Data"
teaching: 30
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- Where should I share my research data?
- What is a DOI, and why does it matter?
- Which license should I choose for my data?
- How do the FAIR and CARE principles guide sharing?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Compare institutional, disciplinary and general-purpose repositories
- Explain persistent identifiers, including DOIs and ORCIDs
- Choose an appropriate license, and respect the licenses of the data you reuse
- Distinguish open, embargoed and controlled access
- Apply the FAIR and CARE principles when sharing data

::::::::::::::::::::::::::::::::::::::::::::::::

## Why share data?

Sharing data lets others **verify** your findings, **build on** your work, and **cite** it, which gives you credit
for the effort of creating it. It is increasingly **required**: by funders (in data management and sharing
plans), by federal public access policies, and by many journals. And it avoids the waste of others collecting
the same data again.

Sharing well, however, takes more than emailing a file on request ("data available upon request" often turns out
to mean "no longer available"). It means putting the data, with its documentation, somewhere designed to keep it
findable and accessible.

## Choosing a repository

| Kind | Examples | Good for |
|---|---|---|
| **Institutional** | Purdue University Research Repository (**PURR**) | Any data from Purdue researchers; local support from the Libraries |
| **Disciplinary** (domain) | **ICPSR** (social and behavioral science), **OpenTopography** (elevation and lidar), **Qualitative Data Repository** (qualitative social science) | Reaching the right community; expert curation; standards for the field |
| **General-purpose** | **Zenodo**, **Harvard Dataverse**, **Open Science Framework (OSF)**, **figshare**, **Dryad** | Data with no obvious disciplinary home |
| **Government portals** | Data.gov, state GIS portals | Data produced by or for government agencies |
| **Code platforms** | GitHub, linked to Zenodo for a DOI | Code and small text-based data, plus documentation |

Ask:

- Does my **funder** or **journal** require or recommend a particular repository?
- Is there a **disciplinary repository** my readers already use?
- Does it assign **DOIs**, require **metadata**, and have a **preservation** commitment?
- Can it handle my data's **size** and any need for **restricted access**?
- Does it cost anything, and how long will it keep the data?

### PURR at Purdue

**PURR** (<https://purr.purdue.edu/>) is Purdue's research repository. Researchers create a **project space**
to collaborate and store files (each project starts with 100 GB, and grant-funded projects can be increased to
1 TB at no cost), and can then **publish** a dataset, which receives a **DataCite DOI** and is archived for the
long term. Collaborators from other institutions can be invited to a project. The Purdue Libraries can help
prepare data for publication.

### ICPSR for social science

The **Inter-university Consortium for Political and Social Research** (ICPSR, at the University of Michigan)
archives social and behavioral science data, including many major surveys. It curates deposits (checking files,
writing codebooks, removing identifying information) and offers **restricted-use** access for sensitive data,
including data with detailed geography.

## Persistent identifiers

A web address can break; a **persistent identifier** (PID) is designed to keep working.

- A **DOI** (Digital Object Identifier), such as `https://doi.org/10.4231/XXXX`, identifies a dataset (or
  article) and always resolves to its current landing page. Repositories register dataset DOIs, usually through
  **DataCite**, along with standard metadata.
- An **ORCID** iD (such as `0000-0002-1825-0097`) identifies **you** as a researcher, so your datasets and papers
  are linked to you even if your name or institution changes.

The 2022 federal public access memo specifically asks agencies to use persistent identifiers for research outputs
and researchers.

## Licenses

A **license** tells others what they may do with your data. Without one, people may be unsure whether they can
reuse it at all. Common choices for data:

| License | What it allows | Notes |
|---|---|---|
| **CC0** (public domain dedication) | Any use, no conditions | Recommended by many repositories for data; citation is still expected by scholarly norms |
| **CC BY 4.0** | Any use, with **attribution** | A common default; requires credit to the creator |
| **ODbL** (Open Database License) | Use and share, with attribution, and **share-alike** for adapted databases | The license of OpenStreetMap; data derived from OSM must keep it |
| **CC BY-NC** (non-commercial) | Use with attribution, but not commercially | Restrictive and often unclear; generally discouraged for research data |

Some things to know:

- **Respect the licenses of what you reuse.** If your dataset is built from OpenStreetMap, it must remain under
  the ODbL with attribution. U.S. federal data (such as Census Bureau data) is generally in the public domain.
- In the United States, **facts** themselves are not protected by copyright, though the selection and
  arrangement of a database can be; licenses make your intentions clear either way.
- You can only license what you have the right to share. Data from interviews, purchased data or data under a
  data use agreement may not be yours to license openly.

## Levels of access

Not all data can be fully open. Repositories support several levels:

| Level | What it means | When to use it |
|---|---|---|
| **Open** | Anyone can download | Most non-sensitive data |
| **Embargoed** | Metadata public now; data released after a set date | Waiting for a paper to be published or a patent to be filed |
| **Controlled (restricted) access** | Approved users only, often under a data use agreement or in a secure environment | Sensitive data, such as confidential survey responses or detailed locations of people |
| **Metadata only** | The record describes the data and how to request it | Data that cannot be deposited, such as licensed commercial data |

Even when data must be restricted, publishing its **metadata** makes it findable, and is part of being FAIR.

## FAIR and CARE

The **FAIR** principles (findable, accessible, interoperable, reusable), introduced in the first episode, are
about making data work well for **machines and researchers**.

The **CARE** principles for Indigenous data governance, published by the Global Indigenous Data Alliance in
2019, add a focus on **people and purpose**, especially for data about Indigenous peoples, lands and resources:

| Principle | Meaning |
|---|---|
| **Collective benefit** | Data ecosystems should allow Indigenous peoples to benefit from the data |
| **Authority to control** | Indigenous peoples' rights and interests in data about them must be recognized, including their authority to govern it |
| **Responsibility** | Those working with the data must show how it supports self-determination and collective benefit |
| **Ethics** | The rights and wellbeing of Indigenous peoples should be the primary concern throughout the data lifecycle |

The two are meant to be used **together**: "Be FAIR and CARE." Geospatial data about sacred sites, land use or
resources can have serious consequences for communities, so it should be shared only in ways the communities
concerned agree to.

::::::::::::::::::::::::::::::::::::: challenge

## Pick a repository

Where would you deposit each dataset, and why?

1. Anonymized responses from a national survey about housing, with county of residence
2. Grocery store points you verified in the field in Lafayette, Indiana, for a Purdue thesis
3. A 2 TB lidar point cloud of a river corridor
4. The Python code and small GeoJSON files behind a published paper

:::::::::::::::: solution

1. **ICPSR**: the social science community uses it, and it can offer restricted access if county plus other
   answers could identify people.
2. **PURR**: Purdue's repository, with a DOI and local support (Zenodo or Harvard Dataverse would also work).
3. **OpenTopography** (a disciplinary repository for elevation data), or institutional research storage for the
   raw data plus a repository record with a DOI.
4. **GitHub** for development, archived to **Zenodo** (or PURR) for a DOI that matches the published version.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

## Pick a license

Which license would suit each case?

1. Tract-level statistics you calculated from public Census Bureau data
2. A layer you created by editing and adding to OpenStreetMap data
3. Interview transcripts collected under consent forms that promised confidentiality

:::::::::::::::: solution

1. **CC0** or **CC BY 4.0**: the inputs are public domain, so you are free to choose an open license.
2. **ODbL**: it is a derivative of OpenStreetMap, so it must be shared under the same license with attribution.
3. **No open license**: the consent forms rule out public sharing. Share only de-identified data (if the consent
   allows), under controlled access with a data use agreement, or share metadata only.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Share data through a repository rather than on request; choose disciplinary, institutional or general-purpose repositories to suit the data
- PURR is Purdue's repository; ICPSR is the main archive for social science data
- Persistent identifiers (DOIs for data, ORCID iDs for people) keep data findable and creators credited
- Choose a clear license (often CC0 or CC BY), and keep the licenses of data you reuse, such as ODbL for OpenStreetMap
- Data can be open, embargoed, controlled or metadata-only; apply both FAIR and CARE principles

::::::::::::::::::::::::::::::::::::::::::::::::
