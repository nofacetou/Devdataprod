---
title       : My First Shiny App  
subtitle    : To get the stock price and return
author      : WANG, Yihong
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Inspiration 

My Shiny App is inspired by [RStudio stockVis example](http://shiny.rstudio.com/tutorial/lesson6/).I made modifications include:
* Delete unnecessary ui element and functions
* Use the adjusted price rather than the unadjusted price
* Add a tab to display the monthly return table

--- .class #id 

## Return Caculation
Here's an example that retrieves Microsoft adjusted stock price and returns a monthly table

```r
library(quantmod);
data <- getSymbols("MSFT", src = "yahoo", from ="2013-01-03", to = "2014-06-20", auto.assign = FALSE);
data <- data[, "MSFT.Adjusted", drop=F];
head(monthlyReturn(data))
```

```
##            monthly.returns
## 2013-01-31        0.007288
## 2013-02-28        0.021325
## 2013-03-28        0.029083
## 2013-04-30        0.156884
## 2013-05-31        0.061697
## 2013-06-28       -0.010324
```

---
## App Demo

<iframe src="https://wyih.shinyapps.io/test1/" width="100%" 
height="100%" frameborder="0">Loading</iframe>


---
## How to use the App

* [My shinyapp.io](https://wyih.shinyapps.io/test1/)
* Call my [Github Gist](https://gist.github.com/nofacetou/66b31a379c7670979f68): Run `shiny::runGist('66b31a379c7670979f68')` in your RStudio.



