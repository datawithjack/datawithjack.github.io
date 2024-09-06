---
layout: post
title: Masters Thesis
description: >
  A page showing Hydejack-specific markdown content.
image: /assets/img/blog/example-content-iii.jpg
sitemap: false
---

# Different Slopes for Different Folks: Using Linear Mixed Models to Prediction High Jump Performance

In athletics, predicting future performance (and ultimately success) is a challenge that has long intrigued athletes, coaches, national federations and statisticians alike. My master's thesis delved into this very topic, exploring how statistical models, namely linear mixed models (LMMs), can be used to (attempt to) predict high jump performance over time.

The following article aims to give a brief overview of how and why I applied a linear mixed model to the problem of predicting high jump performance in youth athletes and the iterative approach I took to finding and slecting the best model.

If you want to read the full thesis you can download it [here](https://raw.githubusercontent.com/datawithjack/masters-thesis/main/Jack-Andrew-Masters-Thesis.pdf).

## The Dataset

The dataset consisted of high jump results from over 6000 athlete all of which had 10 or more performances. The major of the data was scraped from the [World Athletics](https://worldathletics.org/) website and the UK's [Power of 10](https://www.thepowerof10.info/) website. 

## Exploratory Data Analysis (EDA)
An extensive exploratory data analysis was included building a R Shiny App (available [here]()) to explore the data.

The most important findings of the EDA were:

* **Repeated measurements** – some athletes have multiple observations (performances) over time.
* A **non-linear relationship** is evident between age and performance.
* **Hierarchical structures** are present - Athletes within countries, Athletes within Competitions, Competitions within Seasons.



## Selecting an a Modelling Approach

All the findings from the EDA ruled out linear regression models and pointed towars the use linear mixed models

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


