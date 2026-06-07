# Netflix_Recommendation_Engine

## Dataset Information

![{47BCFE8E-682C-4FEC-9C6E-B557F2D05FEA}](https://github.com/user-attachments/assets/c060d494-eff5-4f9c-ae8c-2f890f66059d)

- The numbers with " : " behind them and NaN in corresponding rating are movie ids according to data set
- The rest are customer id

**Importing Surprise Library**

The Surprise library is a Python library used for building and analyzing recommender systems. It is particularly useful for collaborative filtering-based recommendation algorithms. Surprise stands for "Simple Python Recommendation System Engine" and is designed to work efficiently with large datasets.

📌 Key Features of Surprise:
- Implements collaborative filtering methods (e.g., matrix factorization and nearest neighbors algorithms).
- Supports both explicit (e.g., ratings) and implicit feedback.
- Provides tools for model evaluation (e.g., RMSE, MAE, precision-recall).
- Allows for custom algorithms to be implemented.
- Works well with pandas and scikit-learn.


📌 **1. Reader (Data Preprocessing)**

The Reader class defines the rating scale and format of the dataset. Since different datasets have different rating scales (e.g., 1–5 stars or 0–10 scores), the Reader ensures that Surprise understands the data correctly.
- If using a custom dataset, you must specify the Reader while loading data.
- If using built-in datasets (like ml-100k), the Reader is not required.

📌 **2. Dataset (Loading Data)**

The Dataset module is used to load and process recommendation data.

📌 **3. SVD (Singular Value Decomposition)**

SVD (Singular Value Decomposition) is a matrix factorization algorithm that is widely used in recommendation systems.
- A collaborative filtering algorithm used for making recommendations

**SVD (Singular Value Decomposition) in a recommendation system works by finding patterns in user preferences and item similarities. Here's a basic idea without going deep into the topic**

**1) What the System Has:** A big table (matrix) with users on one side and items (like movies) on the other. Users give ratings to items, but not everyone has rated everything

**2) What SVD Does**: SVD looks at the ratings that are available and tries to figure out the hidden connections between users and items. It learns what kind of movies users like based on their previous ratings

**3) How It Helps:** Once SVD understands these patterns, it can predict how a user might rate a movie they haven’t seen yet. Based on these predictions, the system recommends movies that the user is most likely to enjoy

**4) Step-by-Step Implementation of SVD in a Recommendation System**

Install and Import Libraries

Load and Prepare the Dataset

Train the SVD Model

Evaluate the Model

Make Predictions

Here’s a **project explanation tailored for interviews** based on your Netflix recommendation engine built using SVD and the Surprise library. It highlights your skills in data processing, collaborative filtering, model evaluation, and hands-on implementation:

---

### 🎬 **Netflix Movie Recommendation Engine — Project Overview**

#### 🔹 **Objective:**

To build a **personalized movie recommendation engine** for Netflix users using **collaborative filtering**, specifically the **SVD (Singular Value Decomposition)** algorithm from the Surprise library.

---

### 📁 **Dataset Description:**

* The dataset `netflix.csv` contains **Cust_IDs**, **Movie_IDs**, and **ratings**.
* Each row represents a user's rating for a movie.
* Additional metadata like movie titles can be integrated using a separate file (e.g., `movies.csv`).

---

### 🧠 **Approach & Workflow:**

#### 1. **Data Preprocessing:**

* Loaded the dataset using `pandas`.
* Ensured columns were renamed properly (`user_id`, `movie_id`, `rating`) for compatibility with Surprise.
* Converted the dataset into a format that the Surprise library accepts using `Reader` and `Dataset.load_from_df()`.

#### 2. **Model Selection — SVD (Singular Value Decomposition):**

* Chose **SVD**, a matrix factorization-based algorithm, ideal for **collaborative filtering**.
* SVD reduces dimensionality of the user–item rating matrix and learns **latent features** that represent user preferences and item characteristics.

#### 3. **Model Training & Evaluation:**

* Trained the model using **cross-validation** (`cross_validate`) with 5 folds.
* Evaluated the model performance using:

  * **RMSE (Root Mean Square Error)**
  * **MAE (Mean Absolute Error)**
* Achieved good prediction accuracy, showing the model’s ability to generalize.

#### 4. **Predictions & Recommendation Generation:**

* Used `algo.predict(Cust_id, movie_id)` to predict ratings for a user–movie pair.
* Built a function to generate **Top-N recommendations** for each user using predictions on the **anti-testset** (all unseen movies by the user).
* Sorted predictions by estimated rating to suggest the most relevant movies.

---

### 📌 **Key Features Implemented:**

* Collaborative filtering with SVD (no content-based features required).
* Top-N personalized movie recommendations.
* Evaluation of model performance using multiple metrics.
* Mapping of recommended movie IDs to actual **movie titles** (via an external movie metadata file).

---

### ✅ **What I Learned:**

* Understanding of **latent factor models** (Latent factor models are statistical models that represent observed variables as a result of underlying, unobserved factors. These models aim to capture the relationships between observed data by identifying a smaller set of latent variables (factors) that explain the patterns in the data) and collaborative filtering.
* Implementation of **SVD using Surprise**, including model training, testing, and tuning.
* Evaluating recommender systems using appropriate metrics.
* The importance of **data preprocessing**, **anti-testset generation**, and **ranking logic** for recommendations.

---
