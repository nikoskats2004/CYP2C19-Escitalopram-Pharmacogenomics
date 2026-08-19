# CYP2C19 & Escitalopram – Pharmacogenomics Summary

**File:** `CYP2C19_Escitalopram_Pharmacogenomics_Summary.pbix`

## Overview

A compact Power BI report summarizing pharmacogenomic variants of the **CYP2C19** gene that affect the metabolism of **escitalopram** (an SSRI antidepressant). It maps specific genetic variants to predicted metabolizer phenotypes and the corresponding clinical/dosing recommendation — a typical pharmacogenomics reference table used to support personalized medicine decisions.

## Data model

Single table, `Πίνακας1` ("Table 1"), with the following columns:

| Column | Description |
|---|---|
| `RSID` | Reference SNP ID identifying the genetic variant (e.g. dbSNP identifier) |
| `Variant (Αλλήλιο)` | The allele associated with that SNP |
| `Phenotype (Φαινότυπος)` | Predicted CYP2C19 metabolizer phenotype (e.g. poor, intermediate, normal, rapid, ultrarapid metabolizer) |
| `Recommended Action (Προτεινόμενη Ενέργεια)` | Clinical/dosing recommendation associated with that phenotype |

> Column names are bilingual (English label with the original Greek term in parentheses), reflecting the report's coursework origin.

## Report pages

- **Page 1** (2 visuals)
  - A detail table listing all variants, phenotypes, and recommendations
  - A clustered column chart

## Use case

Intended as an educational/reference summary for a pharmacology or pharmacogenomics course, illustrating how genotype data (CYP2C19 variants) can inform escitalopram dosing decisions.

## Requirements

- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free) to open and view the report.

## How to open

Download `CYP2C19_Escitalopram_Pharmacogenomics_Summary.pbix` and open it directly in Power BI Desktop.

## Disclaimer

This report is for educational purposes only and is **not** a substitute for professional clinical or pharmacogenomic guidance.
