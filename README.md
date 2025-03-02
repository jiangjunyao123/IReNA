IReNA: integrated regulatory network analysis of single-cell
transcriptomes
================

<!-- README.md is generated from README.Rmd. Please edit that file -->

[![](https://img.shields.io/badge/r-version4.04-green.svg)](https://www.r-project.org)
[![](https://img.shields.io/badge/Seurat-version4.01-red.svg)](https://satijalab.org/seurat/articles/get_started.html)
[![](https://img.shields.io/badge/monocle-version2.18-blue.svg)](http://cole-trapnell-lab.github.io/monocle-release)
[![](https://img.shields.io/badge/publication-iscience-purple.svg)](https://www.cell.com/iscience/pdf/S2589-0042(22)01631-5.pdf)

## Significance of IReNA

There are several cell states involved in cell development or disease
occurrence (e.g., progenitor, precursor, immature, and mature), each
state maintained by a unique gene program (**gene regulatory modules**). Decoding the
**inter**- or **intra**-regulatory mechanisms among these modules can
further elucidate the key mechanisms that regulate cell state
transitions, including identifying key transcription factors that
regulate cell fate decisions or cell differentiation. Most current gene
regulatory network (GRN) analysis methods focus on **intra**-modular
regulations; they select all cell states or single cell states to
construct GRNs and **neglect inter**-modular regulations.

IReNA can address this gap by identifying transcription factors (TFs)
that regulate other modules and inferring inter-modular interactions
through hypergeometric tests. For instance, if IReNA identifies **TF A**
from **module a** significantly activating **module b**, we can infer
that TF A may regulate the differentiation of the progenitor state into
the precursor state. In a second case, if IReNA identifies **TF B** from
**module c** significantly repressing **module d**, we can infer that TF
B represses the differentiation process from the immature state to the
mature state.

<img src="docs/Readme%20figure/significance.png"
style="width:80.0%;height:80.0%" />

## Workflow

<img src="docs/Readme%20figure/workflow_new.jpg"
style="width:60.0%;height:60.0%" />

## Installation

IReNA needs R version 4.0 or higher, and
[Bioconductor](http://bioconductor.org/) version 3.12.

First, install Bioconductor, open R platform and run:

``` r
if (!requireNamespace("BiocManager", quietly = TRUE))
install.packages("BiocManager")
BiocManager::install(version = "3.12")
```

Next, install several Bioconductor dependencies:

``` r
BiocManager::install(c('Rsamtools', 'ChIPseeker', 'monocle',
                       'RcisTarget', 'RCy3', 'clusterProfiler'))
```

Then, install IReNA from GitHub:

``` r
install.packages("devtools")
devtools::install_github("jiang-junyao/IReNA")
```

Finally, check whether IReNA was installed correctly, restart R session
and run:

``` r
library(IReNA)
```

## Quick start

- [Run IReNA based on seurat object (without pre-build GRN and gene
  modules)](https://jiang-junyao.github.io/IReNA/qucik-start)

- [Run IReNA based on pre-build GRN and gene
  modules](https://jiang-junyao.github.io/IReNA/qucik-start2)

## News

2024.11.12: add the signifiance of IReNA and update the workflow.

2024.10.17: add qucik start tutorial at the ReadME page.

## Full tutorials

- [Regulatory network analysis through only scRNA-seq
  data](https://jiang-junyao.github.io/IReNA/only-scRNA)

- [Regulatory network analysis through intergrating scRNA-seq data and
  scATAC-seq data](https://jiang-junyao.github.io/IReNA/scATAC+scRNA)

- [Regulatory network analysis through intergrating scRNA-seq data and
  bulk ATAC-seq
  data](https://jiang-junyao.github.io/IReNA/bulk-ATAC+scRNA)

## External links

[An example of applying IReNA to identify key transcription factors 
in retinal
regeneration](https://github.com/jiewwwang/Single-cell-retinal-regeneration)

## Citation

Jiang J, Lyu P, Li J, et al. IReNA: Integrated regulatory network analysis of single-cell transcriptomes and chromatin accessibility profiles. [iScience 2022, 25(11): 105359.](https://www.cell.com/iscience/fulltext/S2589-0042(22)01631-5)

Hoang T, Wang J, Boyd P, et al. Gene regulatory networks controlling vertebrate retinal regeneration. [Science 2020, 370 (6519): eabb8598.](https://www.science.org/doi/abs/10.1126/science.abb8598)

## Help and Suggestion

If you have any question, comment or suggestion, please use github issue
tracker to report issues of IReNA or contact <jyjiang@link.cuhk.edu.hk>.
I will answer you timely, and please remind me again if you have not
received response more than three days.
