# Dealing with Sensitive Features

## Introduction

## Objectives

You will be able to:

* Define protected characteristics and sensitive features
* Describe the ethical considerations surrounding sensitive features

## Protected Characteristics

Governments around the world as well as the United Nations have recognized that certain groups of people should be afforded a special "protected" status. Protected groups are members or minority and/or marginalized populations based on ***protected characteristics***.

In the United States, for example, these characteristics have been defined at the federal level via the Equal Pay Act of 1963, Civil Rights Act of 1964, Americans with Disabilities Act of 1990, and other laws and executive orders. Those laws [prohibit discrimination](https://content.next.westlaw.com/practical-law/document/Ibb0a38daef0511e28578f7ccc38dcbee/Protected-Class) on the basis of race, religion, national origin, age, sex, disability status, and veteran status. Some U.S. states, such as New York, have laws that cover a [wider range of protected classes](https://www1.nyc.gov/site/fairhousing/rights-responsibilities/what-are-the-protected-classes.page) for certain areas such as housing.

From a [legal perspective](https://rayneslaw.com/what-is-the-difference-between-disparate-impact-and-disparate-treatment-discrimination/), discrimination based on protected characteristics can include both ***disparate treatment*** (practices that intentionally treat people unequally) and ***disparate impact*** (practices that treat people unequally regardless of intent). In other words, practices do not have to be intentionally discriminatory to be considered illegal discrimination.

As a data professional, you might not have a legal obligation not to discriminate against protected classes in your analyses, but you still have an ethical obligation not to do so.

One of the reasons achieving fair ML models is difficult is because models that are unaware of sensitive features *(like race and gender) can still perpetuate discrimniation, despite the intention of data science teams. 

Sensitive features are attributes that hint that a data point represents a legally protected group or a proxy for legally protected groups. Sensitive attributes are usually easy to spot, they often represent demographic  groups, but proxies for sensitive features can be a bit more nefarious. For example, in the United States, geography is highly correlated with racial demographics. 

Considering this, a credit card company that uses zip code as a factor to decide how credit “worthy” and applicant is may end up unintentionally exhibiting racial discrimination. 

While fairness testing requires access to features that are sensitive attributes, it’s common data science teams don’t have this information to start testing models for fairness. 
