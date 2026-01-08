# Vita Mahjong: App Rating Prediction Project

![Python](https://img.shields.io/badge/language-Python-blue)
![Jupyter Notebook](https://img.shields.io/badge/output-Jupyter%20Notebook-orange)

## Overview
This repository contains an **end-to-end Text Mining project** designed to predict user ratings based on textual reviews. The project was developed as a **mid-exam project for the Text Mining course**. 

The dataset consists of **1,000 English reviews** scraped from the "Vita Mahjong" app on the Google Play Store. This study compares traditional statistical methods (**TF-IDF**) with neural-based embeddings (**Word2Vec**) and addresses real-world challenges like **class imbalance** using SMOTE.

---

## Repository Structure

- `Data/vitamahjong_reviews.csv` → Raw dataset containing user reviews, ratings, and timestamps.
- `Notebook/2702346361_UTS_Text_Mining.ipynb` → Comprehensive Jupyter Notebook including data scraping, EDA, preprocessing, and model evaluation.

---

## Methodology

1. **Data Acquisition**
   - Scraped 1,000 reviews from "Vita Mahjong" using the `google-play-scraper` library.
   - Filtered for English language to ensure linguistic consistency.

2. **Exploratory Data Analysis (EDA)**
   - Analyzed rating distributions and average review lengths.
   - Visualized dominant words per rating using WordClouds to identify common user sentiments.

3. **Text Preprocessing**
   - Performed case folding, symbol/number removal, and tokenization.
   - Applied **Lemmatization** to reduce words to their base forms while maintaining grammatical integrity and part-of-speech tags.

4. **Text Representation**
   - **Method 1 (TF-IDF)**: Captured word importance relative to the document corpus.
   - **Method 2 (Word2Vec)**: Utilized Skip-gram architecture to generate dense vectors based on semantic context.

5. **Modeling & Optimization**
   - Compared **Support Vector Machine (SVM)** and **Random Forest** classifiers.
   - Implemented hyperparameter tuning for each algorithm to obtain optimal results.
   - Applied **SMOTE (Synthetic Minority Over-sampling Technique)** to handle skewed rating distributions and improve performance on minority classes.

---

## Key Insights

| Text Representation | Algorithm | Handling | Accuracy | Weighted F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **TF-IDF** | SVM | Original | 0.72 | 0.69 |
| **TF-IDF** | Random Forest | Original | 0.71 | 0.64 |
| **TF-IDF** | **Random Forest** | **SMOTE + Tuned** | **0.725** | **0.676** |
| **Word2Vec** | SVM | SMOTE + Tuned | 0.545 | 0.60 |
| **Word2Vec** | Random Forest | SMOTE + Tuned | 0.675 | 0.672 |

- **Representation Comparison**: TF-IDF outperformed Word2Vec in this specific dataset, likely due to the vocabulary size of 1,000 samples favoring statistical frequency over deep semantic embeddings.
- **Handling Imbalance**: Implementing SMOTE significantly improved the model's ability to recognize minority classes (low ratings), providing a fairer and more accurate evaluation.
- **Model Selection**: The **Tuned Random Forest with TF-IDF and SMOTE** provided the most robust performance, balancing overall accuracy with critical review categories.

---

## Conclusion
The project demonstrates that for smaller text datasets, **TF-IDF** remains a highly competitive baseline. Furthermore, addressing **data imbalance** is vital; without treatment, models were heavily biased towards majority ratings. This pipeline provides a scalable framework for monitoring user satisfaction and pinpointing areas for app improvement.

---

## Presentation Video
[Vita Mahjong Rating Prediction – Video Presentation](https://drive.google.com/file/d/1T1a993SdSeOkSgvEIdZ8jVZkD76vntEC/view?usp=sharing)

---

## References
- **Python Libraries**: `google-play-scraper`, `NLTK`, `Gensim`, `Scikit-Learn`, `Imbalanced-learn`, `Pandas`.

---

## Author
**Syalista Galuh Nadira**
