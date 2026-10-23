# econ3916-lab12-ols-prediction
# OLS as a Line of Best Fit: Estimation versus Prediction

## Objective

The objective of this lab was to understand how OLS regression can be used for both estimation and prediction, and how different methods of evaluating a model can lead to different conclusions.

## Methodology

- I used the California Housing dataset to fit the same OLS regression line using three methods: the closed form, statsmodels, and scikit-learn.
- I added up to 100 columns of random noise to examine how R-squared and adjusted R-squared respond to additional variables.
- I split the data into training and test sets before fitting an eight-feature regression model, then compared its performance on both sets.
- I used the same regression specification for estimation and prediction, examining the coefficient and its 95% confidence interval alongside the test RMSE.
- I created a function called `holdout_rmse()` to calculate test RMSE using different predictors, including median income alone.

## Key Findings

- All three OLS methods produced the same intercept of 0.450856 and slope of 0.417938, confirming that each method gives the same regression results.
- R-squared increased from 0.4734 with no noise variables to 0.4758 with 100 noise variables, while adjusted R-squared decreased from 0.4734 to 0.4732. This showed me that adding more variables can improve R-squared without necessarily improving the model.
- The eight-feature model had a training RMSE of 0.7197 and a test RMSE of 0.7456, suggesting that the model performed similarly on both sets of data.
- The AveRooms coefficient was -0.0381, with a 95% confidence interval of [-0.0430, -0.0333]. Although the coefficient was statistically significant, the two-feature model still had a test RMSE of 0.8379.
- Using median income alone resulted in a test RMSE of 0.8421, compared to 0.7456 with all eight features. This represents approximately $9,650 in additional prediction error when using only median income.

Overall, this lab helped me understand that a model fitting the existing data well doesn't necessarily mean it will make accurate predictions. Comparing performance on unseen test data provides a better way to evaluate how well a model predicts new observations.
