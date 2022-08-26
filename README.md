# Dealing with Sensitive Features

## Introduction

## Objectives

You will be able to:

* Define protected characteristics and sensitive features
* Describe the ethical considerations surrounding sensitive features
* Explain why the Ames Housing dataset is preferable to the Boston Housing dataset

## Protected Characteristics

Governments around the world as well as the United Nations have recognized that certain groups of people should be afforded a special "protected" status. Protected groups are members or minority and/or marginalized populations based on ***protected characteristics***.

In the United States, for example, these characteristics have been defined at the federal level via the Equal Pay Act of 1963, Civil Rights Act of 1964, Americans with Disabilities Act of 1990, and other laws and executive orders. Those laws [prohibit discrimination](https://content.next.westlaw.com/practical-law/document/Ibb0a38daef0511e28578f7ccc38dcbee/Protected-Class) on the basis of race, religion, national origin, age, sex, disability status, and veteran status. Some U.S. states, such as New York, have laws that cover a [wider range of protected classes](https://www1.nyc.gov/site/fairhousing/rights-responsibilities/what-are-the-protected-classes.page) for certain areas such as housing.

### Two Types of Discrimination Based on Protected Characteristics: Disparate Treatment and Disparate Impact

From a [legal perspective](https://rayneslaw.com/what-is-the-difference-between-disparate-impact-and-disparate-treatment-discrimination/), discrimination based on protected characteristics can include both ***disparate treatment*** (practices that intentionally treat people unequally) and ***disparate impact*** (practices that treat people unequally regardless of intent). In other words, practices do not have to be intentionally discriminatory to be considered illegal discrimination.

As a data professional, you might not have a legal obligation not to discriminate against protected classes in your analyses, but you still have an ethical obligation not to do so.

## Sensitive Features

The category of ***sensitive features*** is broader than protected characteristics and tends to be more culturally-specific. There is no specific legal definition of a sensitive feature, but it is generally understood to include protected characteristics, personally-identifiable information (PII), and other characteristics with privacy protections such as health data ([HIPAA](https://www.hhs.gov/hipaa/index.html)) or payment card data ([PCI](https://www.pcisecuritystandards.org/)).

### Risk of Discrimination

If sensitive features are included in your data analysis, you may be discriminating against people based on those features. This can happen with data visualizations, descriptive statistics (such as correlation), inferential statistics, and predictive models!

The best way to avoid this is to consider whether the sensitive features should be included in your analysis, and to consult with domain experts and members of protected groups as much as possible.

### Fairness Criteria

On the other hand, there can be downsides to excluding sensitive features from datasets. Without information about those features, it can actually be difficult to determine whether the analysis is discriminatory! There is an emerging field of AI fairness which specifically uses sensitive features to test for disparate impact in machine learning models. Check out the [Wikipedia page](https://en.wikipedia.org/wiki/Fairness_(machine_learning)) for longer explanations of some of the mathematical techniques being used.

### Proxies

Another concern to consider is that some features might not initially appear to be sensitive, but are actually highly correlated with a sensitive feature. For example, in the United States, geography is highly correlated with racial demographics.

Considering this, a credit card company that uses zip code as a factor to decide how creditworthy an applicant is may end up unintentionally exhibiting racial discrimination.

## Case Study: The Boston Housing Dataset

Many data science examples tend to return over and over again to "classic" datasets, many of which can be found on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets.php) or [Kaggle](https://www.kaggle.com/datasets). Some of these datasets are even built in to Python packages like [Seaborn](https://seaborn.pydata.org/generated/seaborn.load_dataset.html), [StatsModels](https://www.statsmodels.org/dev/datasets/index.html), and [scikit-learn](https://scikit-learn.org/stable/datasets/toy_dataset.html).

One of these datasets, which is currently built in to scikit-learn, is the [Boston Housing](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_boston.html) dataset. It contains data from a [1978 paper](https://www.researchgate.net/publication/4974606_Hedonic_housing_prices_and_the_demand_for_clean_air) that attempted to model the amount that people were willing to pay for cleaner air near their homes.

These are the features listed in the Boston Housing dataset:

* `CRIM`: per capita crime rate by town
* `ZN`: proportion of residential land zoned for lots over 25,000 sq.ft.
* `INDUS`: proportion of non-retail business acres per town
* `CHAS`: Charles River dummy variable (= 1 if tract bounds river; 0 otherwise)
* `NOX`: nitric oxides concentration (parts per 10 million)
* `RM`: average number of rooms per dwelling
* `AGE`: proportion of owner-occupied units built prior to 1940
* `DIS`: weighted distances to five Boston employment centres
* `RAD`: index of accessibility to radial highways
* `TAX`: full-value property-tax rate per &#36;10,000
* `PTRATIO`: pupil-teacher ratio by town
* `B`: 1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town
* `LSTAT`: % lower status of the population
* `MEDV`: Median value of owner-occupied homes in &#36;1000's

Do you notice any that correspond to protected characteristics?

The feature that has caused controversy in recent years is the **"B" feature**. It contains dated language referring to Black people as "blacks", seems like a questionable feature to include when 1970s Boston had relatively few Black people, and has this strange quadratic transformation applied to it.

Data scientist M Carlisle investigated that quadratic transformation in [this Medium post](https://medium.com/@docintangible/racist-data-destruction-113e3eff54a8) and found that it both destroyed some data (because it was a non-invertible transformation) and that it appears to be based on a since-disproven racist hypothesis of housing prices based on "self-segregation". This investigation led to the [deprecation](https://github.com/scikit-learn/scikit-learn/issues/16155) and planned removal of the dataset from scikit-learn.

Others such as data scientist [Martina Cantaro](https://medium.com/@docintangible/racist-data-destruction-113e3eff54a8) have noted that the "B" feature is not the only problem with the Boston Housing dataset. The prices and geographic regions are outdated, there are [major mistakes in the target column](https://spatial-statistics.com/pace_manuscripts/jeem_ms_dir/pdf/fin_jeem.pdf), and some values are artificially capped at &#36;50k. The original paper's analysis has also not stood up to recent [revalidation efforts](https://openjournals.wu.ac.at/region/paper_107/107.html).

For all of these reasons, data professionals and educators such as [Colleen Crangle](https://www.linkedin.com/pulse/its-time-retire-boston-housing-dataset-colleen-e-crangle/) have said "It’s time to retire the Boston Housing data set". Nowadays the preferred housing prices dataset for educational purposes is the [Ames Housing dataset](https://www.kaggle.com/datasets/prevek18/ames-housing-dataset), which was published with the paper [*Ames, Iowa: Alternative to the Boston Housing Data as an End of Semester Regression Project*](http://jse.amstat.org/v19n3/decock.pdf). This dataset is larger and messier than the Boston Housing dataset and also avoids some of its thorny ethical issues.

## Summary
