---
title: "Additional Topics"
teaching: 35
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- What happens after data is created?
- How do institutions manage research data repositories?
- What is PURR and how does it support data curation?
- How is large-scale data transferred and preserved globally?
- What challenges arise when curating very large datasets?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explore advanced topics in data curation
- Understand institutional repositories such as PURR
- Learn how large datasets are stored and transferred
- Recognize challenges in global-scale research data management
- Connect local data practices to international infrastructure

::::::::::::::::::::::::::::::::::::::::::::::::

## Beyond Basic Data Curation

Data curation does not stop at organizing files on your computer.

As projects grow larger, data must often be:

- Shared across institutions
- Archived in repositories
- Transferred across countries
- Managed in cloud environments

Modern data science depends on scalable curation systems.

---

## 1. Data Generation: Where Data Begins

Before curation begins, data must first be generated.

### Common sources of data:

- Scientific instruments (sensors, satellites, microscopes)
- Surveys and questionnaires
- Field observations
- Simulations and computational models
- Web APIs and streaming platforms

### Example:
A weather station may generate:

- Temperature every minute
- Humidity every hour
- Rainfall every day

::::::::::::::::::::::::::::::::::::: callout

### Important
The way data is generated affects how it should be curated later.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## 2. Institutional Repositories: Example of PURR

### What is PURR?

**PURR (Purdue University Research Repository)** is Purdue University's platform for:

- Publishing datasets
- Preserving research outputs
- Sharing reproducible workflows

You can find the website [here](https://purr.purdue.edu/).

PURR helps researchers:

- Store curated datasets securely
- Assign DOIs (Digital Object Identifiers)
- Share data publicly or privately
- Meet grant and publication requirements

### Why repositories matter:
Repositories protect data from loss and make it reusable beyond the original project.

---

## 3. Data Publishing and DOI Assignment

When curated data is deposited into repositories like PURR:

- It receives permanent identifiers
- Others can cite it in publications
- It becomes discoverable worldwide

Example citation:
> Smith et al. (2025). Soil Moisture Data for Indiana Watersheds.

This turns datasets into scholarly products.

---

## 4. Large-Scale Cloud Data Transfer

Some datasets are too large for email, USB drives, or local sharing.

Examples:

- Satellite imagery archives
- Climate model simulations
- Genomics databases
- High-resolution remote sensing data

These often require:

- Cloud platforms
- Distributed storage systems
- High-speed transfer protocols

---

## 5. Global Data Transfer Systems

Large-scale research often uses tools such as:

### Globus

Find it [here](https://www.globus.org/). 

Globus is widely used for:

- Secure high-volume data transfer
- Moving terabytes between institutions
- Automating research workflows

Example:
A researcher in Indiana transfers 5 TB of satellite data to collaborators in Europe.

---

## 6. Cloud Storage and Distributed Infrastructure

Modern curated datasets may live in:

- Amazon S3
- Google Cloud Storage
- Microsoft Azure
- Institutional HPC clusters

These systems support:

- Redundancy
- Backup replication
- Global accessibility

---

## 7. Challenges of Big Data Curation

Large-scale datasets introduce new problems:

### Storage Costs
Huge datasets require expensive infrastructure.

### Transfer Speed
Slow internet limits movement of terabytes.

### Metadata Complexity
Larger systems require richer documentation.

### Preservation Risk
Formats may become obsolete over decades.

::::::::::::::::::::::::::::::::::::: challenge

Why might a 100 TB climate archive require different curation strategies than a 10 MB CSV file?

::::::::::::::::::::::::::::::::::::::::::::::::

---

## 8. Data Lifecycle at Global Scale

For large collaborative projects:

Generate → Process → Curate → Store → Transfer → Archive → Reuse

Unlike small projects, this cycle may involve:

- Multiple countries
- Multiple institutions
- Automated pipelines

---

## 9. Reproducibility in Shared Infrastructure

When sharing globally:

- File formats must be standardized
- Metadata must be machine-readable
- Access permissions must be managed carefully

Example standards:

- NetCDF for climate data
- HDF5 for scientific arrays
- JSON metadata schemas

---

## 10. Future of Data Curation

Emerging trends include:

- AI-assisted metadata generation
- Automated cloud archiving
- FAIR-compliant repositories
- Real-time streaming curation pipelines

---

## Final Takeaways

Data curation today extends far beyond local folders:

- Institutions use repositories like PURR
- Large datasets require cloud infrastructure
- Global collaboration depends on scalable transfer systems

::::::::::::::::::::::::::::::::::::: discussion

- What kinds of projects require cloud-scale curation?
- How might your own research data eventually outgrow local storage?

::::::::::::::::::::::::::::::::::::::::::::::::