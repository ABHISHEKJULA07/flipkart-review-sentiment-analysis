# Sentiment Analysis of Real-time Flipkart Product Reviews

## Objective
The objective of this project is to classify customer reviews from Flipkart as **positive** or **negative** and identify the **key pain points** expressed in negative reviews. By performing sentiment analysis, the project aims to understand customer satisfaction and dissatisfaction related to product quality, durability, and overall experience.

---

## Dataset
The dataset consists of **8,518 real-time customer reviews** for the product  
**“YONEX MAVIS 350 Nylon Shuttle”** collected from Flipkart.

The data was provided by a Data Engineering team and includes the following features:
- Reviewer Name
- Review Title
- Review Text
- Ratings
- Place of Review
- Month
- Up Votes
- Down Votes

⚠️ **Note:** No web scraping was performed. Only the provided dataset was used.

---

## Data Preprocessing

### 1. Text Cleaning
- Converted text to lowercase
- Removed punctuation, numbers, and special characters
- Removed English stopwords using NLTK

### 2. Text Normalization
- Applied **lemmatization** to reduce words to their base form

### 3. Sentiment Labeling
- Ratings ≥ 4 → **Positive (1)**
- Ratings ≤ 2 → **Negative (0)**
- Rating = 3 (Neutral) → Removed from dataset

---

## Text Embedding Techniques
The following techniques were explored to convert text into numerical features:
- Bag of Words (BoW)
- **TF-IDF (used for final model)**
- Word2Vec (experimental)
- BERT (optional / exploratory)

---

## Modeling Approach

### Model Used
- **Logistic Regression** (Baseline and final model)

### Why Logistic Regression?
- Performs well with TF-IDF features
- Interpretable and efficient
- Suitable for large text datasets

---

## Model Evaluation

### Evaluation Metric
- **F1-Score** (Primary metric as specified)

### Results
- **F1-Score:** 0.95
- **Accuracy:** 92%

#### Confusion Matrix Summary
- High recall for positive reviews
- Acceptable performance on negative reviews despite class imbalance

---

## Pain Point Analysis
Negative reviews were analyzed to identify common customer issues.

### Key Pain Points Identified:
1. Poor product quality
2. Lack of durability
3. Damaged products on delivery
4. Dissatisfaction with value for money

WordCloud and frequency analysis were used to extract these insights.

---

## Model Deployment

### Web Application
A **Streamlit / Flask** web application was developed that:
- Accepts user review text as input
- Predicts sentiment (Positive / Negative) in real time
- Uses the trained model and TF-IDF vectorizer

### Deployment Platform
- **AWS EC2**
- Application exposed via public IP and port

---

## Project Workflow
1. Data Loading and Exploratory Data Analysis (EDA)
2. Data Cleaning and Text Normalization
3. Text Embedding using TF-IDF
4. Model Training (Logistic Regression)
5. Model Evaluation using F1-Score
6. Pain Point Analysis on Negative Reviews
7. Web App Development (Flask / Streamlit)
8. Deployment on AWS EC2
9. Testing and Monitoring

---

---

## How to Run Locally

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
streamlit run streamlit_app.py

Conclusion

This project successfully demonstrates an end-to-end sentiment analysis pipeline, from data preprocessing and modeling to deployment. The insights derived from negative reviews can help businesses improve product quality and customer satisfaction.