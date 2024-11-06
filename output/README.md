# Bioinformatics Pipeline README
## Summary
This pipeline is designed to perform spatial enrichment analysis on normalized transcriptomics data using the STenrich algorithm. It provides parameters for controlling various aspects of the analysis, including input file type, gene set database, and parameters for estimating null distributions.

## Use Cases
The following use cases demonstrate the application of this pipeline:

* Performing spatial enrichment analysis on a sample of 1000 high expression ROIs/spots/cells across multiple conditions.
* Testing a gene set in different samples with varying minimum spot/ROI/cell numbers to ensure robustness.
* Calculating standard deviations to define the high-expression threshold for a specific gene set.

## Implementation
This pipeline consists of the following modules:

* **Input Preprocessing**: normalizes spatial transcriptomics data coming from the `spatialGE.Preprocessing` module.
* **Gene Set Database Selection**: selects a gene set database to test for spatial enrichment (upload if not listed in MSigDB).
* **Permutation Estimation**: estimates null distributions using different permutations of the STenrich algorithm.
* **Random Seed Replication**: replicates results with varying random seed values to check for consistency.

## Parameters
The following parameters control various aspects of the analysis:

| Parameter | Description | Default Value | Required |
| --- | --- | --- | --- |
| `input_file` | Normalized spatial transcriptomics data | * | Yes |
| `gene_sets_database` | Select a gene set database to test for spatial enrichment | Upload if not listed as a choice from MSigDB | Yes |
| `permutations` | The number of permutations to estimate null distribution (no-spatial pattern) | 100 | Yes |
| `random_seed` | A seed number to replicate results | 12345 | No |
| `minimum_spots` | The minimum number of high expression ROIs/spots/cells required for a gene set to be tested | 5 | Yes |
| `minimum_genes` | The minimum number of genes of a set required to be present in a sample, for that gene set to be tested in that sample | 5 | Yes |
| `standard_deviations` | The number of standard deviations to define the high-expression threshold | 1.0 | No |
| `filter_p_values` | Plot only gene sets whose multiple test adjusted p-value is less than this threshold | 0.05 | No |
| `filter_gene_proportion` | Plot only gene sets where the proportional number genes in the set present in the field of view equals or exceeds this threshold | 0.3 | No |

Note: This README provides a general overview of the pipeline, and additional sections can be added as needed to provide further details on specific aspects of the implementation.