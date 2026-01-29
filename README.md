# Amazon Fashion Reviews – Text Mining Project

## Project Overview
This project applies a full text-analytics workflow to the Amazon Fashion subset of the Amazon Reviews 2023 dataset. The goal was to extract insights from unstructured text to monitor customer satisfaction and detect product issues.

## Data Source
This project uses the **Amazon Fashion** subset of the Amazon Reviews 2023 dataset (McAuley et al.).
* **Source:** [Amazon Reviews 2023 - Amazon Fashion](https://mcauleylab.ucsd.edu/public_datasets/data/amazon_2023/raw/review_categories/Amazon_Fashion.jsonl.gz)
* **Format:** JSONL (Gzip compressed)
* **Note:** The dataset is not included in this repository due to size constraints. You can download it directly from the link above.

**Research Objectives:**
1. Measure similarity between reviews using TF-IDF and Cosine Similarity.
2. Group reviews into meaningful clusters using unsupervised learning (K-Means).
3. Build machine-learning models to classify review sentiment based on star ratings.

## Methods & Approach

### 1. Data Preprocessing
* **Dataset:** Roughly 170,000 reviews after filtering.
* **Cleaning:** Lowercasing, removal of punctuation/digits, and stripping whitespace.
* **Labeling:**
    * `Positive (1)`: 4–5 star ratings.
    * `Negative (0)`: 1–2 star ratings.
    * (3-star reviews were dropped to reduce ambiguity).

### 2. Similarity Analysis
* Used **TF-IDF vectorization** and **Cosine Similarity** on a sample of reviews.
* Generated a heatmap to identify clusters of reviews sharing common vocabulary (e.g., fit, quality, color).

### 3. Clustering (Unsupervised Learning)
* **K-Means Clustering:** Determined optimal clusters using the elbow method.
* **Agglomerative Clustering:** Used for validation.
* **Key Themes Identified:**
    * Comfort and Fit
    * Material Quality
    * Price and Value

### 4. Sentiment Classification (Supervised Learning)
We trained and evaluated five models to predict sentiment (Positive/Negative) from text:
* Naive Bayes
* Support Vector Machine (SVM)
* Decision Tree
* Random Forest
* AdaBoost
* *Bonus:* LSTM Deep Learning model

## Key Results
| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| **SVM** | **92.3%** | **0.92** | **0.92** | **0.92** |
| Random Forest | 91.2% | 0.91 | 0.91 | 0.91 |
| Naive Bayes | 88.9% | 0.89 | 0.89 | 0.87 |
| Decision Tree | 87.3% | 0.87 | 0.87 | 0.87 |
| AdaBoost | 85.3% | 0.85 | 0.85 | 0.82 |

**Conclusion:** SVM achieved the highest performance, demonstrating that models capable of capturing complex decision boundaries perform best on high-dimensional text data.

## Files in this Repository
* `Amazon_Fashion_Reviews.ipynb`: Jupyter Notebook containing the full Python code for data loading, preprocessing, clustering, and modeling.
* `Amazon_fashion_Reviews.pdf`: Full project report detailing the methodology, business implications, and references.
* `Fashion_Review_Data_Mining.pdf`: Full project presentation with infographics.
