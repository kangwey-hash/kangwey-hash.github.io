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

### 📌 Recommendations
## 🔎 Deeper Topic Analysis  

📊 **Business Objectives & Actionable Insights:**  
Our topic modeling and sentiment analysis revealed consistent **high customer satisfaction across most themes**, with one area (fit & pants) showing slightly more mixed reviews. Below is the breakdown:

---

### 🧵 Topic 2: *"like dont people think clothes"*
- **Reviews analyzed:** 11,157  
- **Sentiment distribution:** 👍 Positive: **82.6%** | 👎 Negative: **17.4%**  
- **Sample reviews:**  
  - *“military surplus stores would best websites buy military surplus”*  
  - *“need help finding rings… still cool shape design”*  
  - *“bought used paul smith suit… thought process it’ll look way better than Jos Banks at same price”*  
- ✅ **Action:** High satisfaction. Kapital should **promote products/services** tied to general apparel discussions and highlight them in marketing campaigns.

---

### 👟 Topic 3: *"like shoes im wear look"*
- **Reviews analyzed:** 8,888  
- **Sentiment distribution:** 👍 Positive: **84.9%** | 👎 Negative: **15.1%**  
- **Sample reviews:**  
  - *“underwear guys wear… thick legs lifting… need brand that actually fits”*  
  - *“briefs still uncool… switching styles helped”*  
  - *“tall skinny boys… size shoe shopping style footwear doesn’t look like clown shoes”*  
- ✅ **Action:** Strong satisfaction around footwear & wearability. Kapital can **emphasize fit + comfort in shoes and apparel** within engagement content.

---

### 👖 Topic 1: *"fit pants im like bro"*
- **Reviews analyzed:** 9,528  
- **Sentiment distribution:** 👍 Positive: **77.4%** | 👎 Negative: **22.6%**  
- **Sample reviews:**  
  - *“fabletics best deal around price & quality… shorts high quality”*  
  - *“vineyard vines polo neckline too small…”*  
  - *“pants short legs long torso… finding shirts difficult, pants nightmare”*  
- ⚠️ **Action:** Moderate satisfaction. Kapital should **investigate fit-related issues (pants/sizing)**. This could be linked to sizing consistency, body diversity, or unclear product descriptions.

---

### 👕 Topic 4: *"shirt shirts jeans pants jacket"*
- **Reviews analyzed:** 7,376  
- **Sentiment distribution:** 👍 Positive: **87.1%** | 👎 Negative: **12.9%**  
- **Sample reviews:**  
  - *“find denim jacket that’s right length…”*  
  - *“Charles Tyrwhitt shirts… thin see-through issue”*  
  - *“advice for suit + pastel pink styling”*  
- ✅ **Action:** Very high satisfaction around staple apparel (shirts, jeans, jackets). Kapital can **confidently validate premium pricing** here and push these as flagship items.

---

### 👗 Topic 0: *"love outfit post cool fit"*
- **Reviews analyzed:** 7,505  
- **Sentiment distribution:** 👍 Positive: **82.7%** | 👎 Negative: **17.3%**  
- **Sample reviews:**  
  - *“anyone know sunglasses protect UV… Vans shades…”*  
  - *“thinnest breathable boxer briefs… Lululemon mesh better than others”*  
  - *“Paul Vincent Seh Kelly passes away… warm character frequent contributor”*  
- ✅ **Action:** Strong satisfaction tied to **outfits & styling discussions**. Kapital can **leverage this in trend-driven product launches** and social engagement.

---

## 📌 Summary of Insights  

- **High Satisfaction (Topics 0, 2, 3, 4):** Customers show consistently positive sentiment (82–87%) across core categories: *outfits, shirts, jeans, jackets, shoes*. These themes validate **Kapital’s premium product strategy** and can be leveraged in **marketing campaigns**.  
- **Moderate Satisfaction (Topic 1 - Fit & Pants):** Only ~77% positive. This is a **critical product signal**. Kapital should **review sizing issues** (pants fit, shirt necklines) and possibly refine **size charts, body-inclusive fits, or clearer product details**.  
- **Strategic Opportunity:** By addressing fit-related concerns, Kapital can **reduce negative sentiment by ~10–15%**, boosting customer satisfaction and strengthening its premium positioning.  

---


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

