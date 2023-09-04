---
layout: post
title: "Simplified guidelines to submit 16S rRNA-gene seq data to ENA"
author: "Filippo Biscarini"
date: "2023-09-04"
categories: BIOINFORMATICS MICROBIOME
---

ENA (European Nucleotide Archive) is the repository for sequence data hosted by [EMBL-EBI](https://www.ebi.ac.uk/) (European Molecular Biology Laboratory - European Bioinformatics Institute).

### ENA metadata model

<u>Metadata</u>
- **study** (project): accession number
- **samples**: sequence data $\rightarrow$ checklist (e.g. taxon etc.)
- **experiment**: sequencing experiment

<u>Data files</u>
- *run*: sequence data
- *analysis*: other data files (e.g. OTU/ASV table)

### What to submit

Ordered list of conceptual steps to undertake for data submission:

1. study: place-holder for the project
2. samples: place-holder for the sequence data
3. raw reads: sequencing information (experiment) + sequence data files (run)

### How to submit

- <u>Interactive</u>: via browser
- <u>Webin-CLI</u>: command-Line Interface
- <u>Programmatic</u>: XML + cURL


