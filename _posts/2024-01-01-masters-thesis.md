---
layout: post
title: Masters Thesis
description: >
  A page showing Hydejack-specific markdown content.
image: assets/img/blog/high-jump-blog-cover2.jpg
sitemap: false
---

# Different Slopes for Different Folks: Using Linear Mixed Models to Prediction High Jump Performance

In athletics, predicting future performance (and ultimately success) is a challenge that has long intrigued athletes, coaches, national federations and statisticians alike. My master's thesis delved into this very topic, exploring how statistical models, namely linear mixed models (LMMs), can be used to predict high jump performance over time.

The following article aims to give a brief overview of how and why I applied a linear mixed model to the problem of predicting high jump performance in youth athletes and the iterative approach I took to finding and selecting the best model.

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

The findings from the EDA ruled out linear regression models (violations of independence) and pointed toward the use of linear mixed models. This method offered a flexible framework by which to model the sources of variation and correlation that arise from grouped data (5) and also allows for the inclusion of smoothing methods (such as splines) to model non-linear functional forms.

## An Overview of LMMs

Linear mixed models (LMMs) build on general linear models (GLMs), which themselves are an extension of simple linear regression. LMMs can be split into two parts- a 'fixed effects' part and a 'random effects' part. 


The “fixed effects” part of the model focuses on the variables of direct interest, which in my case was age. However, the dataset also includes other variables like venue, country, and year. Even though we aren't particularly interested in these variables, LMMs can still take them into account by focusing on the overall variation they explain, rather than figuring out their specific effects.

In a regular GLM, you’d need to add these extra variables as fixed effects, which would take up more "degrees of freedom"— a resource that's valuable for ensuring the accuracy of your model. LMMs allow you to include these extra variables more efficiently as random effects, helping explain the variance in your data without using up as many degrees of freedom. This leaves the model with more power to focus on the main variable you're interested in— age.

Random effects in LMMs can be set up in two ways: random intercepts and random slopes. Random intercepts deal with variation when individuals (like athletes) are measured multiple times, and random slopes allow for differences between groups (like athletes from different countries) that might improve at different rates. You can also decide whether these effects (intercepts and slopes) are related or not.

My exploratory data analysis (EDA) showed that athletes had multiple measurements over time and improved at different rates depending on their country. This suggested the need for both random intercepts (accounting for the athlete within each country) and random slopes (to capture how performance changes with age). If you didn’t use random effects and just used a regular linear model, you'd need a lot more parameters, which would make the model unnecessarily complicated. Plus, you'd risk overlooking important variations in the data, which could lead to biased results.

To avoid this, using random intercepts and slopes in LMMs helps manage the complexity, reduces the chance of errors (like making wrong conclusions about the data), and prevents overconfidence in the results (like unrealistically low error estimates). However, fitting these random slopes requires a large dataset for the model to work properly. Fortunately, our your dataset was large so this wasn't a .

In summary, LMMs are a powerful tool for handling complex data, like yours, by accounting for both the hierarchical structure and repeated measurements over time (6).

References:

Schielzeth, H., & Forstmeier, W. (2009). Fitting linear mixed models.

If you're interested in some more of the details behind LMMs please take a look at look at my thesis.


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


