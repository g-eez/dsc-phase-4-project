
# Tweet Sentiment Analysis Project

---

## 📌 Project Overview

This project applies **Natural Language Processing (NLP)** to classify sentiment in over **9,000 tweets** about Apple and Google products. Each tweet is labeled as *positive, negative, or neutral*.  

The aim is to build a reliable sentiment classifier that can help **Apple and Google’s marketing and product teams** track public perception, identify trends, and improve engagement strategies.  

### 🎯 Objectives
1. **Sentiment Classification**: Develop models to classify tweets as *positive, negative, or neutral*.  
2. **Performance Optimization**: Evaluate both **binary (positive vs. negative)** and **multiclass (positive, negative, neutral)** tasks.  

Ultimately, these models can be deployed to provide **actionable insights** for stakeholders by monitoring social media sentiment in real time.

---

## 💼 Business Understanding

- **Stakeholders**: Apple and Google’s **marketing** and **product development** teams.  
- **Business Need**: These teams want to understand consumer attitudes on social media to guide **product improvements**, **marketing campaigns**, and **customer engagement**.  
- **Problem Statement**: A generalized sentiment model is needed to quickly determine whether public conversations about Apple and Google products are positive, negative, or neutral, enabling **faster response** to consumer trends and opinions.  

---

## 📊 Data Understanding

- **Source**: Dataset from [CrowdFlower](https://data.world/crowdflower/brands-and-product-emotions) via data.world.  
- **Size**: ~9,093 tweets related to Apple and Google products.  
- **Labels**: Each tweet annotated as *positive, negative, or neutral*.  

➡️ The dataset is suitable because it contains a **diverse, real-world set of consumer opinions**. Its multi-class labels support both **binary** and **multiclass** modeling approaches.

---

## 🔎 Data Exploration & Preparation

- **Initial Structure**: 9,093 rows, three main columns (`tweet_text`, `emotion_in_tweet_is_directed_at`, and `sentiment`).  
- **Cleaning**:
  - Dropped 5,802 missing values in `emotion_in_tweet_is_directed_at`.  
  - Removed one row missing `tweet_text`.  
- **Class Balance**: Sentiment distribution was **imbalanced**, requiring class-balancing techniques (e.g., **SMOTE**).  
- **Preprocessing**:
  - Lowercasing text  
  - Removing punctuation  
  - Tokenizing  
  - Stopword removal  
  - Lemmatization  

Data was split **80/20 (train/test)** and transformed using **TF-IDF vectorization**.  

![sentiment_tweetlength](images/sentiment_tweetlength.png)

---

## 🤖 Modeling

### 🔹 Binary Classification
Tested models: **Logistic Regression**, **Random Forest**, and **SVM**.  

- **Best Model**: Logistic Regression  
- **Accuracy**: 88%  
- **Strength**: Balanced performance, particularly effective at detecting *negative sentiments*.  
- **Note**: Although SVM had slightly higher accuracy (89%), it underperformed in recall and F1 for negative tweets.  

![binary_log](images/binary_log.png)

---

### 🔹 Multiclass Classification
Tested models: **Multinomial Naive Bayes** and an **Ensemble (Naive Bayes + Random Forest)**.  

- **Best Model**: Ensemble Model  
- **Accuracy**: 68% (vs. 61% for Naive Bayes)  
- **Strength**: Better at detecting *neutral* and *negative* sentiments, leading to more balanced results.  

![multiclass_ensemble](images/multiclass_ensemble.png)

---

## 📏 Evaluation Metrics

We assessed models using:  

- **Accuracy** – overall correctness  
- **Precision** – proportion of correct positive predictions  
- **Recall** – ability to capture all relevant cases  
- **F1-Score** – harmonic mean of precision and recall  

➡️ **F1-score** is the most important metric here due to **class imbalance**, ensuring the model performs consistently across all sentiment categories.

---

## ✅ Conclusion

- **Binary Classification**: Logistic Regression performed best (88% accuracy), especially strong at detecting negative sentiment.  
- **Multiclass Classification**: The Ensemble model achieved the best results (68% accuracy), offering more balanced performance across sentiment categories.  

These models provide valuable tools for monitoring consumer sentiment and informing **marketing and product strategies**.

---

## 📌 Recommendations

- Improve **negative sentiment detection** using advanced models (e.g., **BERT**, phrase extraction).  
- Mitigate **class imbalance** by collecting more diverse data.  
- Enhance preprocessing (e.g., **negation handling**, domain-specific terms).  
- Continuously **monitor and retrain** models to keep up with evolving consumer language.  


