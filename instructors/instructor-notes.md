---
title: 'Instructor Notes'
---

## Overall approach

- This module is conceptual. Each episode takes about 30 minutes plus 15 to 20 minutes for challenges.
- It builds on the **Data Management** module; if learners have not taken it, spend a few minutes on file formats
  and on the difference between management and curation.
- Encourage learners to curate a dataset of their own as they go: write its README in the Documentation episode,
  choose its repository and license in the Sharing episode, and check it against the privacy checklist in the
  Ethics episode.

## Episode by episode

### Introduction to Data Curation

- Ask learners whether they have ever tried to reuse someone else's data, and what was missing. The answers
  usually cover every episode of the module.

### Metadata

- Open the metadata of a real dataset from a state or federal portal and compare it with the list of essential
  elements.
- Show the QGIS metadata editor (Layer Properties > Metadata) if QGIS is available.

### Documentation

- The README template can be handed out as a starting point for learners' own datasets.

### Preservation

- Demonstrate a checksum: calculate one, change a single character in a text file, and calculate it again.

### Sharing and Publishing Data

- If teaching at Purdue, invite someone from the Libraries' research data services to talk about PURR.
- Browse ICPSR together to show how a major social science archive describes data and controls access.

### Ethics and Sensitive Location Data

- The geomasking figure uses **simulated** points, not real people. Emphasize that point.
- Discussion of who could be harmed by a map works well in small groups.

## Common questions

| Question | Short answer |
|---|---|
| "Is FAIR the same as open?" | No: data can be FAIR with controlled access; the metadata stays findable |
| "Can I share data I downloaded?" | Check its license; you can always cite it precisely instead |
| "Is removing names enough to anonymize data?" | No, not when locations or small groups remain |
| "Which license should I use?" | CC0 or CC BY 4.0 for most data you created; keep the original license for derived data, such as ODbL for OpenStreetMap |
