# 👕 Analysing Customer Sentiments and Product Categories from Reddit

### 🎯 Business Goal
To optimize the **Kapital fashion brand’s** product offerings, pricing strategies, and customer engagement to **maximize sales and brand loyalty in the global market**.

This project supports that goal by leveraging **text analytics from Reddit discussions** to inform and optimize Kapital’s global **product, pricing, and engagement strategies**.

---

### 📝 Project Background
Manually sifting through thousands of online discussions to gauge customer sentiment and emerging fashion trends is inefficient.  

This project automates the process using **NLP + Machine Learning**, combining **sentiment analysis** and **topic modeling** to extract **actionable business insights**.

---

### 🔧 Workflow

#### 1. Data Preparation
- **Data Acquisition & Merging** → Combined Reddit posts & comments → **44,454 unique entries**.  
- **Cleaning & Preprocessing** → Removed duplicates, handled missing values.  
- **Text Normalization** → Lowercasing, punctuation removal, stopword filtering.  

#### 2. Modeling
- **Feature Extraction** → TF-IDF Vectorizer.  
- **Model Training (with GridSearchCV + StratifiedKFold)**  
  - Logistic Regression → 91%  
  - SVM → **92% (best)**  
  - Random Forest → 90%  
  - XGBoost → 88%  
  - LightGBM → 90%  
- ✅ **Final Model Selected: SVM** (highest accuracy).  

#### 3. Evaluation
- High accuracy overall, but models showed **bias toward positive sentiment**.  
- Negative sentiment often misclassified → risk of missing **critical customer feedback**.  

---

### 📊 Topic-Sentiment Insights

| Topic ID | Top Keywords                     | Positive Ratio | Negative Ratio | Insight |
|----------|----------------------------------|----------------|----------------|---------|
| **4**    | shirt, shirts, jeans, pants      | 0.74           | 0.26           | 🟢 High satisfaction → validates premium pricing |
| **3**    | like, shoes, wear, look          | 0.69           | 0.31           | 🟢 Strong brand reception, leverage in engagement |
| **0**    | love, outfit, post, cool, fit    | 0.65           | 0.35           | 🟢 Inform product strategies to match trends |
| **2**    | like, dont, people, think, clothes | 0.65         | 0.35           | 🟢 Promote related themes in marketing campaigns |
| **1**    | fit, pants, im, like, bro        | 0.54           | 0.46           | ⚠️ Moderate satisfaction → investigate sizing/fit issues |

---

### 📌 Recommendations

- **Product Strategy** → Strengthen high-performing categories (shirts, jeans, shoes, outfits). Investigate sizing/fit issues in pants.  
- **Pricing Strategy** → Positive sentiment supports Kapital’s premium pricing model. Reinforce value by highlighting craftsmanship.  
- **Engagement Strategy** → Use customer language (“cool fit”, “love outfit”) in marketing. Proactively engage in “fit” discussions to address concerns.  

---

### ⚖️ Ethical Considerations
- **Privacy** → Reddit data is public, but anonymization & ToS compliance are key.  
- **Bias** → Dataset overrepresents certain demographics; sentiment models may miss sarcasm/slang.  
- **Accuracy** → Positive-heavy classification risks overlooking complaints.  
- **Transparency** → Complex models (XGBoost, LightGBM) are less interpretable than simpler ones.  

---

### 📂 Source Code & Data
🔗 [GitHub Repository](https://github.com/kangwey-hash/ITD214_Project_KW)

---
