# Models

This folder contains the datasets used for the SDG 12 public discourse analysis. The data were collected from two digital platforms, X and YouTube, and were processed through merging and cleaning stages before being used for further analysis.

## Where the fine-tuned models will live

Once the manuscript is accepted, the fine-tuned BERT classifiers will be uploaded to the [Hugging Face Hub](https://huggingface.co/) and linked from here.

| File | Description |   
|---|---|
| All Data Merged.csv | Combined dataset created by merging the X/Twitter and YouTube datasets. This file represents the full merged dataset before final cleaning and preparation. | 
| Final Data.xlsx | Cleaned dataset generated from the merged data. This file contains the processed text data used for annotation, classification, and subsequent analysis. | 
| X.csv | Source dataset collected from X. It contains posts and replies related to SDG 12, sustainability practices, emotional expressions, and stakeholder-related discourse. | 
| Youtube.csv | Source dataset collected from Youtube. It contains user comments from videos related to SDG 12, sustainability practices, emotional expressions, and stakeholder-related discourse. | 

## Data Preparation Workflow

The dataset was prepared through the following workflow:

1. **Data Collection**  
   Data were collected separately from X and YouTube. X data consist of posts and replies, while YouTube data consist of user comments.

2. **Data Integration**  
   The platform-specific datasets were merged into `All Data_Merged.csv`. This file serves as the integrated dataset containing all collected texts from both platforms.

3. **Cleaning and Preprocessing**  
   The merged dataset was cleaned to remove noise and prepare the text for analysis. The cleaning process included text normalization, removal of unnecessary characters, duplicate handling, and preparation of the corpus for annotation and classification.

4. **Final Analytical Dataset**  
   The cleaned output is stored in `Final Data.xlsx`. This file represents the final cleaned dataset used in the analytical stages of the study.

## Reproducibility Note

The separation between source files, merged data, and final cleaned data is maintained to support transparency and reproducibility. `Twitter.csv` and `Youtube.csv` show the original platform-specific sources, `All Data_Merged.csv` shows the combined dataset, and `Final Data.xlsx` shows the cleaned dataset used for further computational analysis.

## Ethical Use

The datasets are provided for academic research purposes only. All analyses are conducted at an aggregate level, and the data should not be used to identify or target individual users.
