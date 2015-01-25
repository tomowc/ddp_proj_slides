---
title       : NRI Explorer
subtitle    : Developing Data Products Course Project (January 2015)
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
--- 

## Motivation

* Each year World Economic Forum publishes [report](http://www.weforum.org/reports/global-information-technology-report-2014) which presents [NRI](http://en.wikipedia.org/wiki/Networked_Readiness_Index) index for about 150 countries
* Information card about specific country looks like this:

![200](./assets/img/img1.jpg)


* The aim of the presented application was to provide the possibility of comparing countries in terms of 10 main indicators which formulate the NRi index

--- 

## Application description

* Basic assumption: simple - just choose countries and watch data changing
* Data presented in radar chart

![200](./assets/img/img2.jpg)


--- 

## File Global.R

* Its role is to prepare the original data obtained from [this](http://www.weforum.org/global-information-technology-report-2014-data-platform) site, which are in the long format (i.e. few columns):




```
## 'data.frame':	31106 obs. of  11 variables:
##  $ Edition          : int  2012 2013 2014 2012 2013 2014 2012 2013 2014 2012 ...
##  $ Entity.code      : chr  "AGO" "AGO" "AGO" "ALB" ...
##  $ Entity           : chr  "Angola" "Angola" "Angola" "Albania" ...
##  $ GLOBAL.ID        : chr  "NRI" "NRI" "NRI" "NRI" ...
##  $ Series.with.units: chr  "Networked Readiness Index (1-7)" "Networked Readiness Index (1-7)" "Networked Readiness Index (1-7)" "Networked Readiness Index (1-7)" ...
##  $ Rank             : int  140 NA 144 68 83 95 30 25 24 92 ...
##  $ Value            : num  2.49 NA 2.52 3.89 3.75 ...
##  $ Date.description : chr  "2012 edition" "2013 edition" "2014 edition" "2012 edition" ...
##  $ Note             : chr  "Refer to Chapter 1.1 of The Global Information Technology 2012 for details about the computation methodology" "Refer to Chapter 1.1 of The Global Information Technology Report 2013 for details about the computation" "Refer to Chapter 1.1 of The Global Information Technology 2014 for details about the computation methodology" "Refer to Chapter 1.1 of The Global Information Technology 2012 for details about the computation methodology" ...
##  $ Source           : chr  "World Economic Forum;The Global Information Technology Report 2012; www.weforum.org/gcr" "World Economic Forum;The Global Information Technology Report 2013;www.weforum.org/gitr" "World Economic Forum;The Global Information Technology Report 2014; www.weforum.org/gcr" "World Economic Forum;The Global Information Technology Report 2012; www.weforum.org/gcr" ...
##  $ Source.date      : chr  "24/04/2012" "01/4/2013" "22/04/2014" "24/04/2012" ...
```

(the aim was to be absolutely transparent about all data transformation performed for the assignment)

--- 

## Files ui.R and server.R

* ui.R is responsible for application interface - it mainly allows a user to choose countries, but it also presents information about application
* server.R reacts on user's action - it selects data for chosen countries, combines them into one dataframe and then creates plot and table to be displayed




Oh, and [one more thing](https://www.youtube.com/watch?v=hyCzbXx9i-M) ;) The user is allowed to download data in a simplified form.
