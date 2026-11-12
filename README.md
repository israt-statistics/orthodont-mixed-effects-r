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
