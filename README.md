# TCR-germline-repertoire-analysis 

# TCR Repertoire Analysis for Germline Bias Study
This repository contains custom Python scripts used for TCR repertoire analysis in the study:
**MHC restriction is structurally encoded by the T cell receptor germline**
（Code contributors: Wanlu Liu and Nan Wang）

## Overview
The analysis focuses on identifying germline-associated patterns in human TCR repertoires, including:
- TRAV and TRBV gene usage enrichment
- Vα–Vβ pairing enrichment
- Association of TCR features with HLA-A*02 status

These analyses correspond to **Figure 5 and related supplementary figures14 in the manuscript.
---

## Data Description

The analysis is based on a combined table containing:
- Paired TCR annotations (TRAV, TRBV, CDR3α, CDR3β)
- Cell subtype annotations
- Individual identifiers
- HLA class I typing (A_1, A_2)

HLA-A*02 status is defined per individual based on the presence of an A*02 allele.

---

## Analysis Workflow

### 1. Data preprocessing
- Assign HLA-A*02 status to each clonotype
- Filter T cells based on cell subtype annotations
- Define analysis subsets (e.g., CD8, naïve CD8)

### 2. V gene enrichment analysis
- Count TRAV and TRBV usage across defined groups
- Perform Fisher’s exact test using 2×2 contingency tables
- Compute odds ratios and adjust p-values (Benjamini–Hochberg)

### 3. Vα–Vβ pairing analysis
- Construct TRAV–TRBV pairs for each clonotype
- Compute pair frequencies across HLA-defined groups
- Perform enrichment analysis using Fisher’s exact test
- Apply abundance filtering for visualization

### 4. Visualization
- Odds ratio plots for V gene usage
- Volcano plots and lollipop plots for Vα–Vβ pairing

---

## Code Structure

The main analysis is implemented in Jupyter notebooks:

- `code.ipynb`  
  Core pipeline for TCR repertoire analysis and figure generation.
Only code relevant to the analyses reported in the manuscript is included.

---

## Dependencies
The analysis was performed using Python with the following packages:
- pandas
- numpy
- scipy
- statsmodels
- matplotlib
---

## Code Availability
The scripts provided here correspond to the analyses described in the manuscript.  
Additional documentation and cleaned workflows will be provided upon publication.

---

## Notes

This repository contains only the components directly used in the manuscript.  
Exploratory analyses and unrelated scripts have been intentionally excluded.

---

## Contact

For questions regarding the analysis, please contact:
