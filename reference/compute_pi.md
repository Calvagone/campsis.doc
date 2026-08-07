# Compute the prediction interval summary over time.

Compute the prediction interval summary over time.

## Usage

``` r
compute_pi(x, variable, strata = get_default_strata(), level = 0.9)
```

## Arguments

- x:

  data frame

- variable:

  variable(s) used to compute the prediction interval, character vector.

- strata:

  named vector with the strata to use, default is c(SCENARIO="all",
  ARM="all").

- level:

  PI level, default is 0.9 (90% PI)

## Value

a summary table
