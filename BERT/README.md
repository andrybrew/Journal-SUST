# Models

This folder is intentionally kept mostly empty because trained BERT checkpoints are too large to commit directly to GitHub

## Model Overview

This study uses a multi-stage BERT-based classification framework to analyze public discourse on Sustainable Development Goal 12 (SDG 12), focusing on responsible consumption and production. The framework consists of three classification stages:
1. **Stage 1 — Sustainability Practice Type** Identifies sustainability-related issues discussed in the text.
2. **Stage 2 — Emotion Traits** Detects emotional expressions in sustainability discourse.
3. **Stage 3 — Responsible Stakeholder** Identifies the main stakeholder referenced or attributed responsibility in the text. The models are fine-tuned using BERT-based architecture on the annotated SDG 12 discourse dataset.
---

## Classification Stages 
| Stage | Task | Classification Type | Labels | 
|---|---|---|---| 
| Stage 1 | Sustainability Practice Type | Multi-label classification | Excessive Resource Consumption, Waste Mismanagement, Plastic Pollution, Fossil Fuel Dependence, Food Waste | 
| Stage 2 | Emotion Traits | Multi-label classification | Hopeful, Frustration, Skepticism, Concern | 
| Stage 3 | Responsible Stakeholder | Multi-class classification | Individuals, Governance, Corporations, Others | 
---

## Model Availability 
The trained model checkpoints are not included in this repository because of file size limitations. Once the manuscript is accepted, the fine-tuned BERT classifiers will be uploaded to the [Hugging Face Hub](https://huggingface.co/) and linked here. 
| Stage | Model Description | Hugging Face Link | 
|---|---|---| 
| Stage 1 — Sustainability Practice Type | Multi-label BERT classifier for sustainability issue detection | *to be added on acceptance* | 
| Stage 2 — Emotion Traits | Multi-label BERT classifier for emotion trait detection | *to be added on acceptance* | 
| Stage 3 — Responsible Stakeholder | Multi-class BERT classifier for stakeholder attribution | *to be added on acceptance* | 
---

## Loading the Models 
Once the models are published, they can be loaded using the Hugging Face Transformers library: 
```python
from transformers import AutoTokenizer, AutoModelForSequenceClassification

tokenizer = AutoTokenizer.from_pretrained("<your-username>/<model-name>")
model = AutoModelForSequenceClassification.from_pretrained("<your-username>/<model-name>")
