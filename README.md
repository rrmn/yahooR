# yahooR
A little function to web scrape Yahoo Finance data like financials or key statistics. More are to come. It requires tidyverse and rvest to run properly.


# Instructions

1. Download the file **yahooR.R**

1. Load the script via `source("folder/yahooR.R")`

# Usage examples

### Get Financials

    get_yahoo("MSFT", "financials")

### Get Key Statistics

    get_yahoo("AAPL", "statistics)
