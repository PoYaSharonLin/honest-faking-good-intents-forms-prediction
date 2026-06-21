# What People Say And How They Move: A Causal Reanalysis of Cursor-Based Faking-Good Detection in Online Personality Questionnaires

## About

**Note on this fork.** This is a fork of the original authors' repository. In addition to the original
material, it adds a **[Reanalysis](#a-reanalysis)** folder that contains a causal re-analysis (IPTW /
doubly-robust estimation) of the original authors' data, written as an R Markdown (`.Rmd`) file. See the [Reanalysis](#a-reanalysis) section for how to read it. The final report is in the root directory as PDF file.



## <a name="a-reanalysis"> Reanalysis

This fork adds a causal re-analysis of the original authors' data. It compares the **Faking-Good (FG)**
and **Honest (H)** groups using inverse-probability-of-treatment weighting (IPTW) and doubly-robust
estimators. The analysis lives in the [`Reanalysis Scripts`](Reanalysis%20Scripts) folder:

- **[`FG_vs_Honest_data_analysis.Rmd`](Reanalysis%20Scripts/FG_vs_Honest_data_analysis.Rmd)** — the R Markdown source with all of the analysis code.

The `.Rmd` downloads the data directly from this repository
([`Data/Prepared_datasets/clean_dataset_intermediate.xlsx`](Data/Prepared_datasets/clean_dataset_intermediate.xlsx)),
so it can be knitted on its own. It requires R with the following packages: `openxlsx2`, `readxl`,
`dplyr`, `knitr`, `WeightIt`, `cobalt`, and `ggplot2` (plus `CBPS` and `gbm` for the optional
alternative propensity-score specifications).

### How to find the code behind any table or figure in the PDF

**Every table and figure in the PDF can be found inside the `.Rmd` file.** To locate the code for any
of them, copy the table or figure **caption/title** from the PDF and use **Ctrl + F** (find) in the
`.Rmd` to jump to the matching code chunk. For example, searching for `Table 8: H2 secondary` or
`Doubly-robust robustness check` will take you straight to the code that produces it.

The PDF contains these tables and figures (all are reproducible from the `.Rmd`):

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

### Number formatting in the `.Rmd`

In the `.Rmd`, **all numbers are rounded to two decimal places**, with three exceptions:

1. **p-values** — reported with more precision (three decimals) as is standard.
2. **Table 8 (H2 secondary cursor-feature family)** — the original (unrounded) numbers are kept, because
   the features are on very different scales and rounding to two decimals would hide meaningful values.
3. **The robustness check (doubly-robust comparison, Table 11)** — kept at higher precision so that small
   differences between estimators are not lost.

---
## Original  README


### Table of Contents
* [Paper Citation](#a-citation)
* [Datasets](#a-datasets)
* [Questionnaire Preview](#a-questionnaire)
* [Scripts](#a-scripts)
* [Reanalysis](#a-reanalysis)
* [Authors](#a-authors)
* [Licence](#a-licence)

## <a name="a-citation"> Paper Citation
```bibtex
@Article{Kuric2025,
  title={User modeling for detecting faking-good intent in online personality questionnaires in the wild based on mouse dynamics},
  author={Kuric, Eduard and Demcak, Peter and Smrecek, Peter and Spilakova, Beata},
  journal={Multimedia Tools and Applications},
  year={2025},
  month={Apr},
  day={28},
  issn={1573-7721},
  doi={10.1007/s11042-025-20852-9},
  url={https://doi.org/10.1007/s11042-025-20852-9}
}
```

## <a name="a-datasets"> Dataset
In this study, we created a dataset that contains information on user behavior during completion of the Big Five personality questionnaire. To collect data in two groups, Honest (H) and Faking-good (FG) (a.k.a. lying in the context of a personality questionnaire), one half of participants was instructed to present themselves in the questionnaire as better than they actually are, with lying being explicitly encouraged. The other half was asked to fill in the questionnaire truthfully. The dataset has two original sources of information. [Limesurvey](https://www.limesurvey.org/) provided completed questionnaire data. [UXtweak](https://www.uxtweak.com/) provided information about the user's low-level interactions with the questionnaire (mouse dynamics). The data was then cleaned, preprocessed, and formatted into a structure that is suitable for machine learning. The dataset contains pageview records, with each row representing metrics for a single pageview - [Dataset one-pageview-per-one-row](Data/Prepared_datasets/dataset_one_pv_per_one_row.json).
  
### <a name="a-dataset-access"> Dataset Access  

To access the original anonymized dataset, please contact the authors at delie.research([AT])gmail.com.

## <a name="a-questionnaire"> Questionnaire Preview

Betweem the Honest and Faking-good groups, we used 2 variants of the same questionnaire with different instruction. Participants were required to use a physical computer mouse during the questionnaire completion.

<table>
  <tr>
    <td align="center"><img src="Questionnaire/Preview/Mouse alert.jpg">Mouse</td>
    <td align="center"><img src="Questionnaire/Preview/Faking Good Question.jpg">Faking Good</td>
    <td align="center"><img src="Questionnaire/Preview/Honest Question.jpg">Honest</td>
  </tr>
</table>

Previews of the study that allow for viewing the experiment from the perspective of the participants (without any data being collected) are found below. For convenience, we include links for previews with random assignment to questionnaire instruction variants (variants corresponding to the Honest and Faking-good groups that participants are randomly assigned into), as well as direct links to specific questionnaire instruction variants.

Random group assignment study previews:
  - [Study preview - English translation](https://study.uxtweak.com/webusability/duWYfMNUeZSL4odlpZJDa)
  - [Study preview - Original Slovak version used during the experiment](https://study.uxtweak.com/webusability/1gy7SMSugUNnLJtWKtJ0L)

Direct study previews to specific group variants:
  - [Faking-good group study preview - English translation](https://delie.limesurvey.net/628192?lang=en)
  - [Honest group study preview - English translation](https://delie.limesurvey.net/778728?lang=en)
  - [Faking-good  group study preview - Original Slovak version](https://delie.limesurvey.net/919549?lang=sk)
  - [Honest group study preview - Original Slovak version](https://delie.limesurvey.net/192868?lang=sk)

Questionnaire files that can be imported into [Limesurvey](https://www.limesurvey.org/):
  - [Faking-good group questionnaire files - English translation](Questionnaire/Files/fg_en.lss)
  - [Honest group questionnaire files - English translation](Questionnaire/Files/h_en.lss)
  - [Faking-good group questionnaire files - Original Slovak version](Questionnaire/Files/fg_sk.lss)
  - [Honest group questionnaire files - Original Slovak version](Questionnaire/Files/h_sk.lss)

## <a name="a-scripts"> Scripts
The scripts for this project are all written in Python (version 3.10.7), with the aid of libraries obtained through pip (version 22.2.2). They were run on Jupyter notebooks. A detailed list of dependencies can be found in the [requirements file](Scripts/requirements.txt). We recommend using a [virtual environment](https://docs.python.org/3/library/venv.html) to install the necessary components and start the notebooks.

The scripts are intended to be run in the order in which they are numbered. This repository contains all the data needed to run scripts from 05 to 09. To access the rest of the data, follow the instructions in the [Dataset Access](#a-dataset-access) section.

#### [1 - Pairing pageviews with coresponding question](Scripts/01_Pageviews_pairing_v0.ipynb)

Script for pairing pageviews with Big Five questions. The function loads session data and extracts the text of the questions displayed on each pageview. This text is compared to the Big Five questions, and if a match is found, the pageview is marked with the corresponding page number. The resulting pairs are saved.

#### [2 - Extraction of mouse events](Scripts/02_Events_preparing_script_v0.ipynb)

Script for extracting important data from sessions JSON. For every pageview of session, *move, scroll, click and input* information is extracted and saved. This script creates new dataset containing only necessary information.

#### [3 - Calculation of movement metrics](Scripts/03_Sessions_metrics_calculator_v0.ipynb)

Script for calculation of all metrics of mouse movements based on extracted events. All attributes of the proposed user model that are also used as features in machine learning algorithms are metrics calculated by this script.

#### [4 - Combining dataset of movement metrics with questionnaire responses](Scripts/04_Merge_tables_v0.ipynb)

Combining information about sessions with calculated metrics with information about filled-in forms with Big Five questionnaire responses.

#### [5 - Data exploration and cleaning](Scripts/05_Data_exploration_and_cleaning_v0.ipynb)

Simple explorative analysis, proof of concept based on simple statistical test over means of metrics. This script drops unusable pageviews from sessions.

#### [6 - Data preprocessing and transformations](Scripts/06_Data_Preprocessing_v0.ipynb)

Transformation of **1 row = 1 session** dataframe to **1 row = 1 pageview** dataframe. This script creates the dataset suitable for machine learning.

#### [7 - Model training and evaluation](Scripts/07_Model_training_and_evaluation_v0.ipynb)

Script contains explorative analysis of the dataset, feature selection, model selection, cross validation, model evaluation based on pageview classification and also based on session classification. This script generates reports with metrics of machine learning.

#### [8 - Hyperparameter tuning for Gradient Boosting](Scripts/08_Hyperparameter_GB_v0.ipynb)

Script for search of hyperparameters for Gradient Boosting.

#### [9 - Hyperparameter tuning for Logistic Regression](Scripts/09_Hyperparameter_LR_v0.ipynb)

Script for search of hyperparameters for Logistic Regression.



## <a name="a-authors"> Authors
  
### Eduard Kuric
He is a researcher and lecturer at [Faculty of Informatics and Information Technologies](https://www.fiit.stuba.sk/), [Slovak University of Technology in Bratislava](https://www.stuba.sk/). He is also a founder of [UXtweak](https://www.uxtweak.com). His research interests include human-computer interaction, user modeling, and machine learning.
- Email: eduard.kuric([AT])stuba.sk
- [LinkedIn](https://www.linkedin.com/in/eduard-kuric-b7141280/)
- [Google Scholar](https://scholar.google.com/citations?user=MwjpNoAAAAAJ&hl=en&oi=ao)

### Peter Demcak
He is a researcher at [UXtweak](https://www.uxtweak.com/). His current research topics of interest involve user behavior, UX research methods and design practices, and machine learning.
- Email: peter.demcak([AT])uxtweak.com

### Peter Smrecek
He is a Machine Learning Engineer and Computer Science student at [Faculty of Informatics and Information Technologies](https://www.fiit.stuba.sk/), [Slovak University of Technology in Bratislava](https://www.stuba.sk/). He is focusing on development and operations in field of Data Science. 
- [LinkedIn](https://www.linkedin.com/in/peter-smrecek/)
- Email: petersmrecek([AT])gmail.com

### Beata Spilakova
She is a researcher at [UXtweak](https://www.uxtweak.com/). Her research topics of interest involve user behavior, cognitive ergonomics, UX research methods, and design practices.
- [LinkedIn](https://www.linkedin.com/in/beataspilakova/)
- Email: beata.spilakova([AT])uxtweak.com

### General contact
- Email: delie.research([AT])gmail.com

## <a name="a-licence"> Licence

This work is licensed under a
<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">
Creative Commons Attribution-NonCommercial 4.0 International License.
</a>

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/" style="margin-left: 8rem">
<img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" />
</a>
