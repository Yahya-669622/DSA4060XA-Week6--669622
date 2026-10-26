# DSA4060XA: Week 6 Guided Evaluation Lab - Recommendation Systems

This repository contains the code, evaluation pipelines, and findings for the Week 6 Guided Evaluation Lab focusing on building, evaluating, and comparing recommendation system models.

## Dataset Overview
The lab utilizes two core datasets:
* `DSA4060_Week6_Movies.csv`: Contains movie metadata, item IDs, and genre feature representations.
* `DSA4060_Week6_Ratings.csv`: Contains user-item interaction history and explicit user ratings.



## Models Implemented
1. **Popularity Baseline**: Recommends top-rated and most frequently interacted items globally across all users.
2. **Content-Based Filtering**: Matches item genre feature vectors against individual user preference profiles using cosine similarity.
3. **Item-Based Collaborative Filtering (CF)**: Computes item-item rating similarities to predict missing interactions and score unseen items.



## Evaluation Dimensions & Metrics
The models were comprehensively evaluated across multiple categories:
* **Rating Prediction Accuracy**: Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).
* **Ranking Quality**: Precision@K, Recall@K, and Normalized Discounted Cumulative Gain (NDCG@K) at $K = 3$.
* **Beyond-Accuracy Metrics**: 
  * *Catalogue Coverage*: Proportion of unique items recommended across the user base.
  * *Novelty*: Inverse popularity measure indicating the capacity to surface uncommon/unexpected items.
  * *Intra-List Diversity*: Cosine distance dissimilarity among items within individual top-$K$ recommendation lists.



##  Key Findings & Summary
* **Rating Accuracy vs. Beyond-Accuracy Trade-off**: While **Item-Based CF** achieved superior rating prediction accuracy (lowest MAE/RMSE) and maximized catalogue coverage (85%) and diversity (0.780), metrics shift depending on business constraints.
* **Ranking & Discovery**: Content-based filtering showed strong top-$L$ list ordering performance (NDCG@3 = 0.200), whereas popularity baselines suffered from severe popularity bias and restricted catalogue exposure (35% coverage).
* **Business Recommendation**: For scenarios prioritizing user discovery and minimizing popular title saturation, collaborative and content-hybrid strategies provide optimal beyond-accuracy performance despite lower immediate top-$K$ precision.

---

## Repository Structure
* `DSA4060_Week6_Lab.ipynb`: Complete Google Colab notebook containing all data preprocessing, modeling, evaluation steps, and trade-off analyses.
