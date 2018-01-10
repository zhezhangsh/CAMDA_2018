---
title: "CAMDA challenges, 2018"
---

# CAMDA_2018



This repo includes information, code, and results related to CAMDA 2018 challenges. 

Key dates:

  - April 5th: intention to submit
  - April 15th: finalize DILI prediction for FDR meta-analysis paper
  - May 13th: abstract proposal due
  - July 7th – 8th: CAMDA 2018 conference
  - July 6th – 10th: ISMB 2018 conference
  - September 24th: full paper submission
    - CAMDA conference proceedings at Biology Direct
    - ISBM conference proceeding at Bioinformatics

Use the following method to download raw and processed data:

## CMap Drug safety 

  - Predict drug-induced liver injury (DILI)
  - 276 drug compounds
    - 190 for training: 130 positive + 60 negative
    - 86 for validation: unlabeled
  - Cell-based screening of Broad Connectivity Map (CMap) data: 
  - MCF7 and PC3 cancer cell lines
  - 1095 expression arrays
  - Vehicle control vs. compound-treated

**Analysis suggestions:**

  - Prediction of DILI
  - Identification/interpretation of difference between cell lines
  - Option to participate an FDA meta-analysis paper

## Cancer Data Integration 

  - Breast Cancer (Re-analyze METABRIC data):
    - 5 subtypes
    - ~ 2,000 patients
    - Matched expression array, copy number, and clinical information (survival, marker, therapy, …)
    
  - Neuroblastoma (Re-analyze SEQC data):
    - 498 patients
    - Expression array, RNA-seq, and clinical metadata
    - Matched aCGH copy number data of 145 patients

**Analysis suggestions:**

  - Technical
    - Horizontal integration: expression + CNV + clinical
    - Vertical integration: RNA-seq + array, multiple cohorts, …
    - Difference of algorithm performance between two different diseases
    
  - Biological
    - Better prediction of survival via integration analysis
    - Understand progression or therapy response better
    - Improve cancer subgrouping

