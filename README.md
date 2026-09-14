# Pune-riparian-tree-community-analysis
Reproducible analysis of tree species distribution, community structure, and diversity across five ecological riparian zones in Pune.
# Tree Community Structure Across Ecological Zones

## Overview

This repository contains a reproducible analysis of tree-community data collected across five spatially distinct ecological riparian zones in Pune.

Data collection was done using the iNaturalist app.

The aim of the analysis was to investigate how tree species are distributed across zones, identify species with similar distribution patterns, and characterize species that are broadly distributed versus strongly associated with particular zones.

The analysis combines multivariate ordination, species-level distribution patterns, tree-size structure, core-species identification, and alpha-diversity metrics.

## Biological Questions

The analysis addresses five main questions:

1. **Do tree species show distinct distribution patterns across the five zones?**
2. **Which species exhibit similar abundance profiles across zones?**
3. **Which abundant species show differences in tree-size (girth) distributions among zones?**
4. **Which species form the core tree community across zones, and which are more zone-associated?**
5. **Do species richness and diversity differ among zones?**

## Analytical Workflow

### 1. Bray–Curtis PCoA of species distributions

A species × zone abundance matrix was constructed, with species as rows and the five zones as columns.

Bray–Curtis dissimilarities were calculated from species abundance profiles across zones, followed by classical Principal Coordinates Analysis (PCoA).

This analysis allows species with similar distribution patterns across zones to occupy similar regions of ordination space.

Species were additionally assigned to the zone in which their abundance was highest to visualize zone-associated distribution patterns.

**Interpretation:**  
Species occupying similar regions of the ordination have similar abundance distributions across the five zones, while species occupying distinct regions show different spatial distribution profiles.

### 2. PCA of tree girth structure

Mean tree girth as an inference of age was summarized by species and zone and subjected to principal component analysis.

This analysis explores whether differences in tree size structure are associated with particular zones and/or species.

### 3. Girth distributions of abundant species

Ridgeline plots were used to visualize the distribution of tree girth for abundant species across the five zones.

These plots provide a species-level view of differences in size structure that may not be apparent from mean values alone.

### 4. Core species analysis

A species × zone abundance matrix was used to identify species that occur consistently across zones versus species whose distributions are more restricted to particular zones.

A heatmap was generated to visualize these patterns and identify candidate core and zone-associated species.

### 5. Alpha diversity

Species richness and diversity were characterized using:

- **Chao1** — estimated species richness
- **Simpson's index** — community diversity accounting for abundance and dominance

Box and violin plots were used to visualize the distribution of diversity estimates across the five zones.

## Key Outputs

The analysis generates:

- Bray–Curtis PCoA of species distribution profiles
- PCA of species-level mean girth
- Ridgeline plots of girth distributions for abundant species
- Core-species heatmap
- Simpson and Chao1 diversity plots

## Interpretation

Together, these analyses provide complementary views of spatial variation in the tree community:

**Species distribution → Tree structure → Species-specific patterns → Core community → Diversity**

The multivariate analysis is particularly useful for identifying groups of species with similar distribution profiles across zones in Pune, while the abundance and core-species analyses provide direct context for interpreting those patterns.

The results are intended to characterize **zone-associated species assemblages and broadly distributed species**, rather than to infer causal effects of zone membership.

## Reproducibility

All analyses were implemented using scripted workflows in Python.

The repository is organized to separate data processing, statistical analysis, and visualization so that the workflow can be reproduced or adapted to similar ecological community datasets.

### Main tools

- RStudio


## Repository Structure

```text
tree-community-analysis/
│
├── README.md
│
├── scripts/
│   ├── 01_data_processing.py
│   ├── 02_bray_curtis_pcoa.py
│   ├── 03_girth_pca.py
│   ├── 04_girth_distributions.py
│   ├── 05_core_species.py
│   └── 06_diversity_analysis.py
│
├── figures/
│   ├── bray_curtis_pcoa.png
│   ├── girth_pca.png
│   ├── girth_ridgeline.png
│   ├── core_species_heatmap.png
│   └── alpha_diversity.png
│
└── data/
    └── README.md
