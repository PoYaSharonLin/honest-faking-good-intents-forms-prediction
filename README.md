# What People Say And How They Move: A Causal Reanalysis of Cursor-Based Faking-Good Detection in Online Personality Questionnaires

## One-line project summary

This is a **fork** of the original authors' repository. On top of all the original material, it adds a
**causal re-analysis** of the original authors' data: it compares the **Faking-Good (FG)** and
**Honest (H)** groups using inverse-probability-of-treatment weighting (IPTW) and doubly-robust
estimators.

The final report is in the repository **root** as a PDF file.

---

## Repository structure

```
.
├── README.md                                   ← this file
├── <final report>.pdf                          ← the final report (root directory)
├── Reanalysis Scripts/
│   └── FG_vs_Honest_data_analysis.Rmd          ← all reanalysis code (R Markdown source)
├── Figures/                                    ← all figures from the report
├── Tables/                                     ← all tables from the report
├── Data/
│   └── Prepared_datasets/
│       └── clean_dataset_intermediate.xlsx     ← the dataset used by the .Rmd
└── ...                                         ← original authors' material
```

---

## Data availability

The dataset used in this re-analysis is included in this repository at
[`Data/Prepared_datasets/clean_dataset_intermediate.xlsx`](Data/Prepared_datasets/clean_dataset_intermediate.xlsx)
and is downloaded automatically by the `.Rmd`, so no separate data request is needed to reproduce the
analysis. This data originates from the original authors' study; to request the original anonymized
dataset, contact the original authors at delie.research([AT])gmail.com. See the
[original repository](https://github.com/delieresearch/honest-faking-good-intents-forms-prediction) for
full details on data collection.

---

## Assignment self-check ✅

A quick map from each assignment requirement to where it lives in this repo.

| Requirement | Done | Where to find it |
| --- | :---: | --- |
| **Analysis code** | ✅ | [`Reanalysis Scripts/FG_vs_Honest_data_analysis.Rmd`](Reanalysis%20Scripts/FG_vs_Honest_data_analysis.Rmd) (plus the original authors' code elsewhere in the repo) |
| **Data** (shared) | ✅ | [`Data/Prepared_datasets/clean_dataset_intermediate.xlsx`](Data/Prepared_datasets/clean_dataset_intermediate.xlsx) — included in the repo and pulled automatically by the `.Rmd` |
| **Figures and tables** | ✅ | [`./Figures`](Figures) and [`./Tables`](Tables) — every one is also reproducible from the `.Rmd` |
| **Final report (PDF)** | ✅ | the `.pdf` in the repository **root** |
| **README** (how to run + reproduce) | ✅ | this file |

---

## How to run / reproduce

The `.Rmd` is **self-contained**: it downloads the dataset directly from this repository
([`clean_dataset_intermediate.xlsx`](Data/Prepared_datasets/clean_dataset_intermediate.xlsx)), so you
can knit it on its own without any manual data setup.

1. **Install R** (RStudio is optional but convenient). The analysis was run on:
   ```
   R version 4.4.2 (2024-10-31 ucrt) -- "Pile of Leaves"
   Copyright (C) 2024 The R Foundation for Statistical Computing
   Platform: x86_64-w64-mingw32/x64
   ```
2. **Install the required packages:**
   ```r
   install.packages(c(
     "openxlsx2", "readxl", "dplyr", "knitr",
     "WeightIt", "cobalt", "ggplot2",
     "CBPS", "gbm"   # optional: alternative propensity-score specifications
   ))
   ```
3. **Knit the report** — either click **Knit** in RStudio, or run:
   ```r
   rmarkdown::render("Reanalysis Scripts/FG_vs_Honest_data_analysis.Rmd")
   ```

This reproduces all of the tables and figures listed below.

---

## How to find the code behind any table or figure

**Every table and figure in the PDF can be found inside the `.Rmd`.** To locate the code for any of
them, copy the table or figure **caption/title** from the PDF and use **Ctrl + F** (find) in the
`.Rmd` to jump to the matching code chunk. For example, searching for `Table 8: H2 secondary` or
`Doubly-robust robustness check` takes you straight to the code that produces it.

| Item | What it shows |
| --- | --- |
| Table 4 | Pre-treatment covariate balance |
| Table 5 | Covariate balance before and after IPTW |
| Table 6 | H1 — IPTW-weighted ATE on the social-desirability composite |
| Table 7 | H2 — IPTW-weighted ATEs on the two primary cursor outcomes |
| Table 8 | H2 secondary (exploratory) cursor-feature family |
| Table 9 | Positive responses for the three H3 moderator items and the combined indicator *M* |
| Table 10 | H3 (exploratory) — IPTW-weighted moderation by employment adversity |
| Table 11 | Doubly-robust robustness check |
| Table 12 | Alternative propensity-score specifications |
| Table 13 | Bootstrap inference |
| Figure 3 | Covariate balance before and after IPTW (love plot + propensity-score / IPTW weight distributions) |
| Figure 4 | Propensity score overlap before and after IPTW |

---

## Number formatting in the `.Rmd`

All numbers are rounded to **two decimal places**, with three exceptions:

1. **p-values** — reported with more precision (three decimals), as is standard.
2. **Table 8 (H2 secondary cursor-feature family)** — the original (unrounded) numbers are kept,
   because the features are on very different scales and rounding to two decimals would hide
   meaningful values.
3. **Table 11 (doubly-robust robustness check)** — kept at higher precision so that small differences
   between estimators are not lost.

---

## Note on AI use

In line with the course AI Use Policy, AI assistance (a large language model) was used as a support tool
during this project — for example, to help draft and refine the analysis code, debug R code, and write
and polish this README. All analytic decisions, the choice of methods, the interpretation of results, and
the final report were made and reviewed by the author, who takes full responsibility for the content.

---

## Original repository

For the original authors' code and data, see the
[original repository](https://github.com/delieresearch/honest-faking-good-intents-forms-prediction).