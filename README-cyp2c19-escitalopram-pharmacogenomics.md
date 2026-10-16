# Applied Pharmacogenomics: CYP2C19 Genetic Variants & Escitalopram Dosing Guidelines

[![Power BI](https://img.shields.io/badge/Power_BI-Desktop-F2C811?logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![PharmGKB](https://img.shields.io/badge/PharmGKB-Level_1A-007ACC)](https://www.pharmgkb.org/)
[![CPIC](https://img.shields.io/badge/CPIC-Guideline-brightgreen)](https://cpicpgx.org/)

## 🧬 Project Overview & Objectives
This repository contains an advanced, interactive clinical pharmacogenomics decision-support dashboard developed in **Microsoft Power BI**. The project investigates the critical gene-drug interaction between the **CYP2C19** gene (*Cytochrome P450 family 2 subfamily C member 19*) and the selective serotonin reuptake inhibitor (SSRI) **Escitalopram**, commonly prescribed for major depressive and anxiety disorders.

The primary objective is to bridge biomedical informatics and precision medicine by translating raw genomic polymorphisms (dbSNP rsIDs, star-alleles, and diplotypes) into clinically actionable metabolizer phenotypes, functional activity scores, European population-specific frequencies, and **CPIC-guided dosing recommendations**.

---

## 🔍 Data Sources & Methodology
The workflow and clinical datasets were systematically curated from internationally recognized pharmacogenomic databases and consortium guidelines:
1. **PharmGKB (Pharmacogenomics Knowledge Base):** Utilized for gene-drug associations and clinical annotations. The interaction between CYP2C19 and escitalopram/citalopram is categorized under **Level 1A Evidence**, denoting the highest level of curated clinical validation supported by guidelines and FDA-approved drug labels.
2. **CPIC (Clinical Pharmacogenetics Implementation Consortium):** Provided the authoritative dosing guidelines and phenotypic translation tables for adjusting escitalopram regimens based on patient diplotypes.
3. **PharmVar (Pharmacogene Variation Consortium):** Referenced for standardized star-allele nomenclature and reference sequence mapping (hg38).

---

## 📌 Biological & Clinical Background
- **Gene Symbol:** `CYP2C19` (Location: Chromosome 10q23.33)
- **Role:** Encodes a hepatic cytochrome P450 enzyme responsible for metabolizing roughly 10-15% of clinically administered drugs, including antidepressants, antiplatelets (Clopidogrel), and antifungals (Voriconazole).
- **Clinical Rationale:**
  - **Poor Metabolizers (PM) & Intermediate Metabolizers (IM):** Exhibit reduced or complete loss of enzymatic function (e.g., `*2`, `*3` alleles). This leads to impaired drug clearance, elevated systemic plasma exposure (AUC), and a significantly heightened risk of adverse drug reactions (ADRs) such as QT prolongation or severe toxicity.
  - **Ultrarapid Metabolizers (UM) & Rapid Metabolizers (RM):** Exhibit accelerated metabolic capacity driven by increased-function alleles (e.g., `*17`). This results in subtherapeutic plasma concentrations, predisposing the patient to therapeutic failure.

---

## 📊 Data Model & Clinical Decision Matrix
The relational dataset integrated into Power BI maps structural star-alleles to predicted clinical phenotypes, European population distributions (`Population_Frequency_EUR`), and exact therapeutic interventions:

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

## 📈 Power BI Dashboard Architecture & Key Results
The final reporting layout is structured into three distinct analytical zones to maximize clinical usability:
1. **Executive KPI Cards:** Highlights total diplotype variations evaluated (**8**) and calculates the cumulative high-risk patient population percentage (**~7.6%** representing poor and ultrarapid profiles requiring immediate clinical intervention).
2. **Interactive Filtering & Epidemiological Chart:** Incorporates a dynamic phenotype selector (`Slicer`) paired with a horizontal bar chart displaying European population frequencies across risk categories.
3. **Clinical Action Matrix (Detailed Table):** Provides a comprehensive reference mapping genetic variants (rsIDs) to functional activity scores, initial dose percentages, and exact physician actions.

---

## 💻 Requirements & Usage
1. **Prerequisites:** [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free version).
2. **Getting Started:** Download the `.pbix` report file from this repository and open it directly in Power BI Desktop to explore the interactive visual elements.

---
*Disclaimer: This repository was developed strictly for academic, educational, and portfolio demonstration purposes within the scope of biomedical informatics and pharmacogenomics coursework. It does not constitute formal clinical diagnostic advice.*
