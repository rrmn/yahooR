library(tidyverse)
library(rvest)

get_yahoo <- function(stock, type = "financials"){
    if(type == "financials"){
        url <- paste0("https://finance.yahoo.com/quote/", stock, "/financials?p=", stock)
    } else if(type == "statistics"){
        url <- paste0("https://finance.yahoo.com/quote/", stock, "/key-statistics?p=", stock)
#    } else if(type == "analysis"){
#        url <- paste0("https://finance.yahoo.com/quote/", stock, "/analysis?p=", stock)
    } else {
        stop("Please enter the type of data that you would like to scrape (e.g., \"statistics\")")
    }
    
    # Extract and transform data
    x <- url %>% 
        read_html() %>% 
        html_table() %>% 
        map_df(bind_cols) %>% 
        # Transpose
        t() %>%
        as_tibble()
    
    # Set first row as column names
    colnames(x) <- x[1,]
    # Remove first row
    x <- x[-1,]
    # Add stock name column
    x$Stock_Name <- stock
    
    return(x)
}
