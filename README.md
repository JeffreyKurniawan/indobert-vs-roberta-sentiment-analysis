# 📱 IndoBERT vs. RoBERTa: iPhone 17 Sentiment Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep_Learning-red)
![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

**Author:** Jeffrey Kurniawan  
**Institution:** BINUS University  
**Topic:** Natural Language Processing (NLP), Sentiment Analysis, Class Imbalance

## 📖 Overview
This project performs a comparative sentiment analysis on **iPhone 17 YouTube comments** in Indonesia. The goal is to evaluate how well language-specific models (**IndoBERT**) compare to multilingual models (**RoBERTa**) when dealing with **Indonesian slang** and **highly imbalanced data**.

The dataset consists of **4,418 comments** scraped from popular tech reviewers (e.g., GadgetIn), categorized into *Positive*, *Neutral*, and *Negative*.

## 🚩 The Challenge
1.  **Informal Language:** The dataset is filled with slang, sarcasm, and non-standard abbreviations (e.g., "mending rakit PC", "gacor").
2.  **Class Imbalance:** The data is heavily skewed.
    * **Neutral:** ~2,195 comments (Dominant).
    * **Positive:** Only ~404 comments (Minority).

## 🛠️ Methodology
To address these challenges, this research implemented:
* **Models:** Fine-tuned **IndoBERT** (pre-trained on Indonesian) and **RoBERTa** (multilingual).
* **Translation Strategy:** Compared native training (IndoBERT) vs. training on English-translated text (RoBERTa).
* **Cost-Sensitive Learning:** Applied **Class Weighting** to penalize the model more for misclassifying minority classes (Positive sentiments).

## 📊 Key Results (The "Accuracy Trap")
One of the most interesting findings of this research is that **high accuracy does not always mean a better model**.

| Model | Approach | Accuracy | Positive Class Recall | Verdict |
| :--- | :--- | :--- | :--- | :--- |
| **RoBERTa** | Translated Data | **0.77** (Highest) | **0.15** (Very Low) | ❌ Failed to detect happy users due to translation loss. |
| **IndoBERT** | Native + Weighted | ~0.74 | **0.44** (Improved) | ✅ More stable and context-aware. |

> **Insight:** While RoBERTa achieved the highest accuracy, it failed to capture the minority "Positive" class (Recall: 0.15). IndoBERT proved to be more robust for local context, offering a better balance between precision and recall.

## 📂 Dataset
The dataset used in this research is publicly available on Kaggle:
👉 **[4000 Indonesian YouTube Comments Dataset](https://www.kaggle.com/datasets/jeffreykurniawan/4000-indonesian-youtube-comments/data)**.

## 🚀 Tech Stack
* **Language:** Python
* **Frameworks:** PyTorch, Hugging Face Transformers, Scikit-learn
* **Data Processing:** Pandas, NumPy, Sastrawi (for stemming/normalization)
* **Visualization:** Matplotlib, Seaborn, WordCloud

## 🤝 Acknowledgements
This research was conducted as part of the Computer Science curriculum at **BINUS University**, under the supervision of Noviyanti Tri Maretta Sagala, Lili Ayu Wulandhari, and Jeffrey Junior Tedjasulaksana.

---
*Feel free to star ⭐ this repository if you find it useful!*
