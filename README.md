# Dealing with Sensitive Features

## Introduction

As you learn how to tackle larger and more complicated datasets, it is important to consider the ethical implications of certain types of features. After going through some definitions of terms like "protected characteristics" and "sensitive features" this lesson will dive into a case study of the ethical problems with the widely-used "Boston Housing" dataset.

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

## Summary

Protected characteristics come from legal protections against discrimination, and include categories of age, race, sex, etc. In many circumstances it is illegal to treat people unequally based on these characteristics, regardless of whether it is intentional (disparate treatment) or unintentional (disparate impact). Sensitive features form a broader category that includes protected characteristics as well as PII and other forms of personal data. Data professionals should be careful when working with sensitive features as well as their proxies. This includes educational contexts, where there is a movement away from ethically dubious datasets such as the Boston Housing dataset and towards alternatives such as the Ames Housing dataset.
