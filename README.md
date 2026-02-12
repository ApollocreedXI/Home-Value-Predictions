# Home Value Prediction
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/eb7efed7-85c9-41da-8a71-f87dc1231525" />

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

## Introduction
As an investor, it is crucial to have tools to analyze and detect undervalued real estate properties. A model that can predict a home's value can assist in ROI calculations for undervalued homes, aiding in the decision-making process. Such a model will improve the due diligence process of property assessment and mitigate the risks of tying up capital in homes with low ROI.

In addition, it is profoundly insightful to utilize modeling techniques to understand the features that are drivers of a property's value. Every market or area is different, and for a property rehabilitation investor, such knowledge is crucial. It will allow for efficient resource allocation to the features that will increase the value of the home the most. For example, if central air conditioning is found to be a significant feature in a home's valuation, it might be wise to consider adding this to an investment property that does not contain it.
This project will be centralized on the following two research questions

Research question 1: What features are most important to a property's valuation?

Research question 2: How accurately can a property's price be predicted?

## Main methods used
Pandas was utilized for data preprocessing, cleaning, and transformation. This preprocessed data was later utilized for exploratory data analysis (EDA). This allowed for visualization of data anomalies that would adversely affect modeling, and to take any appropriate action (e.g., mean imputation, drop record). During the EDA, the rich categorical data was utilized for data profiling, such as gathering insights into the median sales prices by neighborhoods. After EDA, the data was modeled using a regularized linear model to produce a sparse output of the most important features for sale price prediction, along with a trained model to predict home sales price.

## Summary of findings
The performance metrics of the project model demonstrated strong accuracy in predicting a home's value. 

The trained model on the dataset reveals that the overall quality and the ground living area of a home are significant predictors of a home's value. This makes intuitive sense as homes with larger living spaces and of higher quality will end up costing more.
The model reveals that the location of a home impacts the value of the home. In our exploratory analysis, we found that different neighborhood median home sale values can vary significantly.  The lasso regression does support these findings in our initial exploratory analysis.

The regression model reports that homes in certain neighborhoods reduce the value of a home. This could raise ethical concerns if one uses these features to guide them into selecting which neighborhoods to invest in and which ones to avoid. From a long-run utilitarian perspective, we would find that an investor's utilization of the model will not maximize the general public utility. Investors will allocate resources to invest in those areas where the model predicts overall high values. This will improve the homes of those who already live in better neighborhoods while neglecting the homes of other neighborhoods. The outcome of this is very dire and is similar to that of redlining. A proposed solution is to constrain the model somehow so that it cannot produce negative coefficients for neighborhood features. This solution allows an investor to understand which areas typically have a home of higher value, while not directly deterring an investor from neighborhoods that could potentially have negative regression coefficients.


## Other Key findings 
<img width="2076" height="1326" alt="image" src="https://github.com/user-attachments/assets/e8ef988f-b247-4078-9f0e-c95d662c2816" />

The boxplot reveals that there is significant variation in the neighborhood sale prices given by the IQR of the box plots. For example, the 'Nridght' neighborhood whiskers span from 150,000 to what appears to be 550,000. The center 50% of the data is contained between 250,000 to 375,000. Other neighborhoods such as 'Gilbert' have very narrow variation in price. 

<img width="1244" height="836" alt="image" src="https://github.com/user-attachments/assets/df8e8b11-191b-444b-96f5-f07d1adde967" />

The quality of the property has a significant impact on the average home sale price. The ground living area has a great linear relationship with the sales price with very few points of high leverage (unusual in terms of's). The sales price of a home seems to be very sensitive to increases in lot area. 



## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         home_value_prediction and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
└── setup.cfg          <- Configuration file for flake8
```
## Reproducibility 
1.	Create a virtual environment
2.	Download the project dependencies via the requirements.txt file in this repository
3.	Download the Ames Iowa Housing Data - https://github.com/topepo/AmesHousing
4.	Place the data in a repository that can be referenced by jupyter notebook.
5.	Download the notebook 
6.	Open the notebook and change the “pd.read_csv()” to read the data from your designated repository
7.	Run the remainder of the code

--------

