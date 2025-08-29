# Game Recommender System
Content-based recommendation system designed to suggest similar video games based on their attributes. This project was developed as the final assignment for the **Machine Learning** course and demonstrates an end-to-end workflow: from data preprocessing and exploratory data analysis to model construction, evaluation, and interpretation.

---

## Overview
The objective of this project is to recommend games to users by analyzing metadata and identifying similarities between titles. The system applies a **content-based filtering approach**, relying on descriptive features such as genre, platform, rating, publisher, and developer.  

The workflow includes:
- Exploratory Data Analysis (EDA) to investigate distributions, anomalies, and correlations
- Data cleaning and preprocessing (handling missing values, imputations, and anomalies)
- Feature encoding and weighting for improved similarity detection
- Model construction using cosine similarity on feature vectors
- Evaluation through game-specific case studies

---

## Data
The dataset contains video game metadata, including release information, sales, ratings, and developer details.

**Key Information**
- **Entries:** ~16,700 rows  
- **Features used for recommendation:** `Genre`, `Platform`, `Rating`, `Publisher`, `Developer`  
- **Dropped/Imputed:**  
  - Dropped `Critic_Score` and `User_Score` due to excessive missing values  
  - Imputed missing `Publisher` and `Rating` with `"Unknown"` / `"Unrated"`  
  - Corrected anomalies such as invalid `Year_of_Release` values  

### Data Dictionary (selected variables)

| Variable          | Description |
|-------------------|-------------|
| **Name**          | Game title |
| **Platform**      | Release platform (e.g., Wii, NES, DS, etc.) |
| **Year_of_Release** | Release year |
| **Genre**         | Game genre (e.g., Action, Sports, RPG) |
| **Publisher**     | Game publisher |
| **NA_Sales**      | North America sales (millions) |
| **EU_Sales**      | Europe sales (millions) |
| **JP_Sales**      | Japan sales (millions) |
| **Other_Sales**   | Sales in other regions (millions) |
| **Global_Sales**  | Total worldwide sales (millions) |
| **Critic_Score**  | Average critic score (0–100) |
| **Critic_Count**  | Number of critic reviews |
| **User_Score**    | Average user score (0–10) |
| **User_Count**    | Number of user reviews |
| **Developer**     | Game developer |
| **Rating**        | ESRB rating (E, T, M, etc.) |

---

## Features
- **Exploratory Data Analysis**
  - Game releases peaked between 2005–2010, dominated by Action and Sports genres  
  - Global sales strongly correlated with NA and EU sales  
  - Majority of titles rated **E** (Everyone) or **T** (Teen), showing market focus on family-friendly content  
- **Preprocessing**
  - Dropped unreliable or sparsely filled features (Critic/User scores)  
  - Imputed categorical values with `"Unknown"` / `"Unrated"`  
  - Removed or corrected anomalous release years  
- **Recommendation System**
  - **Content-based filtering** with TF-IDF and one-hot encoding  
  - Features weighted, emphasizing **Genre** and **Developer** as primary determinants of similarity  
  - Cosine similarity used to calculate game-to-game relevance  
- **Evaluation**
  - Case study inputs:  
    - **Resident Evil 4** → recommended Action games with same rating (M) and developer (Capcom)  
    - **Animal Crossing** → recommended Nintendo games with same platform/rating, e.g., The Legend of Zelda: The Wind Waker  
    - **Final Fantasy IV** → recommended RPGs from Matrix Software and related series across platforms  

---

## Tools & Technologies
- **Python** – core development  
- **Pandas / NumPy** – data cleaning and manipulation  
- **Matplotlib / Seaborn** – visualization and EDA  
- **Scikit-learn** – preprocessing, TF-IDF, and similarity computations  
- **Cosine Similarity** – metric for recommendation ranking  

---

## Deliverables
- **Jupyter Notebook** – complete workflow for EDA, preprocessing, and model implementation  
