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

## 1. CMap Drug safety 

### 1.1. Introduction

  - Predict drug-induced liver injury (DILI)
  - 276 drug compounds
    - 190 for training: 130 positive + 60 negative
    - 86 for validation: unlabeled
  - Cell-based screening of Broad Connectivity Map (CMap) data: 
  - MCF7 and PC3 cancer cell lines
  - 1095 expression arrays
  - Vehicle control vs. compound-treated

***Analysis suggestions:***

  - Prediction of DILI
  - Identification/interpretation of difference between cell lines
  - Option to participate an FDA meta-analysis paper

### 1.2. Data

The .CEL files of Affymetrix microarrays of 2 different cell lines were processed separately as described [here](https://github.com/zhezhangsh/MyMethods/blob/master/microarray_affymatrix_typical.md). Most compounds used HT_HG-U133A array platform, but small number of training compounds used HG-U133A. Sample analysis showed that data from different platforms are not directly comparable. As a result, 10 compounds were removed from the training data, and there will be **180** total training compounds: (**120** positive + **60** negative), and **86** validation compounds.
  
***Download:***

  - Processed microarray data matrix of 582 samples from MCF7 cells: [download](CMap/R/expr_MCF7.rds).
  - Processed microarray data matrix of 475 samples from PC3 cells: [download](CMap/R/expr_PC3.rds).
  - Annotation of 12,080 NCBI Entrez genes: [view online](CMap/R/anno_gene.csv) or [download](CMap/R/anno_gene.rds).
  - Annotation of 266 compounds: [view online](CMap/R/anno_compound.csv) or [download](CMap/R/anno_compound.rds).
  - Annotation of 582 MCF7 .CEL files: [view online](CMap/R/anno_cel_MCF7.csv) or [download](CMap/R/anno_cel_MCF7.rds).
  - Annotation of 475 PC3 .CEL files: [view online](CMap/R/anno_cel_PC3.csv) or [download](CMap/R/anno_cel_PC3.rds).
  - Annotation of 103 buffer vehicles (61 MCF7 + 42 PC3): [view online](CMap/R/vehicle_count.csv) or [download](CMap/R/vehicle2cel.rds).


## 2. Cancer Data Integration 

### 2.1. Introduction

  - Breast Cancer (Re-analyze METABRIC data):
    - 5 subtypes
    - ~ 2,000 patients
    - Matched expression array, copy number, and clinical information (survival, marker, therapy, …)
    
  - Neuroblastoma (Re-analyze SEQC data):
    - 498 patients
    - Expression array, RNA-seq, and clinical metadata
    - Matched aCGH copy number data of 145 patients

***Analysis suggestions:***

  - Technical
    - Horizontal integration: expression + CNV + clinical
    - Vertical integration: RNA-seq + array, multiple cohorts, …
    - Difference of algorithm performance between two different diseases
    
  - Biological
    - Better prediction of survival via integration analysis
    - Understand progression or therapy response better
    - Improve cancer subgrouping

### 2.2. Data

#### A. Neuroblastoma

Data were downloaded from CAMDA and GEO websites and formatted as R objects.

***Download:***

  - Sample characteristics: [view online](Cancer/NB/R/clinical.csv) or [download](Cancer/NB/R/clinical.rds).
  - Sample metadata: [view online](Cancer/NB/R/sample_metadata.csv) or [download](Cancer/NB/R/sample_metadata.rds).
  - Gene expression, GSE49711 (RNA-seq): [download](Cancer/NB/R/expression/GSE49711/expr_gene.rds).
  - Gene expression, GSE62564 (RNA-seq): [download](Cancer/NB/R/expression/GSE62564/expr.rds).
  - Gene expression, GSE49710 (microarray): [download](Cancer/NB/R/expression/GSE49710/expr.rds).
  - CNV-aCGH, series summary: [view online](Cancer/NB/R/aCGH/cnv_meta.csv) or [download](Cancer/NB/R/aCGH/cnv_meta.rds).  
  - CNV-aCGH, data matrix (all series): [download](Cancer/NB/R/aCGH/cnv_all.rds).
  - CNV-aCGH, annotation (all series): [download](Cancer/NB/R/aCGH/anno_all.rds).
  - CNV-expression mapping: [view online](Cancer/NB/R/aCGH/SEQC2aCGH.csv) or [download](Cancer/NB/R/aCGH/SEQC2aCGH.rds). 


### 2.3. Results

  - Sample analysis: subgroups, PCA, CNV calls, etc. [download](Cancer/NB/Result/sample_analysis.zip). 

