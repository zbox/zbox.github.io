---
title       : Shiny Application and Reproducible Pitch
subtitle    : Stock price visualisation app
author      : A.Zhukov
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap]   # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## About

The Stock price app allow you to visualize stock price data over a period of time. 

This assignment has two parts. First, the application which is deployed on Rstudio's servers. Second, the reproducible pitch presentation about Stock price visualisation app.

### Shiny app:
- *https://azhukov.shinyapps.io/shiny3/*

### Presentation
- *https://zbox.github.io/stockprice-app/*

--- .class #id 

## Application structure

The app consist of ui and server parts:

### ui.R
The app allow to extract stockprice information for AAPL (Apple), GOOG (Google), YNDX (Yandex), (MSFT) Microsoft and IBM (IBM) tickers. It is possible to define a style of chart to draw (Candlesticks, Line or Bars) and technical analysis indicators.

### server.R
Loads the data for the selected stock symbol, and the selected data range using getSymbols form the quantmod package and plots it using chartSeries.

--- .class #id 

## Quantmod 

The app is based on quantmod prototyping environment. Quantmod is an r package for quantitative financial modelling and trading framework. 

Stock price dataset example:

```
## [1] "AAPL"
```

```
##            AAPL.Open AAPL.High AAPL.Low AAPL.Close AAPL.Volume AAPL.Adjusted
## 2007-01-03  12.32714  12.36857 11.70000   11.97143   309579900 10.73159
## 2007-01-04  12.00714  12.27857 11.97429   12.23714   211815100 10.96978
## 2007-01-05  12.25286  12.31428 12.05714   12.15000   208685400 10.89166
## 2007-01-08  12.28000  12.36143 12.18286   12.21000   199276700 10.94545
## 2007-01-09  12.35000  13.28286 12.16429   13.22429   837324600 11.85469
## 2007-01-10  13.53571  13.97143 13.35000   13.85714   738220000 12.42201
```

--- .class #id 

## Technical indicators
The app uses 2 indicators: moving average and bollinger bands.

### Moving average
An indicator that helps smooth out price action by filtering out the "noise" from random price fluctuations. A moving average (MA) is a trend-following or lagging indicator because it is based on past prices. The average is taken over a specific period of time.

### Bollinger bands
Bollinger Bands consist of a band of three lines which are plotted in relation to security prices. The line in the middle is a Simple Moving Average. The SMA then serves as a base for the Upper and Lower Bands. The Upper and Lower Bands are used as a way to measure volatility by observing the relationship between the Bands and price.
