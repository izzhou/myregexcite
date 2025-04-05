
<!-- README.md is generated from README.Rmd. Please edit that file -->

# myregexcite

<!-- badges: start -->

<!-- badges: end -->

The goal of myregexcite is to make working with regular expressions in R
more convenient and user-friendly. It provides helper functions that
simplify common string manipulation tasks.

## Installation

You can install the development version of myregexcite like so:

``` r
# install.packages("devtools")
devtools::install_github("izzhou/myregexcite")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
library(myregexcite)
# Example string with comma-separated values
text <- "alfa,bravo,charlie,delta"

# Traditional approach with base R
strsplit(text, split = ",")
#> [[1]]
#> [1] "alfa"    "bravo"   "charlie" "delta"

# Our simplified function returns a character vector directly
str_split_one(text, pattern = ",")
#> [1] "alfa"    "bravo"   "charlie" "delta"

# It also handles various pattern types and options
# Split on first comma only
str_split_one("a,b,c", pattern = ",", n = 2)
#> [1] "a"   "b,c"

# Split by period using fixed matching
str_split_one("192.168.0.1", pattern = stringr::fixed("."))
#> [1] "192" "168" "0"   "1"
```

The str_split_one() function is particularly useful when you know your
input is a single string and you want the result as a character vector
rather than a list.

What is special about using `README.Rmd` instead of just `README.md`?
You can include R chunks like so:

``` r
summary(cars)
#>      speed           dist       
#>  Min.   : 4.0   Min.   :  2.00  
#>  1st Qu.:12.0   1st Qu.: 26.00  
#>  Median :15.0   Median : 36.00  
#>  Mean   :15.4   Mean   : 42.98  
#>  3rd Qu.:19.0   3rd Qu.: 56.00  
#>  Max.   :25.0   Max.   :120.00
```

You’ll still need to render `README.Rmd` regularly, to keep `README.md`
up-to-date. `devtools::build_readme()` is handy for this.

You can also embed plots, for example:

<img src="man/figures/README-pressure-1.png" width="100%" />

In that case, don’t forget to commit and push the resulting figure
files, so they display on GitHub and CRAN.
