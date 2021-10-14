# An Introduction to Statistical Learning by Gareth James et al.
Statistical learning refers to a vast set of tools for understaning data. 
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
- [ISL On-line Course Video Archive](https://www.r-bloggers.com/2014/09/in-depth-introduction-to-machine-learning-in-15-hours-of-expert-videos/)
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
