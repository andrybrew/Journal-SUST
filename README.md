# Journal-SUST: A Multi-Stage BERT Framework for Analyzing SDG 12 Public Discourse

This repository contains the datasets, final labeled data, BERT training notebooks, model documentation, and reproducibility materials for the paper titled:

> **"How People Talk About Sustainability: A Computational Discourse Analysis of Framing and Stakeholder Attribution in SDG 12"**

---

## 📂 Repository Structure

```text
Journal-SUST/
│
├── BERT/
│   ├── Prototype_Multiclass.ipynb
│   ├── Prototype_Multilabel.ipynb
│   └── README.md
│
├── Data/
│   ├── All Data_Merged.csv
│   ├── Final Data.xlsx
│   ├── X.csv
│   ├── Youtube.csv
│   └── README.md
│
├── Final Label/
│   ├── Stage 1.xlsx
│   ├── Stage 2.xlsx
│   ├── Stage 3.xlsx
│   └── README.md
│
├── CITATION.cff
├── .gitignore
├── README.md
└── requirements.txt
````
---

## 📘 Project Overview

This project introduces a multi-stage computational discourse analysis framework to examine how Sustainable Development Goal 12 (SDG 12), especially responsible consumption and production, is discussed in digital public discourse.

The study focuses on three interconnected dimensions of sustainability communication:

* **Sustainability issue visibility**
  Stage 1 identifies sustainability-related practices or issues discussed in the text.

* **Emotional framing**
  Stage 2 identifies emotional traits expressed in sustainability discourse.

* **Stakeholder attribution**
  Stage 3 identifies the main stakeholder referenced or attributed responsibility in the text.

The framework uses a BERT-based text classification approach to analyze how SDG 12-related issues are discussed, emotionally framed, and attributed to different actors in digital public discourse.

---

## 🧩 Analytical Framework

The classification pipeline consists of three stages:

| Stage   | Task                         | Classification Type        | Labels                                                                                                     |
| ------- | ---------------------------- | -------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Stage 1 | Sustainability Practice Type | Multi-label classification | Excessive Resource Consumption, Waste Mismanagement, Plastic Pollution, Fossil Fuel Dependence, Food Waste |
| Stage 2 | Emotion Traits               | Multi-label classification | Hopeful, Frustration, Skepticism, Concern                                                                  |
| Stage 3 | Responsible Stakeholder      | Multi-class classification | Individuals, Governance, Corporations, Others                                                              |

Stage 1 and Stage 2 use a multi-label classification approach because a single text may contain more than one sustainability issue or emotional trait.

Stage 3 uses a multi-class classification approach because each text is assigned to one dominant stakeholder category.

---

## 📁 Dataset

The datasets are available in the `/Data` folder.

| File                  | Description                                                                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `X.csv`               | Source dataset collected from X/Twitter. It contains posts and replies related to SDG 12 and sustainability discourse.                     |
| `Youtube.csv`         | Source dataset collected from YouTube. It contains user comments from videos related to SDG 12 and sustainability issues.                  |
| `All Data_Merged.csv` | Combined dataset created by merging the X/Twitter and YouTube datasets. This file represents the integrated dataset before final cleaning. |
| `Final Data.xlsx`     | Cleaned dataset generated from the merged data and prepared for annotation, classification, and analysis.                                  |

The data preparation process follows four main stages:

1. Data were collected separately from X/Twitter and YouTube.
2. The platform-specific datasets were merged into `All Data_Merged.csv`.
3. The merged dataset was cleaned and preprocessed.
4. The cleaned output was stored in `Final Data.xlsx`.

`All Data_Merged.csv` documents the integrated source dataset, while `Final Data.xlsx` represents the cleaned dataset used for downstream annotation and classification.

---

## 🏷️ Final Label Data

The `/Final Label` folder contains the final labeled datasets used for the three-stage classification framework.

| File           | Stage   | Task                         | Description                                                    |
| -------------- | ------- | ---------------------------- | -------------------------------------------------------------- |
| `Stage 1.xlsx` | Stage 1 | Sustainability Practice Type | Final labels for sustainability-related issues.                |
| `Stage 2.xlsx` | Stage 2 | Emotion Traits               | Final labels for emotional traits in sustainability discourse. |
| `Stage 3.xlsx` | Stage 3 | Responsible Stakeholder      | Final labels for stakeholder attribution.                      |

These labeled datasets are used for:

* BERT fine-tuning,
* model validation,
* classification performance evaluation,
* sustainability discourse analysis,
* issue-emotion-stakeholder interpretation.

---

## 🤖 BERT Notebooks

The `/BERT` folder contains the main BERT prototype notebooks used for classification modeling.

| Notebook                     | Purpose                                        | Classification Type        |
| ---------------------------- | ---------------------------------------------- | -------------------------- |
| `Prototype_Multilabel.ipynb` | Fine-tuning BERT for Stage 1 and Stage 2 tasks | Multi-label classification |
| `Prototype_Multiclass.ipynb` | Fine-tuning BERT for Stage 3 task              | Multi-class classification |

The multi-label notebook is used for tasks where a single text may contain more than one label, such as sustainability practice type and emotion traits.

The multi-class notebook is used for stakeholder attribution, where each text is assigned to one dominant stakeholder category.

---

## 🧠 Model Framework

This study uses BERT-based text classification models to analyze public discourse on SDG 12.

The model tasks include:

| Stage   | Model Task                  | Output                         |
| ------- | --------------------------- | ------------------------------ |
| Stage 1 | Multi-label BERT classifier | Sustainability practice labels |
| Stage 2 | Multi-label BERT classifier | Emotion trait labels           |
| Stage 3 | Multi-class BERT classifier | Responsible stakeholder label  |

Trained model checkpoints are not stored directly in this repository because of file size limitations.

Once the manuscript is accepted, the fine-tuned BERT classifiers may be uploaded to the Hugging Face Hub and linked in the repository documentation.

---

## 🔁 Reproducibility

This repository provides the dataset structure, final labeled data, BERT prototype notebooks, and documentation needed to reproduce the classification pipeline.

The general workflow is:

1. Load the cleaned dataset from `/Data/Final Data.xlsx`.
2. Use the labeled files from `/Final Label`.
3. Tokenize the text using a BERT tokenizer.
4. Fine-tune BERT using the appropriate prototype notebook.
5. Evaluate model performance using precision, recall, and F1-score.
6. Use the predicted labels for discourse interpretation.

To install dependencies and run locally:

```bash
git clone https://github.com/rrbelliana-hub/Journal-SUST.git
cd Journal-SUST
python -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

---

## 📊 Expected Outputs

The framework produces three types of classification outputs.

| Stage   | Output Type                   | Example Output                         |
| ------- | ----------------------------- | -------------------------------------- |
| Stage 1 | Sustainability issue labels   | Plastic Pollution, Waste Mismanagement |
| Stage 2 | Emotion trait labels          | Concern, Frustration                   |
| Stage 3 | Responsible stakeholder label | Governance                             |

Example:

| Text                                                                               | Stage 1 Output                         | Stage 2 Output       | Stage 3 Output |
| ---------------------------------------------------------------------------------- | -------------------------------------- | -------------------- | -------------- |
| "Plastic waste is everywhere and the government should do something about it."     | Plastic Pollution, Waste Mismanagement | Concern, Frustration | Governance     |
| "People should reduce food waste and start composting at home."                    | Food Waste, Waste Mismanagement        | Hopeful              | Individuals    |
| "Companies keep promoting sustainability, but most of it feels like greenwashing." | Excessive Resource Consumption         | Skepticism           | Corporations   |

These outputs are used to examine how SDG 12-related issues are discussed, emotionally framed, and attributed to different stakeholders in digital public discourse.

---

## 📝 Data Provenance Note

The repository separates the data into source, merged, cleaned, and labeled files to support transparency and reproducibility.

* `X.csv` and `Youtube.csv` document the platform-specific source datasets.
* `All Data_Merged.csv` documents the merged dataset from both sources.
* `Final Data.xlsx` documents the cleaned dataset prepared for analysis.
* The files in `/Final Label` document the final annotated labels used in the classification stages.
* The notebooks in `/BERT` document the model training workflow.

This structure clarifies the data processing flow from platform-specific collection to final labeled data and BERT-based classification.

---

## 🔗 Links

* 📄 **Paper:** On publication process
* 📁 **GitHub Repository:** https://github.com/rrbelliana-hub/Journal-SUST

---

## ⚖️ License

* **Code and documentation:** [MIT License](LICENSE)
* **Annotated data:** Provided for academic and research purposes only

---

## 📬 Contact

For questions about the repository, datasets, or model documentation, please open a GitHub issue or contact the corresponding author indicated in the manuscript.

---

## 🙏 Acknowledgements

We acknowledge the developers of [Hugging Face Transformers](https://github.com/huggingface/transformers), which supports the BERT-based classification framework used in this study.

```
```
