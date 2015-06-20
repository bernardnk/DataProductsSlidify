---
title       : Logistic Regression
subtitle    : Probability of college admission
author      : Bernard NK
job         : Developing Data Products Project
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Predict admission into graduate school

This logistic regression has 3 predictor variables to determine the effect on admission into graduate school:
* GRE (Graduate Record Exam scores)
* GPA (grade point average)
* Prestige of the undergraduate institution (RANK from 1 to 4)

The outcome variable (prediction), admit/don't admit, is a binary variable.

--- .class #id 

## How to use the Shiny application

How to use the reactive Shiny application:  
  
1. Click on this link: https://bernardnk.shinyapps.io/Project  
2. "Choose a Rank" to see the predicted probability of admission based on the Rank variable.  
3. Pick the "Number of observations to view" to see the observations for the selected rank.  
4. "PredictedProb" is the outcome variable (prediction), admit/don't admit, which is a binary variable.  

Note that the GPA is set to a constant value set to the overall mean.  

--- .class #id 

## The sample dataset

Here is a R expression executed here to display the data structure. The same dataset is loaded in the Shiny R application.  


```r
mydata <- read.csv("http://www.ats.ucla.edu/stat/data/binary.csv")
mydata$rank <- factor(mydata$rank)
mydata$admit <- factor(mydata$admit)
str(mydata)
```

```
## 'data.frame':	400 obs. of  4 variables:
##  $ admit: Factor w/ 2 levels "0","1": 1 2 2 2 1 2 2 1 2 1 ...
##  $ gre  : int  380 660 800 640 520 760 560 400 540 700 ...
##  $ gpa  : num  3.61 3.67 4 3.19 2.93 3 2.98 3.08 3.39 3.92 ...
##  $ rank : Factor w/ 4 levels "1","2","3","4": 3 3 1 4 4 2 1 2 3 2 ...
```

--- .class #id 

## Applicability to other predictions

This application can be converted to predict other types of outcome.

Determine factors that influence:
* Whether a political candidate wins an election, the outcome variable is binary (0/1); win or lose.
* Whether a consumer buys a product, the outcome variable is binary (0/1); buy or not buy.


References:  

* Generalized Linear Models, http://www.statmethods.net/advstats/glm.html  
* R Data Analysis Examples: Logit Regression, http://www.ats.ucla.edu/stat/r/dae/logit.htm  
