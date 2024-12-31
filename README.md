# ML-Prediction-of-Board-Games-Ratings 🎲🎯

---

## Overview
This project focuses on building a machine learning model to predict the average ratings of board games listed on the [BoardGameGeek](https://boardgamegeek.com/) website, using *only information that would be available prior to a new game's release into the market*. Using a combination of numerical and categorical pre-release features, this approach aims to provide actionable insights for game developers, helping them optimize their designs before launch.

### Key Objectives
1. Develop a machine learning model to predict board game ratings.
2. Identify the most important features influencing these ratings.
3. Provide actionable insights for game developers and enthusiasts.

---

## Dataset
The dataset used in this project was sourced from [Kaggle's Board Games Dataset](https://www.kaggle.com/datasets/threnjen/board-games-database-from-boardgamegeek/data?), which contains a comprehensive list of board games and their attributes. Key features include:
- **Numerical Features**:
  - Year of Publication
  - Game Weight (complexity)
  - Minimum and Maximum Players
  - Playtime
  - Age Recommendation
  - Number of Expansions
- **Categorical Features**:
  - Kickstarted (yes/no)
  - Game Category and Subcategory
  - Game Mechanics

---

## Implementation Details

### Preprocessing
1. **Exploratory Data Analysis**:
   - Frequency distributions and correlation analysis for numerical features.
   - Analysis of categorical features, including one-hot encoding for model readiness.
2. **Handling Multicollinearity**:
   - Checked for perfect correlations (±1) among numerical features.
   - No issues found.
3. **Scaling and Transformation**:
   - Applied `StandardScaler` and `MinMaxScaler` for numerical features.
   - Log transformation to handle skewness.

### Model Selection
Top machine learning model tested:
- **XGBoost Regressor (Best Performer)**:
  - Achieved R-squared: 0.570278 (improved from baseline 0.499967).
  - Mean Squared Error (MSE): 0.3663090.

### Hyperparameter Tuning
Used `GridSearchCV` to fine-tune parameters for XGBoost. The best configuration:
- `n_estimators`: 300
- `max_depth`: 7
- `learning_rate`: 0.05
- `subsample`: 0.8
- `colsample_bytree`: 0.8

---

## Key Insights
1. **Top Features Influencing Ratings**:
   - **Game Complexity** (Game Weight)
   - **Year of Publication**
   - Specific categories/mechanics, including:
     - War Games
     - Miniatures
     - Solitaire Games
     - Roll, Spin & Move Games

2. **Feature Analysis**:
   - Games with higher complexity tend to receive better ratings.
   - Recently published games (post-2000s) show trends in higher average ratings.

## Future Directions
1. Explore dimensionality reduction techniques like PCA
2. Fine-tune other models such as KNN, Linear Regression, and Decision Trees to reduce overfitting.
3. Perform a statistical analysis of the effects of top features on ratings.

## Project Structure
- `boardgamesgeek.ipynb`: Jupyter Notebook with the full analysis.
- `ML and Board Games.pdf`: PDF presentation summarizing the findings.
