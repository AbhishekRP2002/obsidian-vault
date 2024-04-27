##### Linear Models VS Non-Linear Models
 In [statistics](https://statisticsbyjim.com/glossary/statistics/), a regression model is linear when all terms in the model are one of the following:
 - constant
 - a parameter multiplied by an independent variable(IV)
 - Dependent variable = constant + parameter * IV + … + parameter * IV
 - by linear we mean linear in params and to fit a curve model we can raise the power of IVs.For example, if you square an independent variable, the model can follow a U-shaped curve.

![Linear model with a quadratic term.](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2017/03/linear_model_quadratic_equation.png?resize=171%2C31&ssl=1)

- Linear models can also contain log terms and inverse terms to follow different kinds of curves and yet continue to be linear in the parameters.
- **If a regression equation doesn’t follow the rules for a linear model, then it must be a nonlinear model.**


##### Residual plots in Linear Regression
**Residual** - difference between the actual value and the predicted value wrt the dependent variable
- Residuals are the sample estimate of the error for each observation.Error is a population value.
- Residuals = Observed value – the fitted value
**Residual plot** - graphical representation of the residuals (errors) in a linear regression model. In simple terms, a residual plot shows how far off the predictions are from the actual data points.
- created by plotting the residuals on the vertical axis against the predicted values or independent variables on x axis.

##### Assumptions for Residuals in Linear Regression:
1. Residuals should be independent of each other.
2. Residuals should have constant variance.
3. The expected value or mean of the residuals should be zero. **E[ε]=0**
4. Residuals should follow a normal distribution

**Assumptions of OLS Linear Regression**:
- there is a linear relationship between the independent and the dependent variables
- The regression model is **linear in the coefficients and the error term.** the defining characteristic of linear regression is this functional form of the _parameters_ rather than the ability to model curvature. Linear models can model curvature by including nonlinear _variables_ such as polynomials and transforming exponential functions.
- population mean of the error term is 0
- all the independent variables are non correlated to the error term
- Observations of the error term are uncorrelated with each other i.e one obs error should not predict the next obs
- the error term has a constant variance ( no heteroscedasticity ) : The easiest way to check this assumption is to create a residuals versus fitted value plot. On this type of graph, heteroscedasticity appears as a cone shape where the spread of the residuals increases in one direction.
  1. Heteroscedasticity reduces the precision of the estimates in OLS linear regression. How exactly ?
- No independent variable should be a perfect linear function of other explanatory variables --> if the Pearson correlation is +1 or -1 between two variables then they are said to have a perfect correlation.
  Ordinary least squares cannot distinguish one variable from the other when they are perfectly correlated.
   ==Statisticians refer to this condition as multicollinearity, and it reduces the precision of the estimates in OLS linear regression.==
- 

**Why we need Residual Plots ?**
- helps us determine how good is the model fit. If the residuals are randomly scattered around the horizontal axis, it indicates that the model is a good fit. However, if there are visible patterns or trends in the residuals, it may suggest that the model is not adequately capturing the underlying relationship between the variables.
- If the residual plot shows a non-random pattern, such as a curve, it indicates that the relationship between the variables may be non-linear, and a non-linear model may be more appropriate for the data.
- helps us spotting outliers in the dataset : Outliers appear as points that are far away from the majority of the other residuals in the plot
- **Identifying Heteroscedasticity:** 
  1. what is heteroscedasticity : 

**Multicollinearlity:**
- situation in which independent variables in a regression model are correlated.
- A key goal of regression analysis is to isolate the relationship between each independent variable and the dependent variable.
- Multicollinearity affects [the coefficients and p-values](https://statisticsbyjim.com/regression/interpret-coefficients-p-values-regression/), but it does not influence the predictions, precision of the predictions, and the goodness-of-fit statistics. If your primary goal is to make predictions, and you don’t need to understand the role of each independent variable, you don’t need to reduce severe multicollinearity.
- Potential solutions to reduce high level multicollinearity:
  1. if the independent variables are large in number, you can think of removing highly correlated variables but before that check the feature importance
  2. Linearly combine the independent variables, such as adding them together.
  3. Partial least squares regression uses [principal component analysis](https://statisticsbyjim.com/basics/principal-component-analysis/) to create a set of uncorrelated components to include in the model.
  4. use L1 or L2 regularization as they can handle multicollinearity by penalizing the coefficients, reducing their values and also helping to handle overfitting

- understand selecting the correct type of regression analysis, specifying the best model, interpreting the results, assessing the fit of the model, generating predictions, and checking the assumptions.
- use **confidence intervals and p-value** to understand the responses
- Selecting the right type of regression analysis is just the start of the process. Next, you need to specify the model.Model specification is the process of determining which independent variables belong in the model and whether modeling curvature and interaction effects are appropriate.

##### Ordinal Regression
- somewhere between classification and regression


**1. Understanding Regression Analysis**  
- Definition of regression analysis  
- Types of regression analysis (Linear, Logistic, Polynomial, etc.)  
- Key concepts (independent variables, dependent variables, fitting a model)

**2. Linear Regression**  
- Concept and mathematical formulation  
- Assumptions of linear regression  
- Simple linear regression vs. multiple linear regression  
- Python and R code example using a publicly available dataset

**3. Logistic Regression**  
- Overview and when to use logistic regression  
- The mathematical model behind logistic regression  
- Interpreting the results (odds ratios, predictions)  
- Python and R code example using a publicly available dataset

**4. Other Types of Regression**  
- Brief overview of Polynomial, Ridge, Lasso, and Elastic Net Regression  
- When to use each type  
- Key differences and advantages  
- Python and R code examples for at least one type

**5. Model Evaluation and Selection**  
- Criteria for evaluating regression models (R-squared, AIC, BIC, etc.)  
- Overfitting vs. underfitting  
- Cross-validation techniques  
- Python and R code example demonstrating model evaluation

**6. Advanced Applications of Regression Analysis**  
- Forecasting and trend analysis  
- Regression in machine learning and artificial intelligence  
- Use cases in finance, healthcare, and environmental studies  
- Discussion on the integration of regression analysis with big data technologies

**7. Challenges and Considerations in Regression Analysis**  
- Dealing with non-linearity  
- Handling multicollinearity  
- Importance of data preprocessing  
- Ethical considerations in predictive modeling

[Reference 1: ](https://statisticsbyjim.com/regression/regression-tutorial-analysis-examples/)
[Linear Regression from Stats POV](https://statisticsbyjim.com/regression/)