# rENM Framework

**A Modular System for Reconstructing and Analyzing Long-Term Ecological Niche Dynamics**

  ---

  👉 **Start here** - Download installation instructions and workflow examples:\
[rENM-Framework-User-Manual.pdf](https://github.com/user-attachments/files/27452573/rENM-Framework-User-Manual.pdf)

## What is rENM?

**Retrospective ecological niche modeling (rENM)** integrates historical species occurrence records with historical environmental data to reconstruct and analyze the spatio-temporal dynamics of species' responses to changing environmental conditions. The **rENM framework** is a **modular suite of R packages** designed to support rENM analyses.

By revealing long-term patterns, rENMs provide a powerful **observational lens** for addressing biological questions and assessing both the **current and future conservation status of species**. Rather than treating ecological niche models as static representations, the rENM framework uses **time-structured modeling** to reveal:

-   Long-term trends in climatic suitability for a species
-   Acceleration and deceleration in these long-term trends
-   Changes in environmental structure across decades
-   Bioclimatic velocity and directional change in suitability
-   Hot spots of potential climate change vulnerability

Although this analytical approach is broadly applicable across taxa, the current implementation of the rENM framework is designed to investigate **climate-driven dynamics in North American bird species**. The framework **spans 45 years (1980–2024)**, leveraging citizen science observations from the **Cornell Lab of Ornithology's eBird database** alongside environmental data derived from **NASA Earth system models**.

## Framework Components

| Component | Role |
  |---|---|
  | rENM | Top-level orchestration package for the rENM framework |
  | rENM.core | Shared utilities for the rENM framework |
  | rENM.data | Data assembly tools for the rENM framework |
  | rENM.model | Modeling tools for the rENM framework |
  | rENM.analysis | Analysis tools for the rENM framework |
  | rENM.reports | Report generation tools for the rENM framework |
  | rENM.ai | GenAI tools for the rENM framework |

  ## Usage

  The simplest way to run the complete rENM pipeline for a species is through
the top-level orchestration package:

  ``` r
library(rENM)
rENM("CASP")
```

At this stage of development, rENM() functions as a deterministic supervisory agent for the scientific workflow. A single function call executes the entire pipeline in sequence — including data assembly, time-series construction, trend analysis, AI-assisted interpretation, and report generation — for the target species. The workflow overview below describes the purpose and operations of each stage in detail.

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
| rENM-documentation | User manual and R package reference manuals |
| rENM-publications | Papers relating to rENM development and use |
| rENM-scripts | Utility scripts |

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

## Framework Repositories

**_R packages:_**\
<https://github.com/rENM-Framework/rENM>\
<https://github.com/rENM-Framework/rENM.core>\
<https://github.com/rENM-Framework/rENM.data>\
<https://github.com/rENM-Framework/rENM.model>\
<https://github.com/rENM-Framework/rENM.analysis>\
<https://github.com/rENM-Framework/rENM.reports>\
<https://github.com/rENM-Framework/rENM.ai>

**_Other resources:_**\
<https://github.com/rENM-Framework/rENM-documentation>\
<https://github.com/rENM-Framework/rENM-publications>\
<https://github.com/rENM-Framework/rENM-scripts>

## Package Installation

``` r
install.packages("devtools")
devtools::install_github("rENM-Framework/rENM")
devtools::install_github("rENM-Framework/rENM.core")
devtools::install_github("rENM-Framework/rENM.data")
devtools::install_github("rENM-Framework/rENM.model")
devtools::install_github("rENM-Framework/rENM.analysis")
devtools::install_github("rENM-Framework/rENM.reports")
devtools::install_github("rENM-Framework/rENM.ai")
```

## Research Status Disclaimer

The rENM Framework is an experimental research platform currently under active development. We are releaseing the software, workflows, and analytical methods to encourage exploration, evaluation, replication, and further refinement by the broader community. While the framework has produced promising results in our own studies — including potentially important new insights into the climatic ecology and natural history of Cassin’s Sparrow — these approaches should be regarded as exploratory and investigational rather than fully validated operational methods. We hope others will test the framework, evaluate its strengths and limitations, and contribute to the continued advancement of climate-informed ecological modeling and conservation analysis.

## Related Publications

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. (in preparation). The rENM Framework: Toward a Modular System for Reconstructing and Analyzing Long-Term Ecological Niche Dynamics.

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2026. Shifts in seasonal
climatic suitability for Cassin’s Sparrow (<i>Peucaea cassinii</i>) over four decades. The Southwestern
Naturalist, 70(1):1-17. https://doi.org/10.1894/0038-4909-70.1.7

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2025. Shifts in breeding phenology for Cassin’s Sparrow (Peucaea cassinii) over four decades. Journal of Field Ornithology 96(3):3. https://doi.org/10.5751/JFO-00691-960303

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2024. Complex changes in climatic suitability for Cassin’s Sparrow (Peucaea cassinii) revealed by retrospective ecological niche modeling. Journal of Field Ornithology 95(1):9. https://doi.org/10.5751/JFO-00432-950109

Schnase, J.L., and M.L. Carroll. 2023. “The MMX Toolkit: High-Performance, Reanalysis-Based Climatic Suitability Modeling to Advance Avian Conservation.” In Proceedings of the 2023 Conference on Big Data from Space (BiDS’23): 6-9 November 2023, edited by P. Soille, S. Lumnitz, and S. Albani, 299–303. Austrian Center, Vienna: Publications Office of the European. https://doi.org/10.2760/46796.

Schnase, J.L. and Carroll, M.L. 2022. Automatic variable selection inf ecological niche modeling: a case study using Cassin’s Sparrow (Peucaea cassinii). PLoS One. 2022 Jan 21;17(1):e0257502. https://doi.org/10.1371/journal.pone.0257502. PMID: 35061658; PMCID: PMC8782318.

Schnase, J.L., M.L. Carroll, R.L. Gill, G.S. Tamkin, J. Li, S.L. Strong, T.P. Maxwell, M.E. Aronne, and C.S. Spradlin. Toward a Monte Carlo approach to selecting climate variables in MaxEnt. PLoS One. 2021. Mar 3;16(3):e0237208. https://doi.org/10.1371/journal.pone.0237208. PMID: 33657125; PMCID: PMC7928495.

## License

MIT License

Copyright (c) 2021-2026 John L. Schnase and Collaborators

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

**Contact:** rENM.Framework@gmail.com | **Issues:**  <https://github.com/rENM-Framework/rENM/issues>

---

