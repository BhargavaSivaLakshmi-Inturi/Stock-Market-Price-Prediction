The main goal of this project is to predict the daily trend of the NASDAQ Composite index (^IXIC) open price.
It specifically aims to forecast whether the opening price of the NASDAQ on the next trading day will be higher than the opening price of the current day. This is set up as a classification problem where the target variable is 1 for an upward movement and 0 for no movement.
The highlight are:
**Historical Data Analysis:** This project uses historical NASDAQ data obtained from the `yfinance` library, focusing on data from 2000 onward.
**Feature Engineering:** It creates custom technical indicators based on rolling averages and historical trends to identify patterns in the stock market data.
**Robust Evaluation:** The project uses `TimeSeriesSplit` for thorough cross-validation, ensuring the model's performance is assessed realistically on time-ordered data and avoids look-ahead bias.
**Model Comparison:** It compares the performance of two strong classification algorithms: Random Forest and XGBoost.
**Missing Value Handling:** The project incorporates a pipeline with imputation to effectively manage any missing data points.

## Novelties

While predicting stock trends is a common application of machine learning, this project stands out because of:
*   **Tailored Feature Set:** The unique combination of rolling mean ratios and trend indicators across different time frames is designed to capture market dynamics at various scales.
*   **Strict Time Series Cross-Validation:** The focus on `TimeSeriesSplit` is an important best practice that is often overlooked. It offers a more reliable assessment of the model's predictive strength in real-world trading scenarios.
*   **Direct Comparison of Ensemble Methods:** A clear comparison between Random Forest and XGBoost, two effective ensemble techniques, sheds light on their relative efficiency for this specific task.

## Results

The models showed very strong performance in predicting the direction of the NASDAQ open price during the backtesting period.

*   **Random Forest:** Achieved precision scores between **0.9981 and 1.0** and accuracy scores from **0.9590 to 1.0** across the 5 cross-validation folds.
*   **XGBoost:** Achieved precision scores between **0.9965 and 1.0** and accuracy scores from **0.9981 to 1.0** across the 5 cross-validation folds.

The **consistently high precision scores (up to 1.0)** are especially impressive, indicating that when the models predict an upward movement, they are very reliable. XGBoost performed slightly better in the first cross-validation fold, while both models did well in the following folds.

These results strongly suggest that the features created and the models selected are effective in identifying potential short-term trends in the NASDAQ open price within this evaluation framework.

## Technologies Used

*   Python
*   pandas
*   yfinance
*   scikit-learn
*   xgboost
*   matplotlib
*   seaborn
