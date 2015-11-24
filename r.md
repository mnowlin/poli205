---
title: R Help
category: r
layout: default
---

# R Help

_R_, as noted on its website, is a free software environment for statistical computing and graphics. It could be used and accessed on any operating system. _R_ is a command based program, meaning that you will be creating and running _R_ code (or scripts) for all the statistical analysis you will be performing. A portion of class time will be spent in _R_ lab sessions. 


_RStudio_ is a user interface program for _R_. It makes the use of _R_ more straightforward. However, _R_ does have a steep learning curve, but example code for all the types of analyses that you will be required to do will be provided.

For help with (very likely) all of your _R_ related questions, go to [Quick R](http://www.statmethods.net). Additional help will be provided in class and on this web page. 

## Downloading R and RStudio

### R

To download R follow the link for your operating system

* [Windows](http://cran.r-project.org/bin/windows/base/)
* [Mac](http://cran.r-project.org/bin/macosx/)


### RStudio

To download RStudio go [here](http://www.rstudio.com/products/rstudio/download/) and then select your operating system.


## Steps for Doing Quantitative Analysis with R

* Create working directory
* Place files in the working directory 
    * Data (.csv file) and R code (.R file)
* Open RStudio 
* Set working directory 
* Load the data set into `R`
* Attach the data set
* Do the analysis 

## R Code

* From R lab 4


##### set your working directory 
##### RStudio: Session -> Set Working Directory -> Choose Directory 

##### load data:
`Rlab4data <- read.csv("Rlab4data.csv")`

##### attach data
`attach(Rlab4data)`

##### variable labels 
`names(Rlab4data)`

### Descriptive Statistics 

##### what is the average age of the respondents? 
`mean(age)`

##### what is the standard deviation of age
`sd(age)`

### Bivariate hypothesis testing 

#### H1: Tea party supporters are less supportive of Obama than non tea party supporters 

###### create table 
`approve <- table(obama,teaparty)` 

###### view table
`approve`

##### Chi-square test
`chisq.test(approve)`

#### H2: Tea party supporters view the environment as less of a priority than non tea party supporters 

##### t-test
`t.test(environment ~ teaparty)`

#### H3: As respondents become more liberal, they are more likely to view the environment as a priority 

##### Pearson's R, correlation coefficient 
`cor(environment,ideology)`

##### t-test of Pearson's R 
`r cor.test(environment,ideology)`

### Simple regression 

#### H3: As respondents become more liberal, they are more likely to view the environment as a priority 

##### OLS regression with one independent variable 
`ols1 <- lm(environment ~ ideology)`
`summary(ols1)`

### Multiple regression 

#### H3: As respondents become more liberal, they are more likely to view the environment as a priority 

##### OLS regression with multiple independent variables 
`r ols2 <- lm(environment ~ ideology+teaparty+age)`
`summary(ols2)`

