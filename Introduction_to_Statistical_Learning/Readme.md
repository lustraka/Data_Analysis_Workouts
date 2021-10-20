# An Introduction to Statistical Learning by Gareth James et al.
Statistical learning refers to a vast set of tools for understaning data. 

![check-In](https://www.plantuml.com/plantuml/png/XLHDRziu4BtdLynHWjPP9ESao6xM2nZeeUX74Q1gZ14vYWQLI9Ma71kk_tj9IfJjj4KlYJZp-DxCcw7lhKFZEbQom_wYWDMRzwLwQ4XyNQpKHL70VrIp8d0DGMzqrL8NelyEtCfIXQX4XvQSZnPmqw5hxlhYwkRl-0KRD8p-aWtfOfq0AUrbgIV_HpdONC9tBq6IXTF6-aDDw0P3_dEwztYRbHiI--rXVLL-6r2cq_Lu4b8xUvReyqdgJ7ykxvMwr-grikG_7PfdShDovDiTJiYcX4fKkh9aDkZO4wHB-soxvhzWj-QyFAptV7jrU5973lXWa1LaDRjyzBBJajh8_e-rGqVdwhTrzfWN9VMMMwrEQrbQn_uqunjq0H__rmT_wzo5jwFBv-Xpo7BRjx6ubQh9vAVGEa61B-aoReQXTkoyuNuYUD1TnOhIH7qIK4dWG4TAKEX_kS5sSFIwTwzDmf64a2RGDLW_K-C3P8msjbHZDSjiCcOnjP0_NK-bbIf3uGPi9uv5gYEnvh5CU4To45oroRdFmUB5qRSlCsF45_0fBBGIizEEjcxlWuTVU-rV2gDDv2CwH0w_bO2LCNDHhqMoDFnJaM1rZuQW8zTecPxQN2ahOGWjMNXXrq3TqfOhRjdj9cGiKT8VKF-pae2Jo0Ygj6lY_3T92vMCWJImAdPVtRNw9QqrMHiXACHWK8pqOSWqBR44tmrw7J9ZBrvyK87fD3N38Ui8LTmIxFgMrJD8jivmDOIjonE5TQWackCIeRLQi6SOkodLpzoJlhyjjAfPqkYdX_WbEYQRNU-T8CiMNBYgdkUcJZSRFbew1Y3Z-BGkxad9wGVu1m00)

## Contents
1. Introduction [[IPYNB](https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Introduction_to_Statistical_Learning/ISL01_Introduction.ipynb)]
2. Statistical Learning [[IPYNB](https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Introduction_to_Statistical_Learning/ISL02_Statistical_Learning.ipynb)]
3. Linear Regression [[IPYNB](https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Introduction_to_Statistical_Learning/ISL03_Linear_Regression.ipynb)]
4. Classification
5. Resampling Methods
6. Linear Model Selection and Regularization
7. Moving Beyond Linearity
8. Tree-Base Methods
9. Support Vector Machines
10. Deep Learning
11. Survival Analysis and Censored Data
12. Unsupervised Learning
13. Multiple Testing

## Data Stories
- [Advertising](https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Introduction_to_Statistical_Learning/DataStory_Advertising.ipynb)
- [Advertising](DataStory_Advertising.ipynb)

## References:
- Gareth James, Daniela Witten, Trevor Hastie, Robert Tibshirani (20210729) An Introduction to Statistical Learning: with Applications in R (Springer Texts in Statistics), 2nd Edition (ISL)
- [ISL Book Website](https://www.statlearning.com/)
- [ISL EdX On-Line Course](https://learning.edx.org/course/course-v1:StanfordOnline+STATSX0001+1T2020/home)
- [Ted Petrou: Introduction to Statistical Learning with Python](https://github.com/tdpetrou/Machine-Learning-Books-With-Python/tree/master/Introduction%20to%20Statistical%20Learning)
- [LaTeX/Mathematics](https://en.wikibooks.org/wiki/LaTeX/Mathematics#Adding_text_to_equations)
- [Latex Codecogs](https://www.codecogs.com/latex/eqneditor.php)

## Math Rendering
All these expression works in IPYNB (even in HTML from `nbconvert`) but are not rendered properly when displayed on GitHub...

$$\begin{array}{}
E(Y - \hat{Y})^2 &= E[f(X) + \epsilon - \hat{f}(X)]^2 \\
&= \underbrace{[f(X) - \hat{f}(X)]^2}_\text{Reducible} + \underbrace{\text{Var}(\epsilon)}_\text{Irreducible}, \qquad (3)
\end{array}$$

$$\begin{matrix}
E(Y - \hat{Y})^2 =& E[f(X) + \epsilon - \hat{f}(X)]^2 \\
\qquad =& \underbrace{[f(X) - \hat{f}(X)]^2}_\text{Reducible} + \underbrace{\text{Var}(\epsilon)}_\text{Irreducible}, \qquad (3)
\end{matrix}$$

$$E(Y - \hat{Y})^2 = E[f(X) + \epsilon - \hat{f}(X)]^2 = \underbrace{[f(X) - \hat{f}(X)]^2}_\text{Reducible} + \underbrace{\text{Var}(\epsilon)}_\text{Irreducible}, \quad (3)$$

![expresstion](http://latex.codecogs.com/gif.latex?E(Y-\hat{Y})^2=E[f(X)+\epsilon-\hat{f}(X)]^2=\underbrace{[f(X)-\hat{f}(X)]^2}_\text{Reducible}+\underbrace{\text{Var}(\epsilon)}_\text{Irreducible},\qquad(3))

<!--
@startmindmap
+ ILS\nCheck-In
++ Define the problem
++ Build\nthe dataset
+++ <math>p+1</math> variables
++++_ <math>p</math> independent v. | predictors | features | <math>X=(\vec{x}_1\quad\vec{x}_2\quad\cdots\quad\vec{x}_p)</math>
++++_ <math>1</math> dependent v. | response | target | <math>\vec{y}</math>
+++ <math>n</math> observations <math>\{(x_i, y_i)\}_{i=1}^n</math>
++ Train (fit)\nthe model
+++ Assume <math>\vec{y}=f(X)+\epsilon</math>
+++ Estimate <math>\hat{y}=\hat{f}(X)</math>
++++_ Predict <math>\hat{y}</math>
++++_ Explain (Infer) <math>\hat{f}</math> i.e. the relationship
++++_ Combine prediction and inference
++ Evalute\nthe model
+++ Expected value of squared errors\n<math>E(\vec{y}-\hat{y})^2</math>\n(actual value - predicted value)
++++ Reducible <math>[f(X)-\hat{f}(X)]^2</math>
+++++ Variance <math>\text{Var}\hat{f}(X)</math>
+++++ Bias <math>[\text{Bias}\hat{f}(X)]^2</math>
++++ Irreducible <math>\text{Var}(\epsilon)</math>
+++ Compare methods
++++_ Variance increases with flexibility
++++_ Bias decreases with flexibility
++++_ Find a method with both the variance and the squared bias <b>low
+++ Assess the accuracy
++++ of estimated parameters
+++++_ unbiased parameter estimate (mean of sampling distribution)
+++++_ standard errors\nassociated with\nparameter estimates
++++++_ confidence intervals
++++++_ hypothesis testing
++++ of the model
++ Use the model (infer)
@endmindmap
-->
