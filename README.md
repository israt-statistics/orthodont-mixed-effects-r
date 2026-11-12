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
