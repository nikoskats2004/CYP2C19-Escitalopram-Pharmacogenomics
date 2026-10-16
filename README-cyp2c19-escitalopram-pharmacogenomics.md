# Applied Pharmacogenomics: CYP2C19 Variants & Escitalopram Dosing Guidelines

[![Power BI](https://img.shields.io/badge/Power_BI-Desktop-F2C811?logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![PharmGKB](https://img.shields.io/badge/PharmGKB-Level_1A-007ACC)](https://www.pharmgkb.org/)
[![CPIC](https://img.shields.io/badge/CPIC-Guideline-brightgreen)](https://cpicpgx.org/)

## 🧬 Overview
This repository hosts an advanced clinical pharmacogenomics decision-support dashboard built in **Microsoft Power BI**, examining the gene-drug interaction between the **CYP2C19** gene and the selective serotonin reuptake inhibitor (SSRI) **Escitalopram**. 

The case study bridges biomedical informatics and precision medicine by translating raw genomic polymorphisms (dbSNP rsIDs, star-alleles, and diplotypes) into clinically actionable metabolizer phenotypes, enzymatic activity scores, European population-specific frequencies, and **CPIC-guided dosing recommendations**.

---

## 📌 Biological & Clinical Background
- **Gene:** `CYP2C19` (*Cytochrome P450 family 2 subfamily C member 19*)
- **Chromosomal Location:** 10q23.33
- **PharmGKB Evidence Level:** **Level 1A** (highest level of curated clinical evidence linking star-alleles to drug toxicity and efficacy).
- **Clinical Rationale:**
  - **Poor & Intermediate Metabolizers (PM/IM):** Characterized by reduced or absent enzymatic activity, leading to decreased drug clearance, elevated systemic exposure (AUC), and heightened risk of adverse drug reactions (ADRs) or toxicity.
  - **Ultrarapid & Rapid Metabolizers (UM/RM):** Exhibit accelerated metabolic clearance, resulting in subtherapeutic plasma levels and therapeutic treatment failure.

---

## 📊 Data Model & Clinical Decision Matrix
The underlying relational dataset is curated in accordance with **CPIC (Clinical Pharmacogenetics Implementation Consortium)** guidelines and **PharmGKB / PharmVar** nomenclature standards:

| Diplotype | rsIDs (dbSNP) | Metabolizer Phenotype | Activity Score | Population Freq. (EUR) | CPIC Recommended Action / Dosing Adjustment |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `*1 / *1` | Reference | Normal Metabolizer | 1.0 | 40.0% | Initiate therapy with standard recommended starting dose. |
| `*1 / *17` | `rs12248560`, Reference | Rapid Metabolizer | 1.5 | 26.0% | Initiate standard starting dose; monitor and titrate based on clinical efficacy. |
| `*1 / *2` | `rs4244285`, Reference | Intermediate Metabolizer | 0.5 | 22.0% | Initiate standard starting dose; closely monitor for adverse events. |
| `*1 / *3` | `rs4986893`, Reference | Intermediate Metabolizer | 0.5 | 1.0% | Initiate standard starting dose; closely monitor for adverse events. |
| `*17 / *17` | `rs12248560` | Ultrarapid Metabolizer | 2.5 | 5.0% | Avoid Escitalopram; select an alternative antidepressant not predominantly metabolized by CYP2C19. |
| `*2 / *2` | `rs4244285` | Poor Metabolizer | 0.0 | 2.0% | Reduce starting dose by 50% or consider an alternative antidepressant. |
| `*2 / *3` | `rs4244285`, `rs4986893` | Poor Metabolizer | 0.0 | 0.5% | Reduce starting dose by 50% or consider an alternative antidepressant. |
| `*3 / *3` | `rs4986893` | Poor Metabolizer | 0.0 | 0.1% | Reduce starting dose by 50% or consider an alternative antidepressant. |

---

## 📈 Dashboard Architecture & Features
- **KPI Summary Cards:** Total diplotypes evaluated (8) and high-risk patient population ratio (~7.6% requiring critical dose alterations or drug switches).
- **Interactive Phenotype Slicer:** Dynamic filtering across metabolic categories.
- **Epidemiological Bar Chart:** Visualizing European allele frequency distributions mapped across phenotypic risk tiers.
- **Clinical Action Matrix (Table):** Comprehensive reference detailing diplotypes, rsIDs, functional activity scores, and precise dosing guidelines.

---

## 💻 Requirements & Usage
1. **Prerequisites:** [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free version).
2. **Execution:** Download the `.pbix` report file from this repository and open it directly in Power BI Desktop.

---
*Disclaimer: Developed strictly for academic, educational, and portfolio demonstration purposes in biomedical informatics and pharmacogenomics. It does not constitute clinical diagnostic advice.*
