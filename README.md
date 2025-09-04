
# Twitter Sentiment Analysis

## 📌 Project Overview

This project focuses on **analyzing consumer sentiment toward Apple and Google products** using data sourced from Twitter. Social media provides a rich source of real-time, user-generated opinions that organizations can leverage for:

* **Brand reputation management**
* **Product development insights**
* **Competitive benchmarking**

The study demonstrates how Natural Language Processing (NLP) and Machine Learning can transform noisy, short-text data into structured sentiment predictions.

---

## 🎯 Business Understanding

The business objective is to classify tweets into sentiment categories to gauge public perception of Apple and Google products.
The dataset consists of **9,093 tweets**, each containing:

* `tweet_text`: the raw tweet content.
* `emotion_in_tweet_is_directed_at`: the specific brand/product mentioned (often missing).
* `is_there_an_emotion_directed_at_a_brand_or_product`: the sentiment label (*Positive*, *Negative*, *No emotion*).

A challenge in this dataset is **class imbalance**, where many tweets contain *no emotion* toward the brand, reflecting real-world conditions.

---

## 🛠️ Data Preparation

Twitter text is inherently noisy, so several preprocessing steps were applied:

* **Tokenization** using `nltk.TweetTokenizer` to handle hashtags, mentions, and emoticons.
* **Lemmatization** with `WordNetLemmatizer` for normalization (e.g., *running → run*).
* **Stopword handling**: standard stopwords removed, but **negations preserved** (e.g., *not*, *no*).
* **Contractions expanded** (*can’t → can not*).
* **Noise removal**: URLs, digit strings, and elongated characters reduced.

This ensures that tweets are represented in a structured, sentiment-preserving format.

---

## 📊 Modeling Approach

The sentiment analysis was conducted in **two phases**:

### Phase 1 – Binary Classification

* Focused only on **Positive** vs. **Negative** sentiment.
* Models tested:

  * Logistic Regression
  * Support Vector Machines (SVM)
* This setup reduces complexity and establishes a performance baseline.

### Phase 2 – Multi-Class Classification

* Expanded to include **No emotion** category.
* This mirrors the real-world distribution of social media sentiment.
* Class imbalance was addressed using sampling strategies and evaluation metrics.

---

## 📈 Results

Key findings from model evaluations:

* **Logistic Regression** performed strongly on binary classification, achieving balanced precision and recall between Positive and Negative tweets.
* **SVM** demonstrated robustness but required careful parameter tuning.
* **Multi-class classification** showed reduced accuracy due to the dominance of “No emotion” tweets. However, targeted strategies improved recall for minority classes.

The models successfully validated that machine learning can capture sentiment signals in noisy Twitter data, though future improvements are needed for imbalanced, multi-class tasks.

---

## 📦 Technologies Used

* **Python 3.x**
* **Libraries**:

  * `nltk` (text preprocessing)
  * `scikit-learn` (machine learning models & evaluation)
  * `pandas`, `numpy` (data handling)
  * `matplotlib` (visualizations)

---

## 👤 Authors

* **George Kariuki**
* **Debborah Omondi**
* **Mohamed Sheikh**


