# Audio description quality: Systematic scoping review

Supplementary materials for:

> Dallı, H., Jankowska, A., Schrijver, I., González Fernández, C. A., Reviers, N.,
> & Vercauteren, G. (2026). Audio description quality: A systematic scoping
> review. *Cadernos de Tradução, 46*(1), pp. xx–xx.

<!-- After archiving a release on Zenodo, paste the badge here:
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)
-->

This repository holds the corpus bibliography, the codebook guide, the two
charted data appendices, and the code that draws the figures reported in the
article.

## Contents

| File | What it is |
|---|---|
| `APX1_Bibliography.pdf` | Bibliography of the entire corpus |
| `APX2_Codebook_Guide.pdf` | The codebook guide |
| `APX3A_Cases_Studies.xlsx` | Appendix 3A — the 75 academic sources, one row per source |
| `APX3B_Cases_Guidelines.xlsx` | Appendix 3B — the 18 industry documents, one row per document |
| `APX4_Code.Rmd` | Reproducible code for Figures 2, 3, 5, 6, 7 and 8 |
| `APX4_Code.html` | The same document knitted, for reading without R |
| `figures/` | Every figure as PDF and PNG, with the summary tables the code writes |

## Reading the two data appendices

Both workbooks share one naming convention. A prefix in square brackets marks
the block a column belongs to:

| Prefix | What the columns hold |
|---|---|
| `[BIB]` | Bibliographic metadata — author, year, publication type, region, discipline, AD modality |
| `[MET]` | Study design — study type, research approach, data collection, quality assessment instrument |
| `[PAR]` | Describer and evaluator profiles, including group-specific sample sizes |
| `[COD]` | Coverage of each node of the AD Quality Dimensions framework |

A `[COD]` value is **proportional coverage**: the percentage of that source's
material coded at the node. **A zero therefore means the node was not coded in
that source** — it records an absence of coding, not a measured absence of the
concept. `NA` marks a field that does not apply to a source, and `Unassigned`
a field not yet charted; both are shown in grey.

The `[COD]` columns run the four parent nodes first (Service, Script, Voice,
Sound), then the thirteen children, then the grandchildren and
great-grandchildren. `APX2_Codebook_Guide.pdf` defines every node, gives its
inclusion criteria and examples, and explains how the codebook's categories
were operationalised when charting these two files. The code selects columns by
name and never by position, so inserting a column will not break it.

## Reproducing the figures

Knitting `APX4_Code.Rmd` regenerates every figure it covers, as both PDF and
PNG, into `figures/`, together with four summary tables:
`Figure5_summary.csv`, `Figure8_summary.csv`, `Figure8_study_groups.csv` and
`Figure8_audit.csv`.

**Requirements.** R 4.1 or later (the code uses the native pipe). The figures
were last built under R 4.3.3 with ggplot2 3.4.4 and readxl 1.4.3; the exact
package versions are printed at the end of `APX4_Code.html`.

```r
install.packages(c("readxl", "dplyr", "tidyr", "tibble", "purrr", "stringr",
                   "forcats", "readr", "ggplot2", "scales", "ggrepel",
                   "patchwork", "ggforce", "rmarkdown"))

rmarkdown::render("APX4_Code.Rmd")
```

Run it from this folder: paths are relative, and the document reads the two
`.xlsx` appendices from beside itself.

**A note on the typeface.** The published figures are set in Gill Sans MT,
the journal's font. If it is not installed the code falls back to the graphics
device's default family, which changes the lettering and nothing else.

## Figures

| Figure | Source |
|---|---|
| 1 | PRISMA 2020 flowchart — drawn, no code |
| 2 | Inter-rater agreement across hierarchical codebook levels and frameworks |
| 3 | Corpus profile by discipline, modality and research type |
| 4 | The four interlocking sites of the agential ecology — drawn, no code |
| 5 | Prevalence of AD Quality Dimensions across academic and industry sources |
| 6 | Child-level prevalence of AD Quality Dimensions by disciplinary practice |
| 7 | Co-occurrence of child-level AD Quality Dimensions across the combined corpus |
| 8 | Evaluator group composition |

Figures 1 and 4 are diagrams rather than plots of charted data. They were drawn
directly and have no code to report, but are included in `figures/` so the set
is complete.

## How to cite

Please cite the article. If you are citing the materials themselves — the
codebook, the charted dataset, or the figure code — cite the archived release
as well; `CITATION.cff` carries the machine-readable metadata, and GitHub turns
it into a "Cite this repository" button.

## Contact

Harun Dallı, University of Antwerp — harun.dalli@uantwerpen.be —
[0000-0001-8753-6024](https://orcid.org/0000-0001-8753-6024)

Corrections and questions are welcome through the repository's issue tracker.
