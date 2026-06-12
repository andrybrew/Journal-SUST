# Data Folder

This folder contains the source, merged, cleaned, and platform-level analytical datasets used in the study:

> **How People Talk About Sustainability: A Computational Discourse Analysis of Framing and Stakeholder Attribution in SDG 12**

---

## File Description

| File | Description |
|---|---|
| `X.csv` | Source dataset collected from X/Twitter. It contains posts and replies related to SDG 12 and sustainability discourse. |
| `Youtube.csv` | Source dataset collected from YouTube. It contains user comments from videos related to SDG 12 and sustainability issues. |
| `All Data_Merged.csv` | Combined dataset created by merging the X/Twitter and YouTube datasets. This file represents the integrated dataset before final cleaning. |
| `Final Data.xlsx` | Cleaned dataset generated from the merged data and prepared for annotation, classification, and analysis. |
| `Final Data_with_platforms.xlsx` | Final analytical dataset with harmonized platform labels and classification labels. This file is used to reproduce platform-level and cross-stage analyses. |

---

## Data Processing Flow

The data preparation process follows four main stages:

1. Data were collected separately from X/Twitter and YouTube using sustainability- and SDG 12-related keywords.
2. The platform-specific datasets were merged into `All Data_Merged.csv`.
3. The merged dataset was cleaned and preprocessed to remove noise, irrelevant formatting, duplicate or incomplete entries, and non-relevant text.
4. SDG 12 relevance filtering was applied to produce the final analytical corpus.

The final analytical corpus consists of **16,850 SDG 12-relevant texts**, comprising **3,450 texts from X** and **13,400 comments from YouTube**.

| Platform | Number of Texts | Share |
|---|---:|---:|
| X | 3,450 | 20.5% |
| YouTube | 13,400 | 79.5% |
| Total | 16,850 | 100.0% |

---

## Final Data with Platform Labels

`Final Data_with_platforms.xlsx` is the recommended dataset for reproducing the platform-level and cross-stage analyses reported in the manuscript. It contains the final cleaned texts, harmonized platform labels, and corresponding labels from the three classification stages.

Key fields include:

| Field | Description |
|---|---|
| `text` | Cleaned text used in the final analysis. |
| `platform_final` | Harmonized platform identifier: X or YouTube. |
| Stage 1 label columns | Sustainability practice labels, including excessive resource consumption, waste mismanagement, plastic pollution, fossil fuel dependence, and food waste. |
| Stage 2 label columns | Emotion trait labels, including hopeful, frustration, skepticism, and concern. |
| Stage 3 label column | Responsible stakeholder label, including individuals, governance, corporations, or others. |

This file should be used to reproduce:

* Section 4.5 Platform-Level Analysis;
* Section 4.6 Cross-Stage Patterns;
* platform-specific label distributions;
* dominant issue, emotion, and stakeholder patterns by platform.

The harmonized platform label is used only to support platform-level descriptive comparison. It does not change the text content, SDG 12 relevance filtering, annotation definitions, or BERT model training procedure.

---

## Relationship with Final Label Files

The classification labels used in the study are stored separately in the `/Final Label` folder:

| File | Stage | Task |
|---|---|---|
| `Stage 1.xlsx` | Stage 1 | Sustainability Practice Type |
| `Stage 2.xlsx` | Stage 2 | Emotion Traits |
| `Stage 3.xlsx` | Stage 3 | Responsible Stakeholder |

The labels from these files are integrated into `Final Data_with_platforms.xlsx` to support platform-level and cross-stage interpretation.

---

## Recommended Use

For general text-level annotation and classification workflows, use:

```text
Data/Final Data.xlsx
Final Label/Stage 1.xlsx
Final Label/Stage 2.xlsx
Final Label/Stage 3.xlsx
```

For platform-level comparison and cross-stage descriptive analysis, use:

```text
Data/Final Data_with_platforms.xlsx
```

For tracing the broader data preparation flow, use:

```text
Data/X.csv
Data/Youtube.csv
Data/All Data_Merged.csv
Data/Final Data.xlsx
```

---

## Data Provenance Note

This folder separates the data into source, merged, cleaned, and platform-level analytical files to support transparency and reproducibility.

* `X.csv` and `Youtube.csv` document the platform-specific source datasets.
* `All Data_Merged.csv` documents the merged dataset from both sources.
* `Final Data.xlsx` documents the cleaned dataset prepared for annotation and classification.
* `Final Data_with_platforms.xlsx` documents the final analytical corpus with harmonized platform labels for platform-level and cross-stage analysis.

This structure clarifies the data processing flow from platform-specific collection to final labeled data and BERT-based classification.
