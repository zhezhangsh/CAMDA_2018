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

### Introduction

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

### Data

The .CEL files of Affymetrix microarrays of 2 different cell lines were processed separately as described [here](https://github.com/zhezhangsh/MyMethods/blob/master/microarray_affymatrix_typical.md). Most compounds used HT_HG-U133A array platform, but small number of training compounds used HG-U133A. Sample analysis showed that data from different platforms are not directly comparable. As a result, 10 compounds were removed from the training data, and there will be **180** total training compounds: (**120** positive + **60** negative), and **86** validation compounds.
  
***Download:***

  - Processed microarray data matrix of 582 samples from MCF7 cells: [download](CMap/R/expr_MCF7.rds).
  - Processed microarray data matrix of 475 samples from PC3 cells: [download](CMap/R/expr_PC3.rds).
  - Annotation of 12,080 NCBI Entrez genes: [view online]() or [download](CMap/R/anno_gene.rds).
  - Annotation of 266 compounds: [view online](CMap/R/anno_compound.csv) or [download](CMap/R/anno_compound.rds).
  - Annotation of 582 MCF7 .CEL files: [view online](CMap/R/anno_cel_MCF7.csv) or [download](CMap/R/anno_cel_MCF7.rds).
  - Annotation of 475 PC3 .CEL files: [view online](CMap/R/anno_cel_PC3.csv) or [download](CMap/R/anno_cel_PC3.rds).
  - Annotation of 103 buffer vehicles (61 MCF7 + 42 PC3): [view online](CMap/R/vehicle_count.csv) or [download](CMap/R/vehicle2cel.rds).
  
### Results

https://github.com/zhezhangsh/CAMDA_2018/raw/master/CMap/R/vehicle2cel.rds
https://github.com/zhezhangsh/CAMDA_2018/blob/master/CMap/R/vehicle2cel.rds

## Cancer Data Integration 

### Introduction

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

### Data

#### Neuroblastoma

Data were downloaded from CAMDA and GEO websites and formatted as R objects.

***Download:***

  - Sample characteristics: [view online]() or [download]().
  - Sample metadata: [view online]() or [download]().
  - Gene expression, GSE49711 (RNA-seq): [download]().
  - Gene expression, GSE62564 (RNA-seq): [download]().
  - Gene expression, GSE49710 (microarray): [download]().
  - 


### Results

#### Sample analysis

