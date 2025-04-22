# 📲 Instagram Engagement Prediction with Vision API, & Multimodal Learning

This project explores how to analyze and predict engagement on Instagram posts using a multimodal approach that combines computer vision, NLP, and machine learning. Built using a real-world Kaggle dataset, this notebook walks through everything from image labeling and topic modeling to regression modeling based on visual and textual features.

---

## 🔹 Project Highlights

### 🗃️ Dataset
- Based on a Kaggle dataset of real Instagram post data (images, captions, and metadata).
- Parsed folder structure with images, metadata `.json` files, and caption `.txt` files.

### 📈 Vision API Integration
- Used Google Cloud Vision API to extract image content labels.
- API responses parsed and stored per image.

### 🌍 Topic Modeling
- Applied Latent Dirichlet Allocation (LDA) on the image labels.
- Identified common themes and named each topic based on top 25 keywords.
- Compared topic prevalence between low and high engagement posts.

### 📊 Engagement Analysis
- Created an "engagement" feature using the number of comments.
- Analyzed differences in topic weights across engagement quartiles.
- Log-transformed engagement for regression stability.

### 🎨 Feature Engineering
- Caption embeddings: using spaCy medium English vectors (`en_core_web_md`).
- Label embeddings: combined label words and encoded similarly.
- Final features were concatenated text + image vectors.

### 🤖 Multimodal Machine Learning
- Trained a Random Forest Regressor to predict log(comment count).
- Hyperparameter tuning via GridSearchCV.
- Final performance: R² ~ 37% and MAE ~ **1.7 comments**

### 📊 Visual Analysis
- Word clouds for LDA topics.
- Feature importance plot from RandomForest to compare caption vs. label contributions.

---

## 💡 Insights

Based on topic modeling and engagement prediction analysis, we found that not all content types drive equal interaction. Here are actionable insights drawn from the data:

### 📢 For Brands:
- Content tied to **personal expression**, **facial emotion**, and **fashion-oriented visuals** (e.g., smiling, close-up portraits, stylish outfits) generates **significantly more comments**.
- If the brand’s strategy is to boost engagement, it should **collaborate with lifestyle influencers** who share happy, relatable moments and connect with their audience through emotion and style.
- Incorporating themes of **beauty, positivity, and everyday fashion** into campaign visuals may foster a stronger emotional connection and trigger more interaction.

### 👩‍💼 For Influencers:
- Use **close-up, expressive shots** that show emotion — laughter, joy, and real moments perform better than overly polished or distant images.
- Include people, pets, or dynamic elements — content featuring **happy children**, **pets**, or **everyday lifestyle** scenes tends to spark more discussion.
- When featuring products (especially in food or home categories), always add a **human element** — showing yourself with the item feels more authentic and earns more engagement.

### 🔍 Summary:
- Engagement is driven by **emotion, expression, and lifestyle relatability**.
- **Caption text** tends to carry more predictive power than image labels, but both together perform better.
- Real moments beat perfectly polished ones in terms of audience interaction.

---

## 🚀 How to Run
1. Clone the repo or open the notebook in Google Colab.
2. Upload your Kaggle `kaggle.json` credentials file and authenticate.
3. Use the Kaggle API to download the dataset directly in the notebook.
4. Enable Google Cloud Vision API and insert your API key.
5. Run the notebook end-to-end.

---

## 🌟 Credits
- Dataset: [Kaggle - Instagram Posts Dataset](https://www.kaggle.com/datasets/thecoderenroute/instagram-posts-dataset)
- Vision API: Google Cloud
- NLP: spaCy
- ML: scikit-learn, pandas, matplotlib

