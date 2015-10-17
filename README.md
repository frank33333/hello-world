# hello-world
Just another repository
Frank here,looking to learn the basics of coding. 

stock-code.R
15 lines (10 sloc)  292 Bytes
library(xts)
library(quantmod)

prices <- getSymbols("GOOG", auto.assign = FALSE)
move <- Cl(last(prices)) - Op(last(prices))

ifelse(move > 0, "BUY", "SELL")

chartSeries(prices, theme = chartTheme("white", bg.col = "white"))

as.data.frame(prices)[1:5 , 1:4]

foo <- function(x) {
  x + 1
}

stock-report.Rmd
r params$symbol
# set up

library(xts)
library(quantmod)

prices <- getSymbols(params$symbol, auto.assign = FALSE)
move <- Cl(last(prices)) - Op(last(prices))
Recommendation: r ifelse(move > 0, "BUY", "SELL")

r params$symbol will r ifelse(move > 0, "increase", "decrease") in price during the next trading period.

Price History

The chart below is made with the quantmod R package, a widely used package for collecting and visualizing financial data in R. You can learn more about quantmod at the website www.quantmod.com.

chartSeries(prices, theme = chartTheme("white", bg.col = "white"))
Method

This forecast was predicted with the recency algorithm, a simple---probably useless---method for determining stock prices. The recency algorithm predicts that the next price movement, $M_{j}$, will be in the same direction as the most recent price movement. $M_{i}$.

$$M_{i}= Close_{i} - Open_{i}$$

$$ M_{j}= \begin{cases} > 0, & \text{if } M_{i} > 0\ \leq 0, & \text{if } M_{i}\leq 0 \end{cases} $$

Raw Data

The table below displays the daily price data for the stock. In the next section, we will learn how to make a concise, interactive table with the DT package, a new package for making searchable data tables. You can learn more about the DT package at the website rstudio.github.io/DT/.

as.data.frame(prices)[1:5 , 1:4]

stock-text.Rmd
GOOG
Recommendation: ?

GOOG will ? in price during the next trading period.

Price History

The chart below is made with the quantmod R package, a widely used package for collecting and visualizing financial data in R. You can learn more about quantmod at the website www.quantmod.com.

Method

This forecast was predicted with the recency algorithm, a simple---probably useless---method for determining stock prices. The recency algorithm predicts that the next price movement, $M_{j}$, will be in the same direction as the most recent price movement. $M_{i}$.

$$M_{i}= Close_{i} - Open_{i}$$

$$ M_{j}= \begin{cases} > 0, & \text{if } M_{i} > 0\ \leq 0, & \text{if } M_{i}\leq 0 \end{cases} $$

Raw Data

The table below displays the daily price data for the stock. In the next section, we will learn how to make a concise, interactive table with the DT package, a new package for making searchable data tables. You can learn more about the DT package at the website rstudio.github.io/DT/.

