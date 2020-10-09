# Project Overview:

In this project, I am trying to understand the results of an A/B test run by an e-commerce website. The company has developed a new web page in order to try and increase the number of users who "convert," meaning the number of users who decide to pay for the company's product. My goal is to work through this notebook to help the company understand if they should implement this new page, keep the old page, or perhaps run the experiment longer to make their decision.

# My approach -- Sampling distribution, Bootstrapping, and Regression

I started off by creating the following hypotheses.
> Null: conversion rate of the old page is the same or better than the new page.
> Alternative: conversion rate of the old page is lower than the new page.

Next, I performed a sampling distribution for the difference in conversion rates between the two pages over 10,000 iterations using the bootstrap method. I then located the sample mean in the distribution and derived a 90.20% p-value, which is higher than the Type I error rate of 5%, meaning that we fail to reject the Null hypothesis. In plain words, it means that we don't have sufficient evidence to prove that the new page's conversion rate is better than the old page.

Furthermore, I performed a logistic regression model to try to fit the model using an intercept variable and a dummy ab_page variable (0 represents old page and 1 represents new page). Next, I observed a p-value of 0.190 from the model for the ab_page variable, which is larger than the 5% Type I error rate. The null hypothesis here is -- the population slope associated with the landing page (varaible ab_page) in relating to converted (whether the user converts or not) is zero. Having a large p-value means that we fail to reject this null hypothesis, meaning that landing page is not statistically significant for predicting conversions.

Last but not the least, I investigated if country had an impact on conversion. Again I was seeing large p-values (>5%). All p-values are higher than 0.05. As a result, none of the variables are statistically significant enough to predict the conversion. As a result, we fail to reject the null again. 

# Conclusion for the company:
The company should not implement the new pages and should keep the old page. There are not sufficient evidence that the new page is doing better.

