---
layout: post
title: Masters Thesis
description: >
  A page showing Hydejack-specific markdown content.
image: /assets/img/blog/example-content-iii.jpg
sitemap: false
---

# Different Slopes for Different Folks: Using Linear Mixed Models to Prediction High Jump Performance

In athletics, predicting future performance (and ultimately success) is a challenge that has long intrigued athletes, coaches, national federations and statisticians alike. My master's thesis delved into this very topic, exploring how statistical models, namely linear mixed models (LMMs), can be used to predict high jump performance over time.

The following article aims to give a brief overview of how and why I applied a linear mixed model to the problem of predicting high jump performance in youth athletes and the iterative approach I took to finding and slecting the best model.

If you want to read the full thesis you can download it [here](https://raw.githubusercontent.com/datawithjack/masters-thesis/main/Jack-Andrew-Masters-Thesis.pdf).

## The Dataset

The dataset consisted of high jump results from over 6000 athlete all of which had 10 or more performances. The major of the data was scraped from the [World Athletics](https://worldathletics.org/) website and the UK's [Power of 10](https://www.thepowerof10.info/) website. 

for modelling Given the size of the data it is computationally (and time) expensive to use all the data to explore what an appropriate functional form might be.   For this reason, a (random) sample of 50 athletes with over 90 observations was used to investigate various smoothing methods using solely age as the predictor of performance. ...however eda wasconducted on all data,

## Exploratory Data Analysis (EDA)
An extensive exploratory data analysis was included building a R Shiny App (available [here]()) to explore the data.

The most important findings of the EDA were:

* **Repeated measurements** – some athletes have multiple observations (performances) over time.
* A **non-linear relationship** is evident between age and performance.
* **Hierarchical structures** are present - Athletes within countries, Athletes within Competitions, Competitions within Seasons.

![EDA](https://raw.githubusercontent.com/datawithjack/datawithjack.github.io/main/assets/img/blog/eda-chart.jpg)
Non-linear relationship between age and performance (left) and repeated measurements per athlete (right).
{:.figcaption}
 

## Selecting a Modelling Approach

All the findings from the EDA ruled out linear regression models and pointed towars the use linear mixed models
Although this posed a challenge from a modelling perspective, all these technicalities can be accommodated nicely using the LMM framework.

The violations of independence rules out linear regression and opens the door to a LMM approach. This method offers a flexible framework by which to model the sources of variation and correlation that arise from grouped data (5) and also allows for the inclusion of smoothing methods (such as splines) to model non-linear functional forms.

LMM’s are an extension of a general linear model (GLM). 

The fixed effect part of the model contains the covariates of direct interest which, in this thesis, is the variable age. However, the dataset is rich and contained other fields such as venue, country, and year.  Whilst the estimated effect of these covariates is not of primary interest, the LMM approach allows for the effect of these covariates on the response to be accounted for by focusing purely on the variance they explain rather than on estimating their individual level effects.
In a general linear model these covariates would have to be added in as fixed effects which use up valuable degrees of freedom. The random effects part of the LMM gives the opportunity to include additional covariates to help explain the variance structure whilst using less degrees of freedom than estimating the effects of each covariate as a fixed effect.  This translates to less degrees of freedom being ‘spent’ in estimating unnecessary effects leaving the model with more power to test the covariate(s) of interested (age).
Random effects can be included in a LMM as either random intercepts or random slopes. Random intercepts account for variation where individuals are sampled repeatedly such athlete’s performance over time and random slopes account for variation in group responses or ‘within individual’ variation such as athletes from different countries improving at different rates.  An adjustment can be made to the model depending on whether the random effects are correlated (e.g., an intercept and a slope) or are independent (e.g., no relationship between an intercept and slope).
The EDA demonstrated that athletes had repeated measurements over time and that athletes from different countries improve at different rates suggesting both random intercepts (i.e., athlete within country) and random slopes (i.e., performance as age increases over time) are required.
To capture these effects in a linear regression model an interaction term would have to be included. For example, given the number of athletes in the dataset, the number of parameters used by this model would be excessively high especially considering that the direct effect of athlete/country is not of interest but rather how much of the variability in performance can be attributed to this.
If there is any between country variation or an age by country interaction then these terms cannot be ignored because systematic variation would end up in the residuals causing a potentially biased inference. To estimate model degrees of freedom more efficiently, a mixed effects model with a random intercept and a random slope can be applied.
Shielzeth and Forstmeier 2009 (7) suggest to always include both random slopes and intercepts when possible. Incorporating random intercepts and slopes collectively reduces the incidence of Type 1 and Type 2 errors and reduces the chance of overconfident estimates (unrealistically low standard error). However fitting random slopes requires relatively large sample sizes for model convergence, especially if the data set contains many groups with only a few observations (8). The dataset used in this thesis is large and therefore it is unlikely that convergence will be a problem.
Given the above, LMM’s are an attractive solution to model both the hierarchical structure present in the data and the serial correlation in each athlete’s performance over time by incorporating a random effect in order to model each athlete’s serial correlation in a flexible way (6).






## A note on Linear Mixed Models


## Building my Model




## The Journey Begins: Simple Linear Regression

The journey started with the basics—simple linear regression. This model is straightforward, where (quite naively) the relationship between an athlete's age and their high jump performance is assumed to be linear. While this method offers a clear and interpretable relationship, it falls short of capturing real-world complexities. Specifically, high jump performance (like many paths in life) does not follow a strict linear trend with athletes age; instead, it varies in a more complex, non-linear fashion.

## A Need for Complexity: Moving Beyond Linear Regression

Recognizing the limitations of simple linear regression, I explored more advanced methods that could accommodate the non-linear nature of the data. Polynomial regression offered a step forward by introducing non-linearity, yet it still imposed global structures that weren’t entirely realistic for every athlete.

This led to the exploration of smoothing techniques, like splines, which allow for more flexibility in modeling performance over time. However, even these methods had limitations when applied in a standard linear model framework.

## The Leap to Linear Mixed Models

The real breakthrough came with the introduction of Linear Mixed Models (LMMs). Unlike simple linear regression, LMMs can account for the hierarchical structure in the data—athletes nested within countries, repeated measures over time, and varying performance trends across different groups.

LMMs also allow for the inclusion of both fixed and random effects. In this case, age was treated as a fixed effect, while individual differences between athletes (random effects) were accounted for by including athlete-specific intercepts and slopes. Moreover, by incorporating splines within the LMM framework, the model could effectively handle the non-linear relationship between age and performance, capturing the nuances in each athlete’s progression.

## The Result: A Robust Predictive Model

The final model, a linear mixed model with B-splines at both the fixed and random effect levels, provided a much more accurate and nuanced understanding of high jump performance. It successfully accounted for the non-linear progression of athletes and the variability within and between different groups, making it a powerful tool for predicting future performance.

## Conclusion

This progression from simple linear regression to linear mixed models illustrates the importance of choosing the right statistical tools for the job. While simple models provide a good starting point, real-world data often demands more sophisticated approaches. In the case of high jump performance, linear mixed models offered the flexibility and precision needed to make meaningful predictions, potentially aiding coaches and athletic organizations in identifying and nurturing future stars.

something about the application of linear mixed models into other real world examples

Add photo of some young high jumper...definitely not me 

# other modelling approaches
machien learning


