---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Metadata & Data Documentation

**Metadata** = data about data. Use it to describe research data and find data later.

## Core Concepts

| Concept | Description |
|---------|-------------|
| **Metadata** | Information that describes research data |
| **Information Entropy** | Measure of uncertainty/information content |
| **Data Documentation** | The practice of recording metadata |

## Categories of Metadata

| Category | Description |
|----------|-------------|
| **Administrative** | Management info (creator, date, access rights) |
| **Structural** | How data is organized (relationships between parts) |
| **Descriptive** | What the data is about (titles, keywords, abstracts) |

## Dublin Core

A set of **general metadata fields** and **metadata standards** widely used for describing digital resources.

Common Dublin Core elements:
- Title, Creator, Subject, Description, Date, Type, Format, Identifier

## Saving Metadata: 4 Approaches

| Approach | Description |
|----------|-------------|
| **Within the data file** | Embedded headers (e.g., NetCDF, TIFF) |
| **At the data** | Attached at variable/column level |
| **Next to the data** | Separate sidecar file (e.g., `.xml`, `.json`) |
| **Metadata database** | Centralized catalog (e.g., CKAN, data catalogs) |

## Document Your Data: README.txt

> [!tip] Best Practice
> Always include a `README.txt` file alongside your data.

A good README includes:
- What the data is
- How it was collected
- File format descriptions
- Variable definitions
- Contact information

## One-Line Summary

> Metadata = data about data — use Dublin Core standards and README files to document and discover research data.

## Related

- [[FAIR Data Principles]]
- [[Data Management Plan]]
- [[README]]
- [[Dublin Core]]
- [[Data Citation]]
- [[Ontology]]
- [[Data Dictionary]]