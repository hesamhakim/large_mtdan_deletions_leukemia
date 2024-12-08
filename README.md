# Mitochondrial DNA Deletion Analysis Pipeline in ALL

This repository contains the analysis pipeline used in the manuscript "Distinct Mitochondrial DNA Deletion Profiles in Pediatric B-Cell and T-Cell Acute Lymphoblastic Leukemia: Implications for Disease Etiology and Treatment Response". The pipeline analyzes patterns of large mitochondrial DNA deletions in B-ALL and T-ALL cancer samples.

## Pipeline Overview

The analysis pipeline consists of several R scripts that perform sequential analyses of mitochondrial DNA deletion patterns:

1. **Circular Visualization** (`Cricular_visual_deletion.R`)
   - Creates circular plots of mitochondrial genome and deletions
   - Visualizes deletion patterns for different sample groups
   - Shows gene locations and deletion frequencies
   - Supports random sampling of cases for visualization

2. **Sample-Level Analysis** (`sample_distances_03.R`)
   - Comprehensive analysis of mtDNA deletion profiles
   - Performs PCA and hierarchical clustering
   - Generates heatmaps of deletion patterns
   - Conducts PERMANOVA analysis
   - Analyzes common deletion patterns across groups
   - Performs mixed-effects modeling for clonal dynamics

3. **Repeat Pattern Analysis** (`Large_del_Repeat_pattern_analysis.R`)
   - Analyzes sequence patterns at deletion breakpoints
   - Identifies perfect and imperfect repeats
   - Calculates GC content and sequence characteristics
   - Generates visualizations of repeat patterns
   - Supports multiple sample group comparisons

4. **Gene Impact Analysis** (`Compare_deleted_genes.R`)
   - Compares deletion patterns between B-ALL groups
   - Analyzes affected genes and their frequencies
   - Performs statistical comparisons between groups
   - Generates comprehensive visualization of results

5. **Clinical Association Analysis** (`MANOVA_clinical_molecular_vars.R`)
   - Performs MANOVA analysis of clinical variables
   - Associates molecular features with clinical outcomes
   - Generates statistical summaries and visualizations
   - Exports results in Excel format

## Prerequisites

Required R packages:
```R
# Data manipulation and analysis
library(tidyverse)
library(dplyr)
library(readr)
library(readxl)

# Visualization
library(ggplot2)
library(ggforce)
library(pheatmap)
library(ComplexHeatmap)
library(RColorBrewer)
library(patchwork)

# Statistical analysis
library(vegan)
library(car)
library(lme4)
library(emmeans)

# Sequence analysis
library(Biostrings)

# Other utilities
library(gridExtra)
library(rlang)
```

## Input Data Requirements

The pipeline expects the following input files:

1. Clinical Data:
   - Patient metadata (diagnosis, timepoints, clinical features)
   - Sample quality metrics
   - Treatment information

2. Deletion Data:
   - Breakpoint coordinates
   - Deletion frequencies
   - Read support metrics

3. Reference Data:
   - Mitochondrial genome sequence (FASTA)
   - Gene annotations (BED format)
   - Other reference files as needed

## Usage

1. Set up the working directory and input files:
```R
working_dir <- "path/to/working/directory"
setwd(working_dir)
```

2. Run the scripts in the following order:
```R
# 1. Visualize deletions
source("Cricular_visual_deletion.R")

# 2. Perform comprehensive deletion analysis
source("sample_distances_03.R")

# 3. Analyze repeat patterns
source("Large_del_Repeat_pattern_analysis.R")

# 4. Compare deletion patterns between groups
source("Compare_deleted_genes.R")

# 5. Associate with clinical variables
source("MANOVA_clinical_molecular_vars.R")
```

## Output

The pipeline generates several types of outputs:

1. Visualizations:
   - Circular genome plots
   - PCA plots
   - Heatmaps
   - Statistical visualization

2. Statistical Results:
   - PERMANOVA results
   - MANOVA results
   - Mixed-effects model outputs
   - Group comparisons

3. Data Tables:
   - Deletion summaries
   - Gene impact analyses
   - Clinical associations

All outputs are organized in the following directory structure:
```
project/
├── figures/
│   ├── CPM_ALL_Circle/
│   └── CPM_ALL_stats/
├── tables/
│   └── CPM_ALL_deletions_statistics/
└── data/
    └── annotations/
```

## Citation

...
## License

...
## Contact

...
