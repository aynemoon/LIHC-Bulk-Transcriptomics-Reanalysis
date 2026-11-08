# LIHC Bulk Transcriptomics Reanalysis

Collaborative R-based reanalysis of hepatocellular carcinoma (LIHC) bulk gene-expression data from TCGA-LIHC, GTEx and GEO GSE54236.

This independent repository continues the research project originally hosted as [LIHC-pr/LiverCanNet](https://github.com/LIHC-pr/LiverCanNet). It preserves the original research files and attribution, with a new directory layout and documentation.

## Scientific scope

The historical analyses cover data acquisition and preparation, differential expression, weighted gene co-expression networks (WGCNA), Gene Ontology enrichment, differential gene correlation (DGCA), and survival associations.
See [CONTRIBUTORS.md](CONTRIBUTORS.md) for attribution and historical Git contributions.

## Repository guide

| Path | Contents |
| --- | --- |
| [scripts/preprocess_WGCNA_topGO.R](scripts/preprocess_WGCNA_topGO.R) | TCGA–GTEx retrieval, preprocessing, differential expression, WGCNA and GO enrichment |
| [scripts/GEO-DEG.R](scripts/GEO-DEG.R) | GSE54236 analysis and exploratory plots |
| [scripts/DGCA.R](scripts/DGCA.R) | Differential correlation and enrichment |
| [scripts/survival_liver.R](scripts/survival_liver.R) | Gene-wise survival analysis and plots |
| [reports/LIHC.pdf](reports/LIHC.pdf) | Original Persian project report, unchanged |
| [docs/REPRODUCIBILITY.md](docs/REPRODUCIBILITY.md) | Data requirements, packages and execution limitations |
| [docs/PROVENANCE.md](docs/PROVENANCE.md) | Source revision, migration mapping and historical attribution |
| [docs/migration-manifest.json](docs/migration-manifest.json) | Original and migrated paths, sizes, Git blob IDs and SHA-256 checksums |

## Data and results

The scripts use the UCSC Xena TCGA–GTEx resources and [GEO GSE54236](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE54236). Raw datasets and generated intermediate tables were not included in the original repository and are not included here.

The original report describes 68 differentially expressed genes and enrichment involving complement, cytokine-related and metabolic processes. These are historical findings. This migration does not independently reproduce or validate those findings.

## Running the analyses

Read [the reproducibility notes](docs/REPRODUCIBILITY.md) before running the scripts. Original code is preserved byte-for-byte, including its local working directories and dependencies. It is not yet a portable, automated pipeline; package versions and data snapshots are not pinned.

## Contributing

Contributions are welcome through issues and pull requests. See [CONTRIBUTING.md](CONTRIBUTING.md). Proposed methodological changes should be reviewed before replacing historical analyses or results.

## Attribution and reuse

Please acknowledge all three researchers and the [original project](https://github.com/LIHC-pr/LiverCanNet). Original historical Git contributors are retained in the provenance archive. Git commit authorship and research roles are distinct.

No software license was present in the source snapshot; this migration does not introduce one. The publication originally reanalyzed remains to be verified and cited explicitly. This repository documents research analyses, not a validated clinical tool.
