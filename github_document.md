p8105\_hw1\_zf2211
================
Francis
9/21/2018

Problem 1
=========

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
sed.seed = 777
rs = runif(10, 0, 5)
df = tibble(
  rs,
  vec_logical = rs>2,
  vec_character = c("usa", "canada", "france", "england", "japan", "sweden", "korea", "germany", "italy", "austria"),
  vec_factor = c("M", "M", "M", "F", "M", "F", "M", "F", "M", "F")
)
#print df
df
```

    ## # A tibble: 10 x 4
    ##       rs vec_logical vec_character vec_factor
    ##    <dbl> <lgl>       <chr>         <chr>     
    ##  1 3.42  TRUE        usa           M         
    ##  2 4.55  TRUE        canada        M         
    ##  3 3.99  TRUE        france        M         
    ##  4 0.508 FALSE       england       F         
    ##  5 1.63  FALSE       japan         M         
    ##  6 2.79  TRUE        sweden        F         
    ##  7 0.411 FALSE       korea         M         
    ##  8 3.80  TRUE        germany       F         
    ##  9 0.373 FALSE       italy         M         
    ## 10 3.45  TRUE        austria       F
