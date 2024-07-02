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
- **samples**: sequence data $$\rightarrow$$ checklist (e.g. taxon etc.)
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

#### Interactive

With this method, you'll use a mix of the web-browser and the server command line.

1. First, go to the [EBI-ENA](https://www.ebi.ac.uk/ena/submit/webin/login) website and register a study: from the dashboard, click on Register study.
Add a project title and short description + abstract. Download the receipt: remember, you'll need the **project accession number** (e.g. PRJEB77087) to link samples and reads to the project/study.

2. Register samples: download the spreadsheet template $$\rightarrow$$ Environmental Checklist $$\rightarrow$$ **GSC MIxS host associated**. Move `sample_alias` to the first column in the spreadsheet. 
Add optional columns if relevant: e.g. `host taxid` (*Bos taurus*: 9913), `host body site` (gut), `host sex`.

3. Fill in the spreadsheet: 
	- unique `sample_alias` and/or `sample_title` (name) from the mapping file (file of metadata); make sure that this is a unique ID also across experiments (sequence of 1, 2, 3 ... N is not a good choice)
	- `tax_id` (id codes from [NCBI](https://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi));
	- `scientific_name`, the name associated to `tax_id` (e.g. bovine gut metagenome); 
	- `project name`, the project accession number from point 1) (see above); 
	- collection date, geographic location and coordinates; importantly, you need to fill in also the environmental context and medium (from [EnvironmentalOntology](https://github.com/EnvironmentOntology/envo/wiki/Using-ENVO-with-MIxS)): you can repeat the same ontology code for all fields (e.g. `UBERON_0001007`) 

4. Upload the sample spreadsheet. This step can involve a number of iterations, as the EBI-ENA platform will run a number of check on the consistency of the information provided in the spreadsheet 

5. Upload the **fastq files** to the EBI-ENA archive  

