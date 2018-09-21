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
    ##  1 3.84  TRUE        usa           M         
    ##  2 3.92  TRUE        canada        M         
    ##  3 0.536 FALSE       france        M         
    ##  4 2.33  TRUE        england       F         
    ##  5 3.91  TRUE        japan         M         
    ##  6 2.79  TRUE        sweden        F         
    ##  7 1.33  FALSE       korea         M         
    ##  8 4.78  TRUE        germany       F         
    ##  9 1.68  FALSE       italy         M         
    ## 10 2.98  TRUE        austria       F

``` r
#mean of variables in dataframe
mean(df$rs)
```

    ## [1] 2.810252

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

``` r
###We can calculate numeric and logical vectors' means because the logical vector "FALSE" and "TRUE" was transformed into numeric 0 and 1. Since character and factor cannot be transformed, their means could not be calculated.
```

``` r
as.numeric(df$vec_logical)
```

    ##  [1] 1 1 0 1 1 1 0 1 0 1

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
###It shows logical "TRUE" and "FALSE" could be converted into numeric 1 and 0, while character and factor variables could not be converted (respectively replaced by "NA" after coercion).
```

``` r
as.numeric(
  as.factor(df$vec_character)
)
```

    ##  [1] 10  2  4  3  7  9  8  5  6  1

``` r
as.numeric(
  as.character(df$vec_factor)
)
```

    ## Warning: NAs introduced by coercion

    ##  [1] NA NA NA NA NA NA NA NA NA NA

``` r
###If I convert character to factor then numeric, it will work. It seems those characters refer to data in some database? While converting factor to character then numeric doesn't work (respectively replaced by "NA" after coercion).
```

Problem 2
=========

``` r
set.seed(777)

x = rnorm(1000)
y = rnorm(1000)
vec_logical2 = x + y > 0
vec_numeric2 = as.numeric(vec_logical2)
vec_factor2 = as.factor(vec_logical2)
```
