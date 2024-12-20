
# ssMutPA

[![Current devel version: 0.1.2](https://img.shields.io/badge/devel%20version-0.1.2-blue.svg)](https://github.com/nanyuan-he/ssMutPA)
[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![License: GPL v2](https://img.shields.io/badge/License-GPL_v2-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/09b138b2fa9242229f081cd180f6fc91)](https://app.codacy.com/gh/nanyuan-he/ssMutPA/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://makeapullrequest.com)
[![Last commit](https://img.shields.io/github/last-commit/nanyuan-he/ssMutPA.svg)](https://github.com/nanyuan-he/ssMutPA/commits/master)
[![Code size](https://img.shields.io/github/languages/code-size/nanyuan-he/ssMutPA.svg)](https://github.com/nanyuan-he/ssMutPA)

ssMutPA is a single-sample mutation-based pathway analysis method for inferring mutation-induced pathway activity profiles.

## Introduction

`ssMutPA` is a single-sample mutation-based pathway analysis method. It integrates somatic mutation data with the protein-protein interaction network and calculates single-sample mutation-based pathway enrichment score (ssMutPES) using the local weighted and global propagation strategies.

ssMutPA complements the current individualized pathway analysis approaches that focus on gene expression data and provide something new insight into the initiation and progression of cancer.
![A simple schema of the labyrinth](man/figure/introduce.jpg)


## A notice on operating system compatibility

We recommended these dependencies to be installed:

- ** R (≥ 4.0.0)**: We developed this R package using R version 4.3.0.
- ** When calculating single-sample mutation-based pathway activity profiles, if your computer has multiple CPU cores, you can increase the computational efficiency by setting the 'Numcore' parameter in the `get_RWR_ES` function.



## Installation

Install `ssMutPA` using:

``` r
install.packages('devtools')
devtools::install_github("nanyuan-he/ssMutPA")
```


## Usage

Load the package using `library(ssMutPA)`. We provide a vignette for the package that can be called using: `vignette("ssMutPA")`. Alternatively, you can view the online version on [CRAN](https://cran.r-project.org/web/packages/ssMutPA/index.html). The examples I provided would take several minutes to run on a normal desktop computer.



