# rENM Framework

[![Lifecycle: experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://lifecycle.r-lib.org/articles/stages.html#experimental) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**A modular R system for reconstructing and analyzing long-term ecological niche dynamics in North American birds**

The rENM Framework integrates 45 years (1980–2020) of eBird citizen science occurrence records with NASA's MERRA-2 reanalysis data to reconstruct the spatio-temporal dynamics of climate-driven niche change in North American bird species. Rather than treating ecological niche models as static snapshots, rENM uses time-structured modeling to reveal how — and how fast — species' climatic environments have shifted across decades.

The complete pipeline can be run from a single function call:
``` r
library(rENM)
rENM("CASP")   # Cassin's Sparrow, for example, or any four-letter banding code ...
```
---

👉 **Start here** - Download the rENM Framework User Manual:
[rENM-Framework-User-Manual.pdf](https://github.com/user-attachments/files/28195648/rENM-Framework-User-Manual.pdf)

---

## What is rENM?

Retrospective ecological niche modeling (rENM) integrates historical species occurrence records with historical environmental data to reconstruct and analyze the spatio-temporal dynamics of species' responses to changing environmental conditions. The rENM Framework is a modular suite of R packages designed to support rENM analyses. By revealing long-term patterns, rENMs provide a powerful observational lens for addressing biological questions and assessing both the current and future conservation status of species, including:

-   Long-term trends in climatic suitability for a species
-   Acceleration and deceleration in these long-term trends
-   Changes in environmental structure across decades
-   Bioclimatic velocity and directional change in suitability
-   Hot spots of potential climate change vulnerability

## Framework Components

| Component | Role |
|---|---|
| [`rENM`](https://github.com/rENM-Framework/rENM) | Top-level orchestration; the single entry point for running the complete pipeline |
| [`rENM.core`](https://github.com/rENM-Framework/rENM.core) | Shared infrastructure: project directory resolution, species and variable metadata, logging |
| [`rENM.data`](https://github.com/rENM-Framework/rENM.data) | eBird occurrence extraction and MERRA-2 variable assembly, thinning, and temporal binning |
| [`rENM.model`](https://github.com/rENM-Framework/rENM.model) | Ensemble ENM construction and five-year time-series assembly using the sdm framework |
| [`rENM.analysis`](https://github.com/rENM-Framework/rENM.analysis) | Suitability trends, centroid tracking, bioclimatic velocity, hotspot detection, range change |
| [`rENM.ai`](https://github.com/rENM-Framework/rENM.ai) | AI-ready package assembly and submission to Claude and ChatGPT for interpretive analysis |
| [`rENM.reports`](https://github.com/rENM-Framework/rENM.reports) | Summary tables, per-topic report pages, and final species PDF report assembly |

## Workflow Overview

**rENM → rENM.core + rENM.data → rENM.model → rENM.analysis → rENM.ai → rENM.reports**

  The rENM framework's modules allow a user to do the following:

1. Orchestrate the complete pipeline for a species (`rENM`)
2. Assemble occurrence data and environmental predictors (`rENM.core`, `rENM.data`)
3. Construct multi-decadal historical ENM time series (`rENM.model`)
4. Analyze trends in climatic suitability and environmental structure (`rENM.analysis`)
5. Perform GenAI-driven interpretations of the trend analyses (`rENM.ai`)
6. Generate reproducible reports (`rENM.reports`)

## Framework Resources

| Component | Role |
|---|---|
| [rENM-documentation](https://github.com/rENM-Framework/rENM-documentation) | User manual and R package reference manuals |
| [rENM-publications](https://github.com/rENM-Framework/rENM-publications) | Papers relating to rENM development and use |

## Example Reports

The rENM Framework includes an experimental AI-assisted module that leverages the interpretive capabilities of ChatGPT and Claude to generate preliminary ecological analyses for review and evaluation by domain experts. Continued refinement, validation, and expansion of these capabilities are an important area of ongoing development. The following are summary analyses for the three bird species included in the Framework’s example dataset. You can browse these online.

| ChatGPT Report | Claude Report |
|---|---|
| [Cassin's Sparrow (<i>Peucaea cassinii</i>)](https://storage.googleapis.com/renm_docs/CASP-Final-Report.pdf) | [Cassin's Sparrow (<i>Peucaea cassinii</i>)](https://storage.googleapis.com/renm_docs/CASP-Final-Report2.pdf) |
| [Greater Roadrunner (<i>Geococcyx californianus</i>)](https://storage.googleapis.com/renm_docs/GRRO-Final-Report.pdf) | [Greater Roadrunner (<i>Geococcyx californianus</i>)](https://storage.googleapis.com/renm_docs/GRRO-Final-Report2.pdf) |
| [Brown-capped Rosy-Finch (<i>Leucosticte australis</i>)](https://storage.googleapis.com/renm_docs/BCRF-Final-Report.pdf) | [Brown-capped Rosy-Finch (<i>Leucosticte australis</i>)](https://storage.googleapis.com/renm_docs/BCRF-Final-Report2.pdf) |

## Example Runs

The rENM Framework generates a collection of output products that can support further analysis, conservation status assessments, climate change impact projections, and conservation policy development. Continued refinement, validation, and expansion of these capabilities also remain important areas of ongoing development. The following are collections for the three bird species included in the Framework’s example dataset. Clicking the links below will download ZIP archives containing the complete output collections, which can then be browsed locally on your machine.

| Species | Banding Code | File Size | Compute Time | ChatGPT Cost |
|---|---|---|---|---|
| [Cassin's Sparrow (<i>Peucaea cassinii</i>)](https://storage.googleapis.com/renm_runs/CASP.zip) | CASP | 347.1 MB | 19.3 mins | $0.09 |
| [Greater Roadrunner (<i>Geococcyx californianus</i>)](https://storage.googleapis.com/renm_runs/GRRO.zip) | GRRO | 474.1 MB | 19.3 mins | $0.16 |
| [Brown-capped Rosy-Finch (<i>Leucosticte australis</i>)](https://storage.googleapis.com/renm_runs/BCRF.zip)| BCRF | 128.1 MB | 15.1 mins | $0.11 |

## Installation

Install Framework packages from GitHub in dependency order:

``` r
# install.packages("remotes")
remotes::install_github("rENM-Framework/rENM.core")
remotes::install_github("rENM-Framework/rENM.data")
remotes::install_github("rENM-Framework/rENM.model")
remotes::install_github("rENM-Framework/rENM.analysis")
remotes::install_github("rENM-Framework/rENM.ai")
remotes::install_github("rENM-Framework/rENM.reports")
remotes::install_github("rENM-Framework/rENM")
```

## Selected Publications

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. (in preparation). The rENM Framework: Toward a Modular System for Reconstructing and Analyzing Long-Term Ecological Niche Dynamics.

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2026. Shifts in seasonal
climatic suitability for Cassin’s Sparrow (<i>Peucaea cassinii</i>) over four decades. The Southwestern
Naturalist, 70(1):1-17. https://doi.org/10.1894/0038-4909-70.1.7

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2025. Shifts in breeding phenology for Cassin’s Sparrow (Peucaea cassinii) over four decades. Journal of Field Ornithology 96(3):3. https://doi.org/10.5751/JFO-00691-960303

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2024. Complex changes in climatic suitability for Cassin’s Sparrow (Peucaea cassinii) revealed by retrospective ecological niche modeling. Journal of Field Ornithology 95(1):9. https://doi.org/10.5751/JFO-00432-950109

Schnase, J.L., and M.L. Carroll. 2023. “The MMX Toolkit: High-Performance, Reanalysis-Based Climatic Suitability Modeling to Advance Avian Conservation.” In Proceedings of the 2023 Conference on Big Data from Space (BiDS’23): 6-9 November 2023, edited by P. Soille, S. Lumnitz, and S. Albani, 299–303. Austrian Center, Vienna: Publications Office of the European. https://doi.org/10.2760/46796.

Schnase, J.L. and Carroll, M.L. 2022. Automatic variable selection in ecological niche modeling: a case study using Cassin’s Sparrow (Peucaea cassinii). PLoS One. 2022 Jan 21;17(1):e0257502. https://doi.org/10.1371/journal.pone.0257502. PMID: 35061658; PMCID: PMC8782318.

Schnase, J.L., M.L. Carroll, R.L. Gill, G.S. Tamkin, J. Li, S.L. Strong, T.P. Maxwell, M.E. Aronne, and C.S. Spradlin. Toward a Monte Carlo approach to selecting climate variables in MaxEnt. PLoS One. 2021. Mar 3;16(3):e0237208. https://doi.org/10.1371/journal.pone.0237208. PMID: 33657125; PMCID: PMC7928495.

## Status and Support

The rENM Framework is an active research platform under ongoing development, provided for educational and research purposes. It is distributed without formal technical support. Feedback and contributions are welcome at [rENM.Framework\@gmail.com](mailto:rENM.Framework@gmail.com).

© 2021–2026 John L. Schnase and Collaborators  \|  MIT License

