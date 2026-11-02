# econ3916-lab12-ols-prediction
# OLS as a Line of Best Fit: Estimation versus Prediction

## Objective
I explored how ordinary least squares regression functions simultaneously as a tool for structural parameter estimation and out-of-sample prediction using California census data.

## Methodology
* Fitted the exact same OLS line three separate ways using the closed-form formula, `statsmodels`, and `scikit-learn` to confirm identical coefficients and intercepts.
* Added up to 100 columns of pure random noise to a regression model to examine how standard R-squared behaves compared to adjusted R-squared.
* Split the dataset into training and testing subsets prior to model training to evaluate an eight-feature model on unseen data.
* Utilized a single regression specification for two distinct economic jobs: estimating parameter confidence intervals and calculating test RMSE.
* Developed a custom function, `holdout_rmse()`, to score custom feature lists on consistent test rows and tested it using median income alone.
* Conducted the take-home challenge by quantifying and removing districts capped at the 5.0 outcome ceiling.

## Key Findings
* **Slope:** 0.4179
* **R-squared:** 0.4734 with no noise, rising to 0.4758 with 100 noise columns
* **Model Errors:** Train RMSE was 0.7197 and test RMSE was 0.7456 for the eight-feature model
* **Room Coefficient:** The `AveRooms` coefficient was -0.0381 with a 95% confidence interval of [-0.0430, -0.0333]
* **Single Predictor Performance:** Test RMSE using median income alone was 0.7482
* **Ceiling Challenge:** Dropping the 990 districts sitting at the 5.0 valuation ceiling removed artificial truncation, altering the slope and improving test RMSE
