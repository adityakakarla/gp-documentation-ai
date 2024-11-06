## Parameters
<!-- short description of the module parameters and their default values, as well as whether they are required -->

| Name                 | Description                                                                                                                                                                              | Default Value |
----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| input file *         | Normalized spatial transcriptomics data coming from the spatialGE.Preprocessing module.                                                                                                  |
| gene sets database * | Select a gene set database to test for spatial enrichment. Upload a gene set if your gene set is not listed as a choice from MSigDB.                                                     |               |
| permutations *       | The number of permutations to estimate the null distribution (no-spatial pattern). The more permutations, the longer STenrich takes to complete, but p-values may be more accurate.      | 100           |
| random seed *        | A seed number to replicate results. It is advisable to run STenrich with different seed values to check for consistency. Different seed values could yield slightly different p-values. | 12345         |
| minumum spots * | The minimum number of high expression ROIs/spots/cells required for a gene set to be tested. If a sample has less than this number of high expression ROIs/spots/cells, the gene set is not tested in that sample. | 5 |
| minimum genes * | The minimum number of genes of a set required to be present in a sample, for that gene set to be tested in that sample. If a sample has less genes of a set than this number, the gene set is ignored in that sample. | 5 |
| standard deviations * | The number of standard deviations to define the high expression threshold. If an ROI/spot/cell has average gene set expression larger than the entire sample average plus this many standard deviations, it will be considered a high-expression ROI/spot/cell. | 1.0 |
| filter p values * | Plot only gene sets whose multiple test adjusted p-value is less than this threshold. | 0.05 |
| filter gene proportion * | Plot only gene sets where the proportional number genes in the set present in the field of view equals or exceeds this threshold. | 0.3 |

\*  required
