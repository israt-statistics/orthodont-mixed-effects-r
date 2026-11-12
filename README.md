# Linear Mixed-Effects Models for Orthodontic Growth Data

## Overview

This project studies how jaw growth changes with age in children, and whether growth differs between boys and girls. Because the same child is measured repeatedly, I used linear mixed-effects models, which allow each child to have their own starting level and growth rate.

## Data

- Source: the `Orthodont` dataset from the `nlme` package in R
- 27 children, each measured 4 times between ages 8 and 14 (108 observations)
- `distance` : distance in mm from the pituitary to the pterygomaxillary fissure (outcome)
- `age` : age in years
- `Subjects` : Child ID
- `Sex` : Male or Female

## Methods

- Plotted each child's growth trajectory by sex.
- Compared a random-intercept model with a random-intercept and random-slope model.
- Compared models with `age` , `age + Sex` and `age * Sex` as fixed effects , using maximum likelihood.
- Refitted the final model using REML.
- Calculated the interclass correlation (ICC) and 95% confidence intervals for the fixed effects.
- Checked the model using residual plots and Q-Q plots.

## R Packages

- `nlme` : fitting the mixed-effects models (`lme`) and the `Orthodont` data
- `ggplot2` : plots

## Results

### Growth trajectories

![Individual growth trajectories by sex](growth_trajectories.png)

Each thin lines is one child ( 16 boys, 11 girls); thick line shows the average linear trend for each sex. Most children show an upward trend, but starting levels and growth rates differ between children. Boys appear to grow faster than girls.

### Random effects structure

| Model | df | AIC | BIC | LogLik | Test | L. Ratio | p-value | 
| --- | --- | --- | --- | --- | --- | --- | --- |
| Random intercept (m1) | 4 | 455.00 | 465.66 | -223.50 | | | |
 Random intercept + slope (m2) | 6 | 454. 64 | 470.62 | -221.32 | 1 vs 2 | 4.37 | 0.1127 |

 The Likelihood ratio Test (LRT = 4.37, P= 0.113> 0.05) showed no significant improvement after adding a random slope. The AIC values were also very similar (455.00 vs. 454.64).

 Although the random slope model did not provide a significant improvement, I retained it in subsequent analyses to account for potential individual differences in growth rates among children. 
