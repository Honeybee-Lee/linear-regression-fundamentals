# Linear Regression Fundamentals: Bridging Theory and Practice, Part 1

Linear regression is a fundamental statistical technique to understand the relationship between two continuous variables. It works on the principle of fitting a straight line through a set of data points to model the relationship between the independent variable (predictor) and the dependent variable(s) (outcome).
This topic isn’t always taught in depth to working professionals or anyone that hasn’t had rigorous mathematical training. So, in a series of posts I will go over in depth some of the fundamental concepts of linear regression.
## Fundamental Assumptions
However, for linear regression to provide reliable insights, it relies on several key assumptions:
1. Linearity: The relationship between the variables should be approximately linear. This means that changes in the outcome variable are proportional to changes in the predictor variable.
2. Independence: Each data point should be independent of other data points. In other words, there should be no correlation between the residuals (the differences between observed and predicted values).
3. Homoscedasticity: The variance of the residuals should be constant across all levels of the predictor variable. This assumption ensures that the model is equally precise in predicting outcomes regardless of the values of the predictor.
4. Normality of Residuals: For this assumption to be met, the residuals are normally distributed around zero. This means that the errors or the differences between the observed and predicted values should follow a bell-shaped curve.
5. No Multicollinearity: In multiple regression (with more than one predictor variable), there should be no high correlation among the predictor variables. High multicollinearity can lead to unreliable estimates of the coefficients.
Meeting these assumptions is crucial for the validity and accuracy of the results obtained from linear regression analysis. When we violate these assumptions, the reliability of the model’s predictions may be compromised, and alternative approaches or transformations might be necessary.
Let’s touch on each assumption of linear regression, and state the ways to check for violations and potential adjustments if these assumptions are not met:
Linearity
	• Check: Plotting the scatterplot of the dependent variable against each independent variable helps assess linearity visually. If the relationship appears nonlinear, a curved trend might indicate a violation.
	• Adjustment: Transforming variables by taking logarithms, squares, or higher-order terms (e.g., quadratic or cubic terms) might help linearize the relationship.

Example of plotting the dependent variable against each independent variable to assess the linearity assumption. Which in this case, there appears to be a violation of the assumption due to nonlinearity.
Independence
	• Check: The Durbin-Watson test or examining residual plots over time (in time series data) can reveal autocorrelation or dependency among residuals.
	• Adjustment: Consider using time series analysis techniques for temporal dependencies or reevaluating the data collection method to ensure independence.
Homoscedasticity
	• Check: Plotting residuals against fitted values helps visualize whether the spread of residuals is consistent across all values of the predictor variable.
	• Adjustment: Performing transformations on the dependent variable (e.g., logarithmic transformation) or using weighted least squares regression can address heteroscedasticity.

Example of a plot of the residuals against the fitted values to visualize if the spread is constant. Generally, we want to see randomness, like above.

Example of residual plot that clearly violates the assumption, due to the non-linear pattern of the above.
Normality of Residuals
	• Check: Histograms or QQ-plots of residuals can indicate departure from normality.
	• Adjustment: Consider applying transformations on the dependent variable or using robust regression techniques that are less sensitive to non-normality.

Example of QQ-Plot of residuals to check assumption of normality
No Multicollinearity
	• Check: Calculating correlation coefficients among predictor variables helps identify multicollinearity. High correlation values (close to 1 or -1) indicate multicollinearity.
	• Adjustment: Remove one of the highly correlated variables, use principal component analysis, or employ regularization techniques like ridge regression or LASSO regression to handle multicollinearity.

Example of a correlation heatmap to assist with visually assessing the assumption.
If assumptions are significantly violated and adjustments don’t suffice, it’s essential to reconsider the model’s suitability for the data or explore alternative regression approaches like nonlinear regression, generalized linear models, or machine learning algorithms that are less sensitive to these assumptions. Additionally, collecting more diverse or additional data might also help address violations of these assumptions.
Uses of Regression
Regression models are used for several purposes, such as the following:
	1. Data description
	2. Parameter estimation
	3. Prediction and estimation
	4. Control
Data description: Professionals that frequently use data, such as engineers and scientists use equations to summarize or describe a set of data. Regression is a helpful tool in developing those equations. For example, we may collect a considerable amount of data noting delivery time and volume, and a regression model would probably be a much more convenient and useful summary of those data rather than a table or graph. It can help visualize the relationships between variables. It is a useful tool in the exploratory data analysis tool set, gathering summary statistics, or model building.
Parameter estimation: Consider, the Michaelis-Menten equation (right). Chemical engineers use this equation to describe the relationship between the velocity of reaction y and concentration x. In this model, B1 is the asymptotic velocity of the reaction. That is, the maximum velocity as the concentration gets large.

If a sample of observed values of the velocity at different concentrations is available, then the engineer can use regression analysis to fit this model to the data, and produce an estimate of the maximum velocity.
Prediction and estimation: Consider that we wish to predict delivery time for a specified number of cases of soft drinks to be delivered. These predictions may be helpful to plan delivery activities such as routing and scheduling. This use of regression for prediction has its potential risks, such as extrapolation. This term refers to inferring unknown values from trends in the known data.
Personally, I feel as though a lot of professionals in the industry fit a model, assume it is valid, and put a lot of weight into extrapolated predictions. But, even when the model form is correct, poor estimates of the model parameters may still cause poor prediction performance. It needs to be emphasized that most regression predictions should be done within the range of the data that the model was trained on (interpolation), and avoid extrapolation when possible. However, sometimes in industry, we may get a task from leadership that asks for extrapolated values. These results should be given with caution to the stakeholder, with some measure of confidence.
Control: Consider the example that an engineer could use regression to develop a model relating the tensile strength of paper to the hardwood concentration in the pulp. This equation could then be used to control the strength to suitable values by varying the level of hardwood concentration. When a regression equation is used for control purposes, it is important that the variables be related in a causal manner. Note that a cause-and-effect relationship may not be necessary if the equation is used only for prediction.
What’s Next?
Understanding these fundamental assumptions is absolutely essential to properly utilize regression analysis, and is the first step of many. This series is meant to introduce linear regression in the format we wish we had in school. We will discuss things we learned in class, as well as hard lessons-learned from real world experience.
