# Models

This folder contains the final labeled datasets used in the multi-stage classification framework for SDG 12 public discourse analysis.

The datasets in this folder represent the final annotation outputs for each analytical stage. Each file contains text data that has been assigned labels according to the classification framework used in the study.

## Files Description

| File Name | Stage | Task | Classification Type | Description |
|---|---|---|---|---|
| `Stage 1.xlsx` | Stage 1 | Sustainability Practice Type | Multi-label classification | Contains final labels for sustainability-related issues, such as excessive resource consumption, waste mismanagement, plastic pollution, fossil fuel dependence, and food waste. |
| `Stage 2.xlsx` | Stage 2 | Emotion Traits | Multi-label classification | Contains final labels for emotional traits expressed in sustainability discourse, including hopeful, frustration, skepticism, and concern. |
| `Stage 3.xlsx` | Stage 3 | Responsible Stakeholder | Multi-class classification | Contains final labels for stakeholder attribution, including individuals, governance, corporations, and others. |

---

## Labeling Framework

The final labeled datasets are organized into three analytical stages.

### Stage 1 — Sustainability Practice Type

Stage 1 identifies the sustainability-related issue discussed in each text.

Possible labels include:

- Excessive Resource Consumption
- Waste Mismanagement
- Plastic Pollution
- Fossil Fuel Dependence
- Food Waste

This stage uses a multi-label classification approach, meaning one text may contain more than one sustainability issue.

---

### Stage 2 — Emotion Traits

Stage 2 identifies the emotional traits expressed in the text.

Possible labels include:

- Hopeful
- Frustration
- Skepticism
- Concern

This stage also uses a multi-label classification approach, meaning one text may express more than one emotional trait.

---

### Stage 3 — Responsible Stakeholder

Stage 3 identifies the main stakeholder referenced or attributed responsibility in the text.

Possible labels include:

- Individuals
- Governance
- Corporations
- Others

This stage uses a multi-class classification approach, meaning each text is assigned to one dominant stakeholder category.

---

## Data Usage

The files in this folder are used as the final labeled datasets for:

- BERT fine-tuning,
- model validation,
- classification performance evaluation,
- sustainability discourse analysis,
- issue-emotion-stakeholder interpretation.

These labeled datasets support the study's objective of analyzing how SDG 12-related issues are discussed, emotionally framed, and attributed to different stakeholders in digital public discourse.

---

## Notes

- `Stage 1.xlsx` and `Stage 2.xlsx` contain multi-label annotations.
- `Stage 3.xlsx` contains multi-class annotations.
- These files represent the final label outputs after the annotation and verification process.
- The datasets are provided for academic and research purposes only.
```
