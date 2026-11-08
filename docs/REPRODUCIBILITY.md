# Reproducibility notes

## Current status

These are historical research scripts, preserved unchanged. Migration integrity is verified separately from scientific reproducibility. No clean-environment execution or result validation was performed.

## Data requirements and dependencies

| Component | Inputs or dependency |
| --- | --- |
| TCGA–GTEx preprocessing | UCSC Xena/Toil expression compendium, TCGA-LIHC clinical data, GTEx phenotype data |
| Gene annotation | `zz_gencode.v23.annotation.csv`, `zz_gene.protein.coding.csv`; absent from the source snapshot |
| WGCNA | `01_voomExpr.csv`, `00_ClinTraits.csv` generated during preprocessing |
| DGCA | `01_voomExpr.csv` |
| Survival | `01_voomExpr.csv`, `02_GSandMM.csv`, `01_DEGsTreat.csv`, `TCGA_survival_data` |
| GEO analysis | GSE54236, GPL6480 via GEOquery |

Packages explicitly loaded in the scripts include UCSCXenaTools, data.table, R.utils, dplyr, limma, edgeR, WGCNA, grex, biomaRt, topGO, ggplot2, GEOquery, Biobase, pheatmap, gplots, reshape2, plyr, umap, DGCA, org.Hs.eg.db, GOstats, HGNChelper, plotrix, RegParallel and survminer. Survival functions also require the appropriate survival namespace. This is an inventory, not a validated environment specification.

## Before attempting execution

1. Establish and record compatible R and Bioconductor versions and package versions.
2. Work from a separate analysis directory; inspect and replace the hard-coded Windows `setwd()` and download paths in a working copy.
3. Acquire the datasets and annotation tables; record versions, checksums and access dates.
4. Run preprocessing before dependent TCGA analyses. Review each section's inputs and outputs rather than assuming the combined script is an automated pipeline.
5. Verify GEO sample labels and sample order against the metadata before fitting models.
6. Resolve code and report differences before presenting regenerated results as a reproduction.

## Known issues requiring review

- Absolute local paths prevent direct execution on other systems.
- External resources and package versions are not pinned.
- The WGCNA script uses `dataTrait$pathologicN` in a gene-significance calculation although surrounding code prepares and labels `pathologicstage`; this requires methodological review.
- GEO group assignments are hard-coded by position; the report and code's sample counts and significance definitions must be reconciled.
- TCGA tumors and GTEx normal tissue come from different cohorts; cohort and technical effects require review.
- No automated workflow, regression tests or independently regenerated outputs were provided in the source snapshot.

Future fixes should be separate, reviewed commits so the original methods remain traceable.
