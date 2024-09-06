---
layout: post
title: Masters Thesis
description: >
  A page showing Hydejack-specific markdown content.
image: assets/img/blog/high-jump-blog-cover.jpg
sitemap: false
---

# Different Slopes for Different Folks: Using Linear Mixed Models to Prediction High Jump Performance

add TOC
### Introduction
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

#### Handling Non Linearity

This chapter explores different methods to model non-linear relationships in data, focusing on how age affects athletic performance. We start with simple methods like polynomial regression and step functions, but these have limitations. Therefore, more advanced methods like splines are introduced, which are better at fitting complex, non-linear data.

Since testing all these methods on the entire dataset would be very time-consuming, a random sample of 50 athletes was used to investigate different smoothing methods, starting with age as the key factor influencing performance.

Polynomial Regression: This method extends regular linear models by adding powers of age (like age² or age³) to the model. It helps capture non-linear patterns. In this case, both second-degree and third-degree polynomial models were tested, but neither fit the data perfectly, as shown by the R² values (which indicate how well the model explains the data). The third-degree polynomial did slightly better but still wasn’t great.

Step Functions: This method breaks age into different ranges (or “bins”) and assumes performance stays constant within each range, which is unrealistic. While step functions aren't suitable for modeling athletic performance, they do introduce the idea of breaking up data into sections, which is useful in more advanced smoothing techniques.

Splines: These are a more flexible way to model non-linear data. Splines essentially "stitch" together small curves (with constraints to keep them smooth) to fit the data better. A specific type of spline called B-splines was used, which place more knots (or change points) where the data varies more rapidly and fewer knots where it is stable. This allows for a smoother and more realistic fit compared to polynomial regression.

Different types of splines were compared, including:

B-splines: Showed a good fit, especially when using 3 degrees of freedom, meaning only a few knots were needed to capture changes in performance accurately.
Natural Splines: These are similar to B-splines but with added constraints that ensure the model behaves better at the boundaries of the data. This made the fit look more realistic, especially when there were fewer data points.
P-splines: This type adds a penalty to prevent the model from overfitting (capturing too much noise in the data). While effective, P-splines were harder to implement compared to B- and natural splines, so they were not used in the final analysis.
In the end, B-splines and natural splines (with around 3 degrees of freedom) gave the most realistic fits to the data, based on both statistical analysis and knowledge of sports performance. The choice of which smoothing method to use depends on both how the data behaves and the ease of implementation.

Visual Comparisons: Throughout the chapter, various graphs show how each method fits the data. Polynomial regression struggled to handle rapid changes, while splines, especially B-splines and natural splines, provided much smoother and more accurate representations of performance changes over time.


### Workflow

When comparing models of increasing complexity it has been recommended by Gelman (15) that simple linear models are fitted initially and then adapted to generate more complex models (according to some goodness-of-fit criterion) with this process repeated until no further improvements were evident. 
Given the aims of this research, age will be the fixed effect component and the remaining covariates used to explain the underlying variance structures.
The following 9 models (written symbolically) were fitted sequentially to model the relationship between the (fixed) covariate Age and the response variable of interest, namely Performance:
	Simple Linear Regression:
Performance ~ Age
	Multiple Linear Regression:
Performance ~ Age + ID + Country + Year + Event + Venue
	LMM with one random intercept:
Performance ~ Age + (1|ID)
	LMM with random intercept and natural spline smoothing:
Performance ~ ns(Age, df = 3) + (1|ID)
	LMM with random intercept and B-spline smoothing:
Performance ~ bs(Age, df = 3) + (1|ID)
	LMM with random intercept and polynomial smoothing:
Performance ~ poly(Age, df = 3) + (1|ID)
	LMM with B-spline smoothing and hierarchical structure on Country:Athlete as a random intercept:
Performance ~ bs(Age, df = 3) + (1| ID:Country)
	LMM with hierarchical structure and additional B-spline at random effect level:
Performance ~ bs(Age, df = 3) + (bs(Age, df = 3)| ID:Country)
	LMM with additional random effects:
Performance ~ bs(Age, df = 3) + (1|Venue) + (1|Year) + (1|Country) + (bs(Age, df = 3)| ID:Country)

All LMM’s were fitted using the lmer function of the lme4 R package (16). The lme4 package default output for LMM’s provides t-values but no p-values. The primary motivation for this omission is that in LMM’s it is not at all obvious what the appropriate denominator degrees of freedom to use are, except perhaps for some simple designs and nicely balanced data (17). In this project, significance of LMM’s were calculated using the lmerTest package (18). Prediction intervals from the LMM’s were obtained using the ‘predictInterval’ function from the merTools package (19). R^2 values for LMMs were estimated using the MuMin package (20).


## Building my Model


QUOTE TEXT

Validating the assumptions is arguably more important in this thesis than predictive accuracy given the main aim is to develop a model to gain insight into how performance is related to increasing age.what does this mean? Validating the assumptions is arguably more important in this thesis than predictive accuracy given the main aim is to develop a model to gain insight into how performance is related to increasing age.

This sentence means that in this thesis, it's more important to ensure that the underlying assumptions of the model are correct than to focus solely on how well the model predicts performance. The goal is not just to make accurate predictions but to understand the relationship between performance and age. If the model's assumptions (like how variables behave or interact) are valid, the insights gained from the model will be reliable and meaningful, even if the model isn’t perfect at making predictions. Essentially, understanding the "why" behind the data is the priority over just getting the "right" answer.


something about the application of linear mixed models into other real world examples

Add photo of some young high jumper...definitely not me 

# other modelling approaches
machien learning
excited to applicatiosn fo LMMs to swimming results, 

