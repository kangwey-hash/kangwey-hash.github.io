---
layout: post
author: Chong Kang Wey
title: "Applied Data Science Project Documentation"
categories: ITD214
---

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
## 🔎 Deeper Topic Analysis & Recommendations

📊 **Business Objectives & Actionable Insights:**  
Our topic modeling and sentiment analysis revealed consistent **high customer satisfaction across most themes**, with one area (fit & pants) showing slightly more mixed reviews. Below is the breakdown:

| Topic ID | Top Keywords | Reviews Analyzed | Positive % | Negative % | Recommendation |
|----------|--------------|----------------|------------|------------|----------------|
| 0 | love outfit post cool fit | 7,505 | 82.7% | 17.3% | Leverage styling discussions in trend-driven product launches and social engagement campaigns. |
| 1 | fit pants im like bro | 9,528 | 77.4% | 22.6% | Investigate fit-related issues (pants sizing, product descriptions) to improve customer satisfaction. |
| 2 | like dont people think clothes | 11,157 | 82.6% | 17.4% | Promote products/services related to general apparel discussions in marketing campaigns. |
| 3 | like shoes im wear look | 8,888 | 84.9% | 15.1% | Emphasize fit and comfort in shoes and apparel; integrate keywords into engagement content. |
| 4 | shirt shirts jeans pants jacket | 7,376 | 87.1% | 12.9% | Validate premium pricing; highlight staple apparel as flagship items. |

---

### 📌 Summary of Insights  

- **High Satisfaction (Topics 0, 2, 3, 4):** Customers show consistently positive sentiment (82–87%) across core categories: *outfits, shirts, jeans, jackets, shoes*. These themes validate **Kapital’s premium product strategy** and can be leveraged in **marketing campaigns**.  
- **Moderate Satisfaction (Topic 1 - Fit & Pants):** Only ~77% positive. This is a **critical product signal**. Kapital should **review sizing issues** (pants fit, shirt necklines) and possibly refine **size charts, body-inclusive fits, or clearer product details**.  
- **Strategic Opportunity:** By addressing fit-related concerns, Kapital can **reduce negative sentiment by ~10–15%**, boosting customer satisfaction and strengthening its premium positioning.  
 

### 📌 Recommendations
Based on the deeper topic analysis and sentiment insights, here are strategic recommendations for Kapital:

---

### 🛍️ Product Recommendations
- Focus on **style-conscious, versatile, high-quality apparel**.  
- Highlight **unique/vintage pieces, seasonal collections, and limited editions**.  
- Offer **bundles** (e.g., shirts + pants) to increase **Average Order Value (AOV)**.  
- Provide **fit guides and size recommendations** to reduce returns and enhance customer satisfaction.

---

### 💰 Pricing Recommendations
- Set **premium pricing** for high-demand or exclusive style items.  
- Use **value-based bundles** for essentials to encourage larger purchases.  
- Ensure **competitive pricing** for standard items to maintain market share.  
- Offer **strategic promotions** around trends or seasonal launches.

---

### 📢 Engagement & Marketing Recommendations
- Encourage **user-generated content (UGC)** like “Outfit of the Day” posts.  
- Run **social campaigns** highlighting positive reviews and real-life wearability.  
- Provide **outfit guides and style tips** through email, social media, or app.  
- Implement **loyalty programs or incentives** for repeat purchases.  
- Leverage **influencers** to showcase both comfort and style.

---

### 🎯 Actionable Takeaway
- **Leverage high-satisfaction topics** to drive marketing campaigns.  
- **Upsell via bundles** and improve **fit & size guidance**.  
- Use **social proof and influencer partnerships** to maximize engagement and sales.  


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

