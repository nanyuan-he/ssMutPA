
# ssMutPA

[![Current devel version: 0.1.1](https://img.shields.io/badge/devel%20version-0.1.1-blue.svg)](https://github.com/nanyuan-he/ssMutPA)
[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![License: GPL v2](https://img.shields.io/badge/License-GPL_v2-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/09b138b2fa9242229f081cd180f6fc91)](https://app.codacy.com/gh/nanyuan-he/ssMutPA/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://makeapullrequest.com)
[![Last commit](https://img.shields.io/github/last-commit/nanyuan-he/ssMutPA.svg)](https://github.com/nanyuan-he/ssMutPA/commits/master)
[![Code size](https://img.shields.io/github/languages/code-size/nanyuan-he/ssMutPA.svg)](https://github.com/nanyuan-he/ssMutPA)

ssMutPA is a single-sample mutation-based pathway analysis method for inferring mutation-induced pathway activity profiles.

## Introduction

`ssMutPA` is a single-sample mutation-based pathway analysis method. It integrates somatic mutation data with the protein-protein interaction network and calculates single-sample mutation-based pathway enrichment score (ssMutPES) using the local weighted and global propagation strategies.

![A simple schema of the labyrinth](man/figure/introduce.jpg)


## A notice on operating system compatibility

We recommended these dependencies to be installed:

- **R (≥ 4.0.0)**: We developed this R package using R version 4.3.0.



## Installation

Install `ssMutPA` using:

``` r
install.packages(c('devtools', 'BiocManager'))
remotes::install_github("nanyuan-he/ssMutPA")
```


## Usage

Load the package using `library(ssMutPA)`. We provide a vignette for the package that can be called using: `vignette("ssMutPA")`. 



