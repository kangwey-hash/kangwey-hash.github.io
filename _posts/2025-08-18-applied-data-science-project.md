# 👕 Analysing Customer Sentiments and Product Categories from Reddit

## 🎯 Business Goal
To optimize the Kapital fashion brand’s product offerings, pricing strategies, and customer engagement in order to maximize global sales and strengthen brand loyalty.

This project leverages **NLP (Natural Language Processing)** and **Machine Learning** on Reddit discussions to uncover customer sentiment and emerging fashion trends, providing data-driven recommendations for Kapital’s global strategy.

---

## 📝 Project Background
Understanding consumer opinion in fashion is critical but challenging when data comes from unstructured, large-scale sources like Reddit.

This project automates insights generation by combining:

- **Sentiment Analysis** → measure positive vs. negative attitudes.  
- **Topic Modeling (LDA)** → extract themes and trends in apparel discussions.  

Together, these methods help bridge raw online chatter into actionable insights for business strategy.

---

## 📌 Work Accomplished
Documenting the work done to accomplish the outcome is crucial for a data science project portfolio. This section details the complete workflow, from the raw data to the final insights. The project followed a structured data science workflow, from **data preparation** to **model evaluation**.

---

## 🔧 Workflow
1. **Data Preparation**
   - Data Acquisition & Merging → Reddit posts + comments → 44,454 unique entries.  
   - Cleaning & Preprocessing → removed duplicates, handled missing values.  
   - Text Normalization → lowercasing, punctuation removal, stopword filtering.  

2. **Modeling**
   - Feature Extraction → TF-IDF Vectorizer.  
   - Model Training (with GridSearchCV + StratifiedKFold) on 5 ML models:  
     - Logistic Regression → **91%**  
     - Random Forest → **90%**  
     - XGBoost → **88%**  
     - LightGBM → **90%**  
     - Support Vector Machine (SVM) → **92% (Best) ✅**  

3. **Evaluation**
   - Classification Reports + Confusion Matrices showed high overall accuracy.  
   - **Key Issue → Models predict positive sentiment well, but misclassify many negative reviews** → leads to false positives and risks overlooking customer complaints.  

---

## 🧾 Detailed Model Evaluation Summary

### ✅ Models Trained & Tuned
- Logistic Regression  
- Support Vector Machine (SVM)  
- Random Forest  
- XGBoost  
- LightGBM  

### 📊 Performance Overview
- Accuracy range: **88% – 92%**  
- Strong at detecting positive sentiment (Recall ≈ **0.97–0.98**)  
- Weaker at detecting negative sentiment (Recall ≈ **0.49–0.70**)  
- **Best model: SVM (Accuracy = 92%)**  

---

### 📌 Detailed Metrics (Test Data)

**Logistic Regression**  
- Accuracy: 91%  
- Negative recall: 0.70  
- Positive recall: 0.97  
- Confusion Matrix: `[[904, 380], [167, 4764]]`  

**SVM (Best)**  
- Accuracy: 92%  
- Negative recall: 0.69  
- Positive recall: 0.98  
- Confusion Matrix: `[[881, 403], [122, 4809]]`  

**Random Forest**  
- Accuracy: 90%  
- Negative recall: 0.61  
- Positive recall: 0.97  
- Confusion Matrix: `[[787, 497], [128, 4803]]`  

**XGBoost**  
- Accuracy: 88%  
- Negative recall: 0.49  
- Positive recall: 0.98  
- Confusion Matrix: `[[624, 660], [80, 4851]]`  

**LightGBM**  
- Accuracy: 90%  
- Negative recall: 0.58  
- Positive recall: 0.98  
- Confusion Matrix: `[[748, 536], [94, 4837]]`  

---

## 🔑 Key Findings
- All models achieve high accuracy (≥88%).  
- **Bias toward positive class** → High recall for positive, weaker for negative.  
- **Critical issue: False positives** → negative reviews mistaken as positive.  
- **SVM recommended**: Best balance between precision, recall, and accuracy.  

---

## 🎯 Business Implications
- **Risk**: Missing negative sentiment may hide customer pain points.  
- **Action**: Improve negative class detection (e.g., rebalancing, data augmentation).  
- **Deployment choice**: SVM with additional fine-tuning.  

---
### 📊 Topic-Sentiment Insights Methodology
- **Runs LDA topic modeling** to group reviews into topics (e.g., clothes, shoes, pants).  
- **Assigns each review a dominant topic** based on LDA results.  
- **Predicts sentiment** of each review using the best-performing ML model (Logistic Regression, SVM, Random Forest, XGBoost, or LightGBM).  
- **Aggregates results by topic:**  
  - Calculate **average sentiment score** (positive vs. negative ratio).  
  - Identify **top keywords** that describe each topic.  
- These aggregated insights inform **business actions** like marketing campaigns, product adjustments, or promotional strategies.  

## 📊 Topic-Sentiment Insights

| Topic ID | Top Keywords                        | Positive Ratio | Negative Ratio | Key Insight |
|----------|-------------------------------------|----------------|----------------|-------------|
| 4        | shirt, shirts, jeans, pants         | 0.74           | 0.26           | 🟢 High satisfaction → validates premium pricing |
| 3        | like, shoes, wear, look             | 0.69           | 0.31           | 🟢 Strong reception → integrate into brand engagement |
| 0        | love, outfit, post, cool, fit       | 0.65           | 0.35           | 🟢 Style trends → align with future product strategy |
| 2        | like, dont, people, think, clothes  | 0.65           | 0.35           | 🟢 Broad apparel sentiment → useful for marketing |
| 1        | fit, pants, im, like, bro           | 0.54           | 0.46           | ⚠️ Mixed satisfaction → investigate sizing/fit issues |

---

### 🔎 Deeper Topic Analysis Overview
- **Group reviews by dominant topic** using LDA.  
- **For each topic:**
  - Calculate **sentiment distribution** (e.g., 82% positive, 18% negative).  
  - Extract **sample reviews** (real text snippets).  
  - Identify **keywords** from LDA.  
- **Business recommendations based on sentiment:**
  - Mostly positive → **promote & market**.  
  - Mostly negative → **investigate & improve**.  
  - Mixed → **opportunity to grow and optimize**.  

## 🔎 Deeper Topic Analysis & Recommendations

| Topic ID | Keywords | Reviews Analyzed | Positive % | Negative % | Recommendation |
|----------|----------|-----------------|------------|------------|----------------|
| 0 | love outfit post cool fit | 7,505 | 82.7% | 17.3% | Leverage outfit/styling discussions in trend-driven launches and social engagement. |
| 1 | fit pants im like bro | 9,528 | 77.4% | 22.6% | Investigate fit issues (pants sizing, body types); update size guides. |
| 2 | like dont people think clothes | 11,157 | 82.6% | 17.4% | Promote general apparel themes in campaigns; highlight versatility. |
| 3 | like shoes im wear look | 8,888 | 84.9% | 15.1% | Stress comfort + style in footwear; integrate keywords into marketing. |
| 4 | shirt shirts jeans pants jacket | 7,376 | 87.1% | 12.9% | Flagship apparel → reinforce premium positioning (denim, jackets). |

---

## 📌 Strategic Insights
- **Strengths** (Topics 0, 2, 3, 4): High satisfaction (82−87%) in core apparel categories → validates Kapital’s premium pricing and quality-driven positioning.  
- **Weakness** (Topic 1 – Fit & Pants): Only 77% positive. Fit-related complaints are critical signals → addressing sizing issues can reduce dissatisfaction by 10−15%.  
- **Opportunities**: Kapital can reinforce its craftsmanship, uniqueness, and premium value while addressing fit issues to further boost brand loyalty.  

---

## 🛍️ Product Recommendations
- Prioritize style-conscious, versatile, and high-quality apparel.  
- Highlight seasonal collections, limited editions, and vintage pieces.  
- Introduce bundle deals (e.g., shirt + pants) to increase AOV.  
- Offer detailed fit guides and size recommendations to cut return rates.  

---

## 💰 Pricing Recommendations
- Maintain premium pricing for high-demand/exclusive products.  
- Use value-based bundles to encourage larger basket sizes.  
- Stay competitive on essentials to safeguard market share.  
- Apply seasonal promotions for trend launches.  

---

## 📢 Engagement & Marketing Recommendations
- Encourage **UGC campaigns** (e.g., “Outfit of the Day”).  
- Spotlight real-life wearability and positive reviews in campaigns.  
- Provide **outfit guides & styling tips** across channels.  
- Launch **loyalty programs** to reward repeat customers.  
- Collaborate with **influencers** to highlight comfort + style.  

---

## 🎯 Actionable Takeaway
- Double down on **high-satisfaction apparel** to drive sales.  
- Address **fit-related issues** to reduce churn.  
- Use **social proof and influencer content** to build trust and expand reach.  

---

## ⚖️ Ethical Considerations
- **Privacy** → Reddit data is public, but must be anonymized and used within ToS limits.  
- **Bias** → Reddit’s demographics may not represent all markets; sentiment models struggle with slang/sarcasm.  
- **Accuracy** → Positive-heavy classification risks overlooking negative reviews.  
- **Transparency** → Advanced models (XGBoost/LightGBM) are less interpretable vs. simpler models like Logistic Regression.  

---

### 📂 Source Code & Data
🔗 [GitHub Repository](https://github.com/kangwey-hash/ITD214_Project_KW_1)

There is 2 ipynb file both at most the same good to use Kapital_
