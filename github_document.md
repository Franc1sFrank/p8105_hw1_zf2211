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
    ##  1  4.03 TRUE        usa           M         
    ##  2  3.70 TRUE        canada        M         
    ##  3  1.79 FALSE       france        M         
    ##  4  1.77 FALSE       england       F         
    ##  5  1.95 FALSE       japan         M         
    ##  6  1.66 FALSE       sweden        F         
    ##  7  1.03 FALSE       korea         M         
    ##  8  4.87 TRUE        germany       F         
    ##  9  1.14 FALSE       italy         M         
    ## 10  3.87 TRUE        austria       F

``` r
#mean of variables in dataframe
mean(df$rs)
```

    ## [1] 2.580456

``` r
mean(df$vec_logical)
```

    ## [1] 0.4

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

``` r
###We can calculate numeric and logical vectors' means because the logical vector "FALSE" and "TRUE" was transformed into numeric 0 and 1. Since character and factor cannot be transformed, their means could not be calculated.
```

``` r
as.numeric(df$vec_logical)
```

    ##  [1] 1 1 0 0 0 0 0 1 0 1

``` r
as.numeric(df$vec_character)
```

    ## Warning: NAs introduced by coercion

    ##  [1] NA NA NA NA NA NA NA NA NA NA

``` r
as.numeric(df$vec_factor)
```

    ## Warning: NAs introduced by coercion

    ##  [1] NA NA NA NA NA NA NA NA NA NA

``` r
###It shows logical "TRUE" and "FALSE" could be transformed into numeric 1 and 0, while character and factor variables could not be transformed.
```
