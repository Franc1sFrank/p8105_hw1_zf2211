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
    ##  1 1.25  FALSE       usa           M         
    ##  2 3.67  TRUE        canada        M         
    ##  3 2.96  TRUE        france        M         
    ##  4 0.808 FALSE       england       F         
    ##  5 2.54  TRUE        japan         M         
    ##  6 3.99  TRUE        sweden        F         
    ##  7 2.33  TRUE        korea         M         
    ##  8 1.93  FALSE       germany       F         
    ##  9 3.86  TRUE        italy         M         
    ## 10 4.51  TRUE        austria       F

``` r
#mean of variables in dataframe
mean(df$rs)
```

    ## [1] 2.785369

``` r
mean(df$vec_logical)
```

    ## [1] 0.7

``` r
mean(df$vec_character)
```

    ## Warning in mean.default(df$vec_character): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
mean(df$vec_factor)
```

    ## Warning in mean.default(df$vec_factor): argument is not numeric or logical:
    ## returning NA

    ## [1] NA
