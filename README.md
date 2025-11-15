Amazon Sales Prediction: Modeling Product Price

A machine learning project that uses Multiple Linear Regression on a large Amazon Canada dataset to build a baseline model for predicting product prices based on features like reviews, ratings, and sales volume.

About the Project

This notebook, `AmazonSalesPrediction.ipynb`, documents the entire process of building a baseline price prediction model. The primary goal was to determine if standard product metrics (ratings, reviews, sales, and category) could effectively predict the final listing price of a product.

The project involves rigorous data cleaning, particularly using the Interquartile Range (IQR) method to remove significant outliers in `price`, `reviews`, and `stars` to ensure model stability.

Installation

# Prerequisites

  * **Python** (3.x)
  * Common data science libraries: `pandas`, `numpy`, `scikit-learn`
  * Visualization libraries: `matplotlib`, `seaborn`

# Steps

1.  **Clone the Repository**

    ```bash
    git clone https://github.com/shadab-tajwar/AmazonSalesPrediction.git
    cd AmazonSalesPrediction
    ```

2.  **Install Dependencies**

    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn
    ```

3.  **Run the Notebook**
    Open the `AmazonSalesPrediction.ipynb` file in Jupyter or Colab and run the cells sequentially to execute the cleaning, EDA, feature engineering, and modeling steps.

Methodology and Results

### Dataset Summary

The model was trained on the cleaned Amazon\_CA\_Price\_Prediction dataset:

| Metric | Value |
| :--- | :--- |
| **Initial Records** | Over 2.5 Million |
| **Final Records (After Cleaning)** | 1,952,182 |
| **Target Variable** | `price` |

### Key Preprocessing Steps

  * NaN and Infinite values were dropped.
  * Outlier removal using **IQR** on `price`, `reviews`, and `stars`.
  * The top 20 `category` values were selected and **one-hot encoded** for use as features.

### Model Performance (Multiple Linear Regression)

The linear regression model was used as a baseline, but the results showed a weak predictive relationship:

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **R-squared** | $\approx 0.052$ | Only 5.2% of the variance in price is explained by the features. |
| **Mean Squared Error (MSE)** | $\approx 553.7$ | High error value, indicating poor predictive accuracy. |

### Feature Insights

  * **Strongest Predictors:** `reviews` and `boughtInLastMonth` were the most statistically significant variables.
  * **Correlation:** `reviews` and `boughtInLastMonth` exhibited the highest correlation ($\approx 0.47$).
  * **`isBestSeller`:** This feature had a coefficient near 0, suggesting it did not significantly impact the predicted price in the linear model.

Future Work

To achieve a meaningful price prediction, the following steps are recommended:

1.  **Non-Linear Modeling:** Implement and compare models like **Random Forest** or **Gradient Boosting (XGBoost)** to capture complex, non-linear patterns in the data.
2.  **Feature Refinement:** Explore advanced feature engineering, potentially involving text features from product titles or more sophisticated categorical encoding methods.
3.  **Further Outlier Analysis:** Revisit the outlier removal process to see if less aggressive cleaning improves results for non-linear models.

License

This work is provided under the **Creative Commons Zero v1.0 Universal (CC0)** Public Domain Dedication.

Contact

**Project Link:** [https://github.com/shadab-tajwar/AmazonSalesPrediction](https://www.google.com/search?q=https://github.com/shadab-tajwar/AmazonSalesPrediction)
**Maintainer:** shadab-tajwar
