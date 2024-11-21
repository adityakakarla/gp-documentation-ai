# Spatial Data Preprocessing Module

## Description

This module provides a comprehensive overview of the spatial data preprocessing workflow, including command line options, script flow, and data structures used in the process.

## Module Details

### Authors

* Edwin

### Categories

* spatial transcriptomics
* Link: https://github.com/genepattern/spatialGE.Preprocessing

### Source Repo

* Link: https://github.com/genepattern/spatialGE.Preprocessing

### Contact

* Link: https://groups.google.com/g/genepattern-help

## Input Files (info + type)

| Info | Type |
| --- | --- |
| Expression Matrix File Paths | `exprmats` |
| Metadata File Paths | `metas` |
| Sample Names | `samples` |
| Image File Path | `image_file` |

## Output Files (info + type)

| Info | Type |
| --- | --- |
| STlist Object | `output.RData` |

## Parameters (formatted as a Markdown table with name, description, default value, and type)

| Name | Description | Default Value | Type |
| --- | --- | --- | --- |
| `-e`, `--exprmats` | Comma-separated list of expression matrix file paths | NULL | `list` |
| `-m`, `--metas` | Comma-separated list of metadata file paths | NULL | `list` |
| `-a`, `--samples` | Comma-separated list of sample names | NULL | `list` |
| `-w`, `--ws` | Weight to be applied to spatial distances (0-1) with a default value of 0.025 | 0.025 | `numeric` |
| `-d`, `--dist_metric` | Distance metric to be used with a default value of 'euclidean' | 'euclidean' | `string` |
| `-l`, `--linkage` | Linkage method applied to hierarchical clustering with a default value of 'ward.D2' | 'ward.D2' | `string` |
| `-k`, `--ks` | Range of k values to assess with a default value of 'dtc' | 'dtc' | `numeric` |
| `-t`, `--topgenes` | Number of genes with highest spot-to-spot expression variation with a default value of 2000 | 2000 | `integer` |
| `-s`, `--deepSplit` | Logical or integer (1-4) to control cluster resolution with a default value of FALSE | FALSE | `boolean` |
| `-p`, `--plot` | Option to plot intermediate results with a default value of FALSE | FALSE | `boolean` |
| `-o`, `--output` | Path to save the output STlist object with a default value of 'output.RData' | NULL | `string` |
| `-f`, `--image_zip` | Path to the zip file containing images with a default value of NULL | NULL | `string` |
| `-d`, `--temp_dir` | Temporary directory for extraction with a default value of 'image_extract_' | 'image_extract_' | `string` |

## Script Flow

1. Extract images from the zip file and load them into the `lung_subset` object.
2. Perform clustering using Spatial Clustering of Integers (SCIT) on the `lung_subset` object, applying the specified parameters.
3. If intermediate results are required, plot the cluster distribution with a specified color palette.
4. Finally, save the output STlist object to the specified file.

## Data Structures

* `expression_matrix`: A matrix of expression values
* `metadata`: A dictionary of metadata for each sample
* `sample_name`: The name of each sample
* `image_file`: The path to an image file in the 'CellComposite' folder