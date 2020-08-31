# Developer Type Job Satisfaction - Stack Overflow 2020 Developer Survey


## Installation

To run this code:

- Install the Anaconda distribution of Python 3.
- There are additional dependencies available via pip, so I recommend creating a new conda environment to make these pip installations and run the project notebooks:
  - `conda create --name so_dev_satisfaction`
- Install pydotplus (graphviz graph visualization)
  - `pip install pydotplus`
- Install CatBoost machine learning library and (optionally) SHAP for model explanation:
  - `pip install catboost shap`

Survey data and descriptions of the survey can be downloaded at the 2020 "Download Full Dataset (CSV)" link from this page: https://insights.stackoverflow.com/survey/.

## Project Description

This project explores job satisfaction among different developer types, using data from Stack Overflow 2020 survey [1]. This project has **two main purposes**.

**First**, to explore the impact of software developer role types on job satisfaction. This exploration was guided by these questions:

1. What is the magnitude of the effect of developer role types on job satisfaction compared to other factors?
2. How do developer roles compare to one another in the job satisfaction reported in the survey?
3. Are the reported differences in job satisfaction among developer roles statistically significant?

**Second**, to explore novel visualizations to allow end users to make their own comparisons of the mean satisfaction among the subsets of developer type type categories that they choose. This addresses a common problem, as noted in the 1993 paper by Goldstein and Healy [2]:

> When a study produces estimates for many units or categories a common problem is that
> end-users will wish to make their own comparisons among a subset of these units. 

The added visualizations include, first, a significance relation digraph paired to a bar chart. An edge in the digraph from **A** to **B** indicates that the estimate for **A** is greater than the estimate for **B**, and the difference is significant at the chosen level.

![ac_graph_reduced](./images/ac_graph_reduced.png)	

![ac_cluster_bar_chart](./images/ac_cluster_bar_chart.png)

The second visualization is a one-to-many p-value comparison plot. The examples below show comparisons of mean job satisfaction difference p-values between one developer type and the rest. Reciprocal p-values are shown so that larger bars indicate greater significance. A bar above the bottom dotted line indicates significance at the 0.05 level; above the top dashed line indicates significance at the 0.01 level. A **red** bar indicates that the dev type in the title has a significantly **lower** mean satisfaction score; **green** indicates significantly **higher**.

![level_2_misfits](images/level_2_misfits.png)

## File Descriptions

- `Predict JobSat.ipynb` Creating a regression model to assess the magnitude of the effect of developer role types on job satisfaction.
- `DevType Comparison.ipynb` Comparisons of job satisfaction among developer type roles.

## Results

The main findings of the code can be found at the post available [here](https://medium.com/@rick.froom/software-developers-who-has-it-better-3dfc4646e207).



## References

[1] https://insights.stackoverflow.com/survey/

[2] Harvey Goldstein and Michael J. R. Healy, "The Graphical Presentation of a Collection of Means," Journal of the Royal Statistical Society. Series A (Statistics in Society) Vol. 158, No. 1 (1995), pp. 175-177. https://www.jstor.com/stable/2983411



## Acknowledgements

In the `Predict JobSat.ipynb` notebook, I used donut chart styling ideas from: https://medium.com/@kvnamipara/a-better-visualisation-of-pie-charts-by-matplotlib-935b7667d77f