---
layout: post
author: Chong Kang Wey
title: "Applied Data Science Project Documentation"
categories: ITD214
---

# 👕 Analysing Customer Sentiments and Product Categories from Reddit

### 🎯 Business Goal
To optimize the **Kapital fashion brand’s** product offerings, pricing strategies, and customer engagement in order to maximize global sales and strengthen brand loyalty.  

This project leverages **NLP (Natural Language Processing)** and **Machine Learning** on Reddit discussions to uncover customer sentiment and emerging fashion trends, providing **data-driven recommendations** for Kapital’s global strategy.

---

### 📝 Project Background
Understanding consumer opinion in fashion is critical but challenging when data comes from **unstructured, large-scale sources** like Reddit.  

This project automates insights generation by combining:

- **Sentiment Analysis** → measures positive vs. negative attitudes.  
- **Topic Modeling (LDA)** → extracts themes and trends in apparel discussions.  

Together, these methods bridge raw online chatter into actionable insights for business strategy.

---

### 🏗 Work Accomplished
Documenting the work done to accomplish the outcome is crucial for a data science project portfolio.  
This section details the complete workflow, from raw data to final insights. The project followed a **structured data science workflow**, covering data preparation, model training, evaluation, and insights extraction.

---

### 🔧 Workflow

#### 1. Data Preparation
- **Data Acquisition & Merging** → Reddit posts + comments → **44,454 unique entries**.  
- **Cleaning & Preprocessing** → removed duplicates, handled missing values.  
- **Text Normalization** → lowercasing, punctuation removal, stopword filtering.  

#### 2. Modeling
- **Feature Extraction** → TF-IDF Vectorizer.  
- **Model Training** (with GridSearchCV + StratifiedKFold) on 5 ML models:
  - Logistic Regression → 91%
  - Random Forest → 90%
  - XGBoost → 88%
  - LightGBM → 90%
  - Support Vector Machine (SVM) → 92% ✅ (Best)

#### 3. Evaluation
- **Classification Reports & Confusion Matrices** showed high overall accuracy.  
- **Key Issue** → Models predict positive sentiment well, but misclassify many negative reviews → leads to false positives and risks overlooking customer complaints.  

---

### 🧾 Detailed Model Evaluation Summary

| Model | Accuracy | Negative Recall | Positive Recall |
|-------|---------|----------------|----------------|
| Logistic Regression | 91% | 0.70 | 0.97 |
| SVM (Best) | 92% | 0.69 | 0.98 |
| Random Forest | 90% | 0.61 | 0.97 |
| XGBoost | 88% | 0.49 | 0.98 |
| LightGBM | 90% | 0.58 | 0.98 |

**Key Findings:**  
- All models achieve high accuracy (≥88%).  
- **Bias toward positive sentiment** → high recall for positive, weaker for negative.  
- **Critical issue:** False positives → negative reviews misclassified as positive.  
- **Recommendation:** Deploy SVM with fine-tuning, consider data rebalancing for negative class.

---

### 🔎 Topic-Sentiment Insights Methodology
- **Runs LDA topic modeling** to group reviews into topics (e.g., clothes, shoes, pants).  
- **Assigns each review a dominant topic** based on LDA results.  
- **Predicts sentiment** of each review using the best-performing ML model.  
- **Aggregates results by topic:**  
  - Calculate **average sentiment score** (positive vs. negative ratio).  
  - Identify **top keywords** that describe each topic.  
- **Business recommendations** derived:
  - Mostly positive → promote & market.  
  - Mostly negative → investigate & improve.  
  - Mixed → opportunity to grow.

---

### 📊 Deeper Topic Analysis & Recommendations

| Topic ID | Keywords | Reviews Analyzed | Positive % | Negative % | Recommendation |
|----------|---------|----------------|------------|------------|----------------|
| 0 | love, outfit, post, cool, fit | 7,505 | 82.7% | 17.3% | Leverage outfit/styling discussions in trend-driven launches and social engagement campaigns. |
| 1 | fit, pants, im, like, bro | 9,528 | 77.4% | 22.6% | Investigate fit issues (pants sizing, body types); update size guides. |
| 2 | like, dont, people, think, clothes | 11,157 | 82.6% | 17.4% | Promote general apparel themes in campaigns; highlight versatility. |
| 3 | like, shoes, im, wear, look | 8,888 | 84.9% | 15.1% | Stress comfort + style in footwear; integrate keywords into marketing. |
| 4 | shirt, shirts, jeans, pants, jacket | 7,376 | 87.1% | 12.9% | Flagship apparel → reinforce premium positioning (denim, jackets). |

**Strategic Insights:**  
- **Strengths:** Topics 0, 2, 3, 4 → consistently high satisfaction (82–87%) validates **premium pricing and quality-driven positioning**.  
- **Weakness:** Topic 1 → only 77% positive, highlighting **fit-related concerns**. Addressing sizing issues can **reduce dissatisfaction by 10–15%**.  
- **Opportunities:** Reinforce craftsmanship, uniqueness, and premium value while resolving fit issues to **boost brand loyalty**.

---

### 🛍️ Product Recommendations
- Prioritize **style-conscious, versatile, high-quality apparel**.  
- Highlight **seasonal collections, limited editions, and vintage pieces**.  
- Introduce **bundle deals** (e.g., shirt + pants) to increase **AOV**.  
- Offer **detailed fit guides and size recommendations** to cut return rates.

### 💰 Pricing Recommendations
- Maintain **premium pricing** for high-demand/exclusive products.  
- Use **value-based bundles** to encourage larger basket sizes.  
- Stay competitive on essentials to safeguard market share.  
- Apply **seasonal promotions** for trend launches.

### 📢 Engagement & Marketing Recommendations
- Encourage **UGC campaigns** (e.g., “Outfit of the Day”).  
- Spotlight **real-life wearability and positive reviews**.  
- Provide **outfit guides & styling tips** across channels.  
- Launch **loyalty programs** to reward repeat customers.  
- Collaborate with **influencers** to highlight comfort + style.

### 🎯 Actionable Takeaway
- Double down on **high-satisfaction apparel** to drive sales.  
- Address **fit-related issues** to reduce churn.  
- Use **social proof and influencer content** to build trust and expand reach.

---

### ⚖️ Ethical Considerations
- **Privacy:** Reddit data is public, anonymize and comply with ToS.  
- **Bias:** Reddit demographics are not representative; sentiment models may misinterpret slang/sarcasm.  
- **Accuracy:** Positive-heavy classification risks overlooking negative reviews.  
- **Transparency:** Advanced models (XGBoost/LightGBM) less interpretable than simpler models.

---

### 📂 Source Code & Data
🔗 [GitHub Repository](https://github.com/kangwey-hash/ITD214_Project_KW)
