# Dealing with Sensitive Features

* What are sensitive features
* How to work with sensitive features
* Why fairness can’t be unaware
* Features proxies

One of the reasons achieving fair ML models is difficult is because models that are unaware of sensitive features *(like race and gender) can still perpetuate discrimniation, despite the intention of data science teams. 

Sensitive features are attributes that hint that a data point represents a legally protected group or a proxy for legally protected groups. Sensitive attributes are usually easy to spot, they often represent demographic  groups, but proxies for sensitive features can be a bit more nefarious. For example, in the United States, geography is highly correlated with racial demographics. 

Considering this, a credit card company that uses zip code as a factor to decide how credit “worthy” and applicant is may end up unintentionally exhibiting racial discrimination. 

Legally protected classes
There are various laws that set precedent for enforcing certain levels of fairness for applications in finance and other heavily regulated fields. The Civil Rights Act of 1964 
prohibits discrimination on the basis of race, color, religion, sex or national origin. Requiiring that organizations aren’t discriminatory requires a federal defininition of discrimination. 

Formally, United States labor law refers to disparate impact in practices like housing and employment that adversely affect one group of people who share a protected characteristic in common. Disparate impact is a legal theory, with adverse impact as one part of the Title VII of the 1964 Civil Rights Act. Adverse impact refers to "substantially different rate of selection in hiring, promotion, or other employment decision which works to the disadvantage of members of a race, sex, or ethnic group". 

While fairness testing requires access to features that are sensitive attributes, it’s common data science teams don’t have this information to start testing models for fairness. 
