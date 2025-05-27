# 📱 Smartphone Recommendation System

India is one of the fastest-growing smartphone markets globally, with millions of consumers relying on digital platforms for product discovery. This project aims to build a recommendation system that helps surface relevant smartphone options to users based on popularity trends and personalized preferences.

The system leverages both **popularity-based** and **collaborative filtering** techniques to suggest smartphones users are most likely to engage with—improving product visibility and increasing conversion chances.

---

## 🎯 Purpose of the Analysis

The purpose of this analysis is to:

- Understand smartphone user review patterns across a large dataset
- Build a **popularity-based model** to recommend the highest-rated phones overall
- Build **collaborative filtering models** to personalize recommendations using user-item interaction data
- Compare model performances using RMSE and other summary metrics

---

## 📂 What's in the Repo

- `phone_recommendation_system.py` – Full script covering data ingestion, cleaning, model building, and evaluation
- `README.md` – This file

> ⚠️ **Note:** The review datasets (`phone_user_review_file_*.csv`) are **confidential** and not included in this repository. Please ensure you have access to them and place them in the root directory before running the script.

---

## 🛠 Methods Used

The project workflow includes:

### 1. **Data Preparation**
- Combined 6 review CSV files into a unified DataFrame
- Cleaned null values and rounded scores
- Filtered to include:
  - Products with >50 ratings
  - Users with >50 reviews
- Sampled 1 million rows and filtered down to 5,000 high-quality interactions for modeling

### 2. **Modeling Techniques**
#### 📊 Popularity-Based Recommendation
- Recommends smartphones with highest average scores and highest number of reviews

#### 🤝 Collaborative Filtering
- Implemented using the `Surprise` library
- Models used:
  - **SVD (Singular Value Decomposition)**
  - **KNNWithMeans (Item-based)**
  - **KNNWithMeans (User-based)**

### 3. **Evaluation**
- Test/train split (80:20)
- Performance compared using **RMSE**
- Cross-validation (5-fold) for each model
- Top-5 recommendations generated per user from predictions

---

## 🔍 Results Summary

| Model                  | Test RMSE | Average Prediction Score | Cross-Validation RMSE |
|------------------------|-----------|--------------------------|-----------------------|
| SVD                    | 2.84      | 7.78                     | 2.79                  |
| KNNWithMeans (Item)    | 2.99      | 7.80                     | 2.83                  |
| KNNWithMeans (User)    | 2.98      | 7.76                     | 2.80                  |

- All models performed competitively, with **SVD and item-based filtering** emerging as consistently strong performers.
- Generated top-5 smartphone recommendations for each user from predicted scores.

---

## 🚀 How to Run

1. **Clone the repository**:
   ```bash
   git clone https://github.com/moni0811/Recommendation-System---User-Phone-Review.git
   cd Recommendation-System---User-Phone-Review

2. Install below requirements if not installed
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn scikit-surprise
   
3. Run analysis script
   ```bash
   python phone_recommendation_system.py
