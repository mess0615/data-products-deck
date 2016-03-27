---
title       : Shiny App to Predict Auto Fuel Economy
subtitle    : Predict a vehicle's MPG using a multivariate linear model.
author      : James M.
job         : Coursera Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Background

A Shiny app was built to make it easy to interactively predict the fuel economy in MPG for a vehicle 
based on several variables.

The mtcars dataset (from 1974 Motor Trend US magazine) was used to build a multivariate linear model.

---

## Model Building

A fairly efficient linear model was built using transmission type (automatic or manual), weight and horsepower. 




```r
mtcars$am <- factor(mtcars$am, labels=c('Auto', 'Manual'))
fit <- lm(mpg ~ am + wt + hp, mtcars)
summary(fit)$coef
```

```
##                Estimate  Std. Error   t value     Pr(>|t|)
## (Intercept) 34.00287512 2.642659337 12.866916 2.824030e-13
## amManual     2.08371013 1.376420152  1.513862 1.412682e-01
## wt          -2.87857541 0.904970538 -3.180850 3.574031e-03
## hp          -0.03747873 0.009605422 -3.901830 5.464023e-04
```

---

## Usage

To use the Shiny app:

<ul>
    <li>Go to the URL http://mess0615.shinyapps.io/data-products/</li>
    <li>Enter the vehicle's weight in lbs</li>
    <li>Enter the vehicle's horsepower (hp)</li>
    <li>Choose the transmission type (auto or manual)</li>
    <li>The predicted fuel economy (in MPG) will be displayed dynamically</li>
    <li>You can change any variable interactively to see how it affects the prediction</li>
</ul>

---

## Screenshot of App

<img src="assets/img/shinyapp.jpg" />
