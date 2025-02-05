# Classifying Mushrooms as Poisonous or Edible Using Binary Logistic Regression
Alejandro Vazquez, 2/5/2025

## Introduction

Hello, thank you for viewing my project! In this project, my goal is to classify mushrooms as either edible or poisonous using binary logistic regression. Throughout the analysis I compared different preprocessing approaches and evaluated their impact on model performance. The dataset consists of various categorical features describing physical and environmental attributes of mushrooms.

## Dataset

* **Source**: UCI Machine Learning Repository
* **Number of observations**: 8,124
* **Features**: 22 categorical variables describing characteristics such as cap shape, odor, gill color, stalk root, and habitat.
* **Target variable**: `poisonous` (binary classification: edible = 0, poisonous = 1)
* **Citation**: Mushroom [Dataset]. (1981). UCI Machine Learning Repository. https://doi.org/10.24432/C5959T.

## Methodology

1. **Exploratory Data Analysis and Preprocessing**
    * Handling missing values in the `stalk-root` column (removing the feature altogether vs. removing the rows with missing data)
    * Used bar plots to view feature distributions
    * One-Hot Encoding for categorical variables
    * Splitting data into training (70%) and test (30%) subsets

2. **Modeling**
    * Selected relevant features using Chi-Square Test of Independence
    * Implemented binary logistic regression

3. **Evaluation**
    * Evaluated model performance using performance metrics such as Accuracy, Precision, Recall, and F1 Score
    * Cross-Validation to assess model generalization

## Results

I created two binary logistic regression models using different data. The first model was built using data where the `stalk-root` column was dropped entirely, and the second model was built where rows with missing values for `stalk-root` were dropped (approximately 25% of the data).

* **Model 1** (Dropped `stalk-root`):

    * Cross-validation mean accuracy: 95.5%
    * Accuracy: 0.9984
    * Precision: 1.0000
    * Recall: 0.9966
    * F1 Score: 0.9983

* **Model 2** (Kept `stalk-root`, dropped missing rows)
    * Cross-validation mean accuracy: 98.8%
    * Accuracy: 1.0000
    * Precision: 1.0000
    * Recall: 1.0000
    * F1 Score: 1.0000

Model 2 performed better, indicating that retaining `stalk-root` (despite dropping missing rows) improves classification accuracy.

## Conclusion

The presence of the `stalk-root` feature significantly influences model performance, emphasizing the importance of considering a features potential predictive ability before dropping it from your data. Furthermore, cross-validation proved to be a more realistic measure of modek accuracy. 

Future work could include exploring more complex machine learning models to potentially improve the predictice capability of classifying a mushroom as poisonous or edible.

## How to Run the Project

1. Clone the repository:
    *     git clone https://github.com/AlexVazquez19/mushroom-project.git
2. Navigate to the directory:
    *     cd mushroom-project
3. Install dependencies
    * Pandas
    * Numpy
    * Sklearn
    * SciPy
    * StatsModels
    * itertools
    * Seaborn
    * Matplotlib
    * ucimlrepo
4. Run the jupyter notebook: `mushroom.ipynb`