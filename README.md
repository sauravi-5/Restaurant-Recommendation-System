# Restaurant Recommendation System

A content-based restaurant recommender built on Zomato's Bangalore restaurant dataset. Given a restaurant a user likes, it recommends similar restaurants based on review text and other features.

## How it works

1. **Data cleaning** — drops irrelevant columns (`url`, `dish_liked`, `phone`), removes duplicates, drops missing values, and renames columns for clarity (e.g. `approx_cost(for two people)` → `cost`).
2. **Feature extraction** — builds a TF-IDF matrix over restaurant review text.
3. **Similarity scoring** — computes cosine similarity between restaurants based on their TF-IDF vectors.
4. **Recommendation** — given a restaurant name, returns the top-N most similar restaurants by similarity score.

## Tech stack

- Python
- pandas, NumPy
- scikit-learn (`TfidfVectorizer`, `cosine_similarity`, `CountVectorizer`)
- seaborn, matplotlib (exploratory data analysis)

## Contents

```
Zomato-Restaurant-Recommendation-System/
├─ Zomato.ipynb      # full analysis, cleaning, and recommendation pipeline
├─ Output.png        # sample output
├─ LICENSE
└─ README.md
```

## How to run

1. Download the [Zomato Bangalore Restaurants dataset](https://www.kaggle.com/datasets/himanshupoddar/zomato-bangalore-restaurants) and update the CSV path in the notebook.
2. Install dependencies: `pip install pandas numpy scikit-learn seaborn matplotlib`
3. Run `Zomato.ipynb` top to bottom.
4. Call `recommend("<restaurant name>")` to get recommendations.

## Notes

The current notebook reads the dataset from a local file path — swap this for a relative path or a data-loading cell if you want this to run out-of-the-box for others.
