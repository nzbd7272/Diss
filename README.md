# Dissertation 
# Chronic Pain Epigenomics Pipeline

An end-to-end computational framework for base-level CpG DNA methylation analysis in chronic pain models. This repository contains the code to reproduce feature-specific spatial asymmetry mapping, locus prioritization, network topology analysis, and KEGG pathway over-representation analyses.

## Directory Structure
- `01_genomic_intersection.sh`: Shell script using `bedtools` for TSS promoter/gene-body extraction and spatial candidate filtering.
- `02_epigenomic_analysis.R`: R script for statistical distributions, global CpG responsiveness calculation, target ranking, and `gprofiler2` pathway mapping.
- `ranked_pain_candidate_genes.csv`: Output candidate matrix ranked by locus hypermethylation count.
- `kegg_pathway_enrichment.csv`: Output over-representation mapping derived from g:Profiler.

## Prerequisites & Dependencies
- **UNIX Dependencies:** `bash`, `awk`, `sed`, `bedtools` (v2.30.0+)
- **R Packages:** `data.table`, `ggplot2`, `gprofiler2`, `viridis`
- **External Network Mapping:** Protein-protein interaction (PPI) maps generated via [STRING-db v12.0](https://string-db.org/) using a minimum interaction score threshold of $\ge 0.700$.

## Execution
1. Make the shell script executable and run feature intersection:
   ```bash
   chmod +x 01_genomic_intersection.sh
   ./01_genomic_intersection.sh
